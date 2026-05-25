---
name: pydicom
description: 用于处理 DICOM（Digital Imaging and Communications in Medicine）files 的 Python library。当读取、写入或修改 DICOM format 的 medical imaging data，从 medical images（CT、MRI、X-ray、ultrasound）提取 pixel data，匿名化 DICOM files，处理 DICOM metadata 和 tags，将 DICOM images 转换为其他格式，处理 compressed DICOM data，或处理 medical imaging datasets 时使用此 skill。适用于涉及 medical image analysis、PACS systems、radiology workflows 和 healthcare imaging applications 的任务。
license: https://github.com/pydicom/pydicom/blob/main/LICENSE
metadata:
    skill-author: K-Dense Inc.
---

# Pydicom

## 概览

Pydicom 是用于处理 DICOM files 的 pure Python package；DICOM 是 medical imaging data 的标准格式。此 skill 提供读取、写入和操作 DICOM files 的指南，包括处理 pixel data、metadata 和各种 compression formats。

## 何时使用此 Skill

在处理以下内容时使用此 skill：
- Medical imaging files（CT、MRI、X-ray、ultrasound、PET 等）
- 需要 metadata extraction 或 modification 的 DICOM datasets
- 从 medical scans 提取 pixel data 并进行 image processing
- 用于 research 或 data sharing 的 DICOM anonymization
- 将 DICOM files 转换为 standard image formats
- 需要 decompression 的 compressed DICOM data
- DICOM sequences 和 structured reports
- Multi-slice volume reconstruction
- PACS（Picture Archiving and Communication System）integration

## 安装

安装 pydicom 和常见依赖：

```bash
uv pip install pydicom
uv pip install pillow  # For image format conversion
uv pip install numpy   # For pixel array manipulation
uv pip install matplotlib  # For visualization
```

处理 compressed DICOM files 时，可能需要额外 packages：

```bash
uv pip install pylibjpeg pylibjpeg-libjpeg pylibjpeg-openjpeg  # JPEG compression
uv pip install python-gdcm  # Alternative compression handler
```

## 核心 Workflows

### 读取 DICOM Files

使用 `pydicom.dcmread()` 读取 DICOM file：

```python
import pydicom

# Read a DICOM file
ds = pydicom.dcmread('path/to/file.dcm')

# Access metadata
print(f"Patient Name: {ds.PatientName}")
print(f"Study Date: {ds.StudyDate}")
print(f"Modality: {ds.Modality}")

# Display all elements
print(ds)
```

**关键点：**
- `dcmread()` 返回 `Dataset` object
- 使用 attribute notation（例如 `ds.PatientName`）或 tag notation（例如 `ds[0x0010, 0x0010]`）访问 data elements
- 使用 `ds.file_meta` 访问 Transfer Syntax UID 等 file metadata
- 使用 `getattr(ds, 'AttributeName', default_value)` 或 `hasattr(ds, 'AttributeName')` 处理 missing attributes

### 处理 Pixel Data

从 DICOM files 提取并操作 image data：

```python
import pydicom
import numpy as np
import matplotlib.pyplot as plt

# Read DICOM file
ds = pydicom.dcmread('image.dcm')

# Get pixel array (requires numpy)
pixel_array = ds.pixel_array

# Image information
print(f"Shape: {pixel_array.shape}")
print(f"Data type: {pixel_array.dtype}")
print(f"Rows: {ds.Rows}, Columns: {ds.Columns}")

# Apply windowing for display (CT/MRI)
if hasattr(ds, 'WindowCenter') and hasattr(ds, 'WindowWidth'):
    from pydicom.pixel_data_handlers.util import apply_voi_lut
    windowed_image = apply_voi_lut(pixel_array, ds)
else:
    windowed_image = pixel_array

# Display image
plt.imshow(windowed_image, cmap='gray')
plt.title(f"{ds.Modality} - {ds.StudyDescription}")
plt.axis('off')
plt.show()
```

**处理 color images：**

```python
# RGB images have shape (rows, columns, 3)
if ds.PhotometricInterpretation == 'RGB':
    rgb_image = ds.pixel_array
    plt.imshow(rgb_image)
elif ds.PhotometricInterpretation == 'YBR_FULL':
    from pydicom.pixel_data_handlers.util import convert_color_space
    rgb_image = convert_color_space(ds.pixel_array, 'YBR_FULL', 'RGB')
    plt.imshow(rgb_image)
```

**Multi-frame images（videos/series）：**

```python
# For multi-frame DICOM files
if hasattr(ds, 'NumberOfFrames') and ds.NumberOfFrames > 1:
    frames = ds.pixel_array  # Shape: (num_frames, rows, columns)
    print(f"Number of frames: {frames.shape[0]}")

    # Display specific frame
    plt.imshow(frames[0], cmap='gray')
```

### 将 DICOM 转换为 Image Formats

使用提供的 `dicom_to_image.py` script，或手动转换：

```python
from PIL import Image
import pydicom
import numpy as np

ds = pydicom.dcmread('input.dcm')
pixel_array = ds.pixel_array

# Normalize to 0-255 range
if pixel_array.dtype != np.uint8:
    pixel_array = ((pixel_array - pixel_array.min()) /
                   (pixel_array.max() - pixel_array.min()) * 255).astype(np.uint8)

# Save as PNG
image = Image.fromarray(pixel_array)
image.save('output.png')
```

使用 script：`python scripts/dicom_to_image.py input.dcm output.png`

### 修改 Metadata

修改 DICOM data elements：

```python
import pydicom
from datetime import datetime

ds = pydicom.dcmread('input.dcm')

# Modify existing elements
ds.PatientName = "Doe^John"
ds.StudyDate = datetime.now().strftime('%Y%m%d')
ds.StudyDescription = "Modified Study"

# Add new elements
ds.SeriesNumber = 1
ds.SeriesDescription = "New Series"

# Remove elements
if hasattr(ds, 'PatientComments'):
    delattr(ds, 'PatientComments')
# Or using del
if 'PatientComments' in ds:
    del ds.PatientComments

# Save modified file
ds.save_as('modified.dcm')
```

### 匿名化 DICOM Files

移除或替换 patient identifiable information：

```python
import pydicom
from datetime import datetime

ds = pydicom.dcmread('input.dcm')

# Tags commonly containing PHI (Protected Health Information)
tags_to_anonymize = [
    'PatientName', 'PatientID', 'PatientBirthDate',
    'PatientSex', 'PatientAge', 'PatientAddress',
    'InstitutionName', 'InstitutionAddress',
    'ReferringPhysicianName', 'PerformingPhysicianName',
    'OperatorsName', 'StudyDescription', 'SeriesDescription',
]

# Remove or replace sensitive data
for tag in tags_to_anonymize:
    if hasattr(ds, tag):
        if tag in ['PatientName', 'PatientID']:
            setattr(ds, tag, 'ANONYMOUS')
        elif tag == 'PatientBirthDate':
            setattr(ds, tag, '19000101')
        else:
            delattr(ds, tag)

# Update dates to maintain temporal relationships
if hasattr(ds, 'StudyDate'):
    # Shift dates by a random offset
    ds.StudyDate = '20000101'

# Keep pixel data intact
ds.save_as('anonymized.dcm')
```

使用提供的 script：`python scripts/anonymize_dicom.py input.dcm output.dcm`

### 写入 DICOM Files

从零创建 DICOM files：

```python
import pydicom
from pydicom.dataset import Dataset, FileDataset
from datetime import datetime
import numpy as np

# Create file meta information
file_meta = Dataset()
file_meta.MediaStorageSOPClassUID = pydicom.uid.generate_uid()
file_meta.MediaStorageSOPInstanceUID = pydicom.uid.generate_uid()
file_meta.TransferSyntaxUID = pydicom.uid.ExplicitVRLittleEndian

# Create the FileDataset instance
ds = FileDataset('new_dicom.dcm', {}, file_meta=file_meta, preamble=b"\0" * 128)

# Add required DICOM elements
ds.PatientName = "Test^Patient"
ds.PatientID = "123456"
ds.Modality = "CT"
ds.StudyDate = datetime.now().strftime('%Y%m%d')
ds.StudyTime = datetime.now().strftime('%H%M%S')
ds.ContentDate = ds.StudyDate
ds.ContentTime = ds.StudyTime

# Add image-specific elements
ds.SamplesPerPixel = 1
ds.PhotometricInterpretation = "MONOCHROME2"
ds.Rows = 512
ds.Columns = 512
ds.BitsAllocated = 16
ds.BitsStored = 16
ds.HighBit = 15
ds.PixelRepresentation = 0

# Create pixel data
pixel_array = np.random.randint(0, 4096, (512, 512), dtype=np.uint16)
ds.PixelData = pixel_array.tobytes()

# Add required UIDs
ds.SOPClassUID = pydicom.uid.CTImageStorage
ds.SOPInstanceUID = file_meta.MediaStorageSOPInstanceUID
ds.SeriesInstanceUID = pydicom.uid.generate_uid()
ds.StudyInstanceUID = pydicom.uid.generate_uid()

# Save the file
ds.save_as('new_dicom.dcm')
```

### Compression 与 Decompression

处理 compressed DICOM files：

```python
import pydicom

# Read compressed DICOM file
ds = pydicom.dcmread('compressed.dcm')

# Check transfer syntax
print(f"Transfer Syntax: {ds.file_meta.TransferSyntaxUID}")
print(f"Transfer Syntax Name: {ds.file_meta.TransferSyntaxUID.name}")

# Decompress and save as uncompressed
ds.decompress()
ds.save_as('uncompressed.dcm', write_like_original=False)

# Or compress when saving (requires appropriate encoder)
ds_uncompressed = pydicom.dcmread('uncompressed.dcm')
ds_uncompressed.compress(pydicom.uid.JPEGBaseline8Bit)
ds_uncompressed.save_as('compressed_jpeg.dcm')
```

**常见 transfer syntaxes：**
- `ExplicitVRLittleEndian` - Uncompressed，最常见
- `JPEGBaseline8Bit` - JPEG lossy compression
- `JPEGLossless` - JPEG lossless compression
- `JPEG2000Lossless` - JPEG 2000 lossless
- `RLELossless` - Run-Length Encoding lossless

完整列表见 `references/transfer_syntaxes.md`。

### 处理 DICOM Sequences

处理 nested data structures：

```python
import pydicom

ds = pydicom.dcmread('file.dcm')

# Access sequences
if 'ReferencedStudySequence' in ds:
    for item in ds.ReferencedStudySequence:
        print(f"Referenced SOP Instance UID: {item.ReferencedSOPInstanceUID}")

# Create a sequence
from pydicom.sequence import Sequence

sequence_item = Dataset()
sequence_item.ReferencedSOPClassUID = pydicom.uid.CTImageStorage
sequence_item.ReferencedSOPInstanceUID = pydicom.uid.generate_uid()

ds.ReferencedImageSequence = Sequence([sequence_item])
```

### 处理 DICOM Series

处理多个相关 DICOM files：

```python
import pydicom
import numpy as np
from pathlib import Path

# Read all DICOM files in a directory
dicom_dir = Path('dicom_series/')
slices = []

for file_path in dicom_dir.glob('*.dcm'):
    ds = pydicom.dcmread(file_path)
    slices.append(ds)

# Sort by slice location or instance number
slices.sort(key=lambda x: float(x.ImagePositionPatient[2]))
# Or: slices.sort(key=lambda x: int(x.InstanceNumber))

# Create 3D volume
volume = np.stack([s.pixel_array for s in slices])
print(f"Volume shape: {volume.shape}")  # (num_slices, rows, columns)

# Get spacing information for proper scaling
pixel_spacing = slices[0].PixelSpacing  # [row_spacing, col_spacing]
slice_thickness = slices[0].SliceThickness
print(f"Voxel size: {pixel_spacing[0]}x{pixel_spacing[1]}x{slice_thickness} mm")
```

## Helper Scripts

此 skill 在 `scripts/` directory 中包含 utility scripts：

### anonymize_dicom.py
通过移除或替换 Protected Health Information（PHI）匿名化 DICOM files。

```bash
python scripts/anonymize_dicom.py input.dcm output.dcm
```

### dicom_to_image.py
将 DICOM files 转换为常见 image formats（PNG、JPEG、TIFF）。

```bash
python scripts/dicom_to_image.py input.dcm output.png
python scripts/dicom_to_image.py input.dcm output.jpg --format JPEG
```

### extract_metadata.py
以可读格式提取并显示 DICOM metadata。

```bash
python scripts/extract_metadata.py file.dcm
python scripts/extract_metadata.py file.dcm --output metadata.txt
```

## 参考材料

详细 reference information 位于 `references/` directory：

- **common_tags.md**：按 category（Patient、Study、Series、Image 等）组织的常用 DICOM tags 完整列表
- **transfer_syntaxes.md**：DICOM transfer syntaxes 和 compression formats 的完整参考

## 常见问题与解决方案

**Issue: "Unable to decode pixel data"**
- Solution：安装额外 compression handlers：`uv pip install pylibjpeg pylibjpeg-libjpeg python-gdcm`

**Issue: "AttributeError" when accessing tags**
- Solution：用 `hasattr(ds, 'AttributeName')` 检查 attribute 是否存在，或使用 `ds.get('AttributeName', default)`

**Issue: Incorrect image display (too dark/bright)**
- Solution：应用 VOI LUT windowing：`apply_voi_lut(pixel_array, ds)`，或使用 `WindowCenter` 和 `WindowWidth` 手动调整

**Issue: Memory issues with large series**
- Solution：迭代处理 files，使用 memory-mapped arrays，或 downsample images

## Best Practices

1. **始终检查 required attributes**，在访问前使用 `hasattr()` 或 `get()`
2. **Preserve file metadata**：修改 files 时使用带 `write_like_original=True` 的 `save_as()`
3. **使用 Transfer Syntax UIDs**，在处理 pixel data 前理解 compression format
4. **处理 exceptions**，尤其是从 untrusted sources 读取 files 时
5. **应用正确 windowing**（VOI LUT）进行 medical image visualization
6. **保留 spatial information**（pixel spacing、slice thickness），尤其是处理 3D volumes 时
7. **彻底验证 anonymization**，再共享 medical data
8. **正确使用 UIDs** - 创建 new instances 时生成 new UIDs，修改时保留它们

## 文档

Official pydicom documentation: https://pydicom.github.io/pydicom/dev/
- User Guide: https://pydicom.github.io/pydicom/dev/guides/user/index.html
- Tutorials: https://pydicom.github.io/pydicom/dev/tutorials/index.html
- API Reference: https://pydicom.github.io/pydicom/dev/reference/index.html
- Examples: https://pydicom.github.io/pydicom/dev/auto_examples/index.html
