---
name: pymatgen
description: Materials science toolkit。面向 computational materials science，支持 crystal structures（CIF、POSCAR）、phase diagrams、band structure、DOS、Materials Project integration 和 format conversion。
license: MIT license
metadata:
    skill-author: K-Dense Inc.
---

# Pymatgen - Python Materials Genomics

## 概览

Pymatgen 是支撑 Materials Project 的综合 Python library，用于 materials analysis。它可创建、分析和操作 crystal structures 与 molecules，计算 phase diagrams 和 thermodynamic properties，分析 electronic structure（band structures、DOS），生成 surfaces 和 interfaces，并访问 Materials Project 的 computed materials database。支持来自多种 computational codes 的 100+ file formats。

## 何时使用此 Skill

此 skill 应用于：
- 在 materials science 中处理 crystal structures 或 molecular systems
- 在 structure file formats（CIF、POSCAR、XYZ 等）之间转换
- 分析 symmetry、space groups 或 coordination environments
- 计算 phase diagrams 或评估 thermodynamic stability
- 分析 electronic structure data（band gaps、DOS、band structures）
- 生成 surfaces、slabs 或研究 interfaces
- 以程序方式访问 Materials Project database
- 设置 high-throughput computational workflows
- 分析 diffusion、magnetism 或 mechanical properties
- 处理 VASP、Gaussian、Quantum ESPRESSO 或其他 computational codes

## 快速开始指南

### 安装

```bash
# Core pymatgen
uv pip install pymatgen

# With Materials Project API access
uv pip install pymatgen mp-api

# Optional dependencies for extended functionality
uv pip install pymatgen[analysis]  # Additional analysis tools
uv pip install pymatgen[vis]       # Visualization tools
```

### 基础 Structure Operations

```python
from pymatgen.core import Structure, Lattice

# Read structure from file (automatic format detection)
struct = Structure.from_file("POSCAR")

# Create structure from scratch
lattice = Lattice.cubic(3.84)
struct = Structure(lattice, ["Si", "Si"], [[0,0,0], [0.25,0.25,0.25]])

# Write to different format
struct.to(filename="structure.cif")

# Basic properties
print(f"Formula: {struct.composition.reduced_formula}")
print(f"Space group: {struct.get_space_group_info()}")
print(f"Density: {struct.density:.2f} g/cm³")
```

### Materials Project Integration

```bash
# Set up API key
export MP_API_KEY="your_api_key_here"
```

```python
from mp_api.client import MPRester

with MPRester() as mpr:
    # Get structure by material ID
    struct = mpr.get_structure_by_material_id("mp-149")

    # Search for materials
    materials = mpr.materials.summary.search(
        formula="Fe2O3",
        energy_above_hull=(0, 0.05)
    )
```

## 核心能力

### 1. Structure Creation and Manipulation

使用多种方法创建 structures 并执行 transformations。

**From files：**
```python
# Automatic format detection
struct = Structure.from_file("structure.cif")
struct = Structure.from_file("POSCAR")
mol = Molecule.from_file("molecule.xyz")
```

**From scratch：**
```python
from pymatgen.core import Structure, Lattice

# Using lattice parameters
lattice = Lattice.from_parameters(a=3.84, b=3.84, c=3.84,
                                  alpha=120, beta=90, gamma=60)
coords = [[0, 0, 0], [0.75, 0.5, 0.75]]
struct = Structure(lattice, ["Si", "Si"], coords)

# From space group
struct = Structure.from_spacegroup(
    "Fm-3m",
    Lattice.cubic(3.5),
    ["Si"],
    [[0, 0, 0]]
)
```

**Transformations：**
```python
from pymatgen.transformations.standard_transformations import (
    SupercellTransformation,
    SubstitutionTransformation,
    PrimitiveCellTransformation
)

# Create supercell
trans = SupercellTransformation([[2,0,0],[0,2,0],[0,0,2]])
supercell = trans.apply_transformation(struct)

# Substitute elements
trans = SubstitutionTransformation({"Fe": "Mn"})
new_struct = trans.apply_transformation(struct)

# Get primitive cell
trans = PrimitiveCellTransformation()
primitive = trans.apply_transformation(struct)
```

**参考：** 参见 `references/core_classes.md`，了解 Structure、Lattice、Molecule 及相关 classes 的完整文档。

### 2. File Format Conversion

通过 automatic format detection 在 100+ file formats 之间转换。

**使用 convenience methods：**
```python
# Read any format
struct = Structure.from_file("input_file")

# Write to any format
struct.to(filename="output.cif")
struct.to(filename="POSCAR")
struct.to(filename="output.xyz")
```

**使用 conversion script：**
```bash
# Single file conversion
python scripts/structure_converter.py POSCAR structure.cif

# Batch conversion
python scripts/structure_converter.py *.cif --output-dir ./poscar_files --format poscar
```

**参考：** 参见 `references/io_formats.md`，了解所有 supported formats 和 code integrations 的详细文档。

### 3. Structure Analysis and Symmetry

分析 structures 的 symmetry、coordination 和其他 properties。

**Symmetry analysis：**
```python
from pymatgen.symmetry.analyzer import SpacegroupAnalyzer

sga = SpacegroupAnalyzer(struct)

# Get space group information
print(f"Space group: {sga.get_space_group_symbol()}")
print(f"Number: {sga.get_space_group_number()}")
print(f"Crystal system: {sga.get_crystal_system()}")

# Get conventional/primitive cells
conventional = sga.get_conventional_standard_structure()
primitive = sga.get_primitive_standard_structure()
```

**Coordination environment：**
```python
from pymatgen.analysis.local_env import CrystalNN

cnn = CrystalNN()
neighbors = cnn.get_nn_info(struct, n=0)  # Neighbors of site 0

print(f"Coordination number: {len(neighbors)}")
for neighbor in neighbors:
    site = struct[neighbor['site_index']]
    print(f"  {site.species_string} at {neighbor['weight']:.3f} Å")
```

**使用 analysis script：**
```bash
# Comprehensive analysis
python scripts/structure_analyzer.py POSCAR --symmetry --neighbors

# Export results
python scripts/structure_analyzer.py structure.cif --symmetry --export json
```

**参考：** 参见 `references/analysis_modules.md`，了解所有 analysis capabilities 的详细文档。

### 4. Phase Diagrams and Thermodynamics

构建 phase diagrams 并分析 thermodynamic stability。

**Phase diagram construction：**
```python
from mp_api.client import MPRester
from pymatgen.analysis.phase_diagram import PhaseDiagram, PDPlotter

# Get entries from Materials Project
with MPRester() as mpr:
    entries = mpr.get_entries_in_chemsys("Li-Fe-O")

# Build phase diagram
pd = PhaseDiagram(entries)

# Check stability
from pymatgen.core import Composition
comp = Composition("LiFeO2")

# Find entry for composition
for entry in entries:
    if entry.composition.reduced_formula == comp.reduced_formula:
        e_above_hull = pd.get_e_above_hull(entry)
        print(f"Energy above hull: {e_above_hull:.4f} eV/atom")

        if e_above_hull > 0.001:
            # Get decomposition
            decomp = pd.get_decomposition(comp)
            print("Decomposes to:", decomp)

# Plot
plotter = PDPlotter(pd)
plotter.show()
```

**使用 phase diagram script：**
```bash
# Generate phase diagram
python scripts/phase_diagram_generator.py Li-Fe-O --output li_fe_o.png

# Analyze specific composition
python scripts/phase_diagram_generator.py Li-Fe-O --analyze "LiFeO2" --show
```

**参考：** 详细示例见 `references/analysis_modules.md`（Phase Diagrams section）和 `references/transformations_workflows.md`（Workflow 2）。

### 5. Electronic Structure Analysis

分析 band structures、density of states 和 electronic properties。

**Band structure：**
```python
from pymatgen.io.vasp import Vasprun
from pymatgen.electronic_structure.plotter import BSPlotter

# Read from VASP calculation
vasprun = Vasprun("vasprun.xml")
bs = vasprun.get_band_structure()

# Analyze
band_gap = bs.get_band_gap()
print(f"Band gap: {band_gap['energy']:.3f} eV")
print(f"Direct: {band_gap['direct']}")
print(f"Is metal: {bs.is_metal()}")

# Plot
plotter = BSPlotter(bs)
plotter.save_plot("band_structure.png")
```

**Density of states：**
```python
from pymatgen.electronic_structure.plotter import DosPlotter

dos = vasprun.complete_dos

# Get element-projected DOS
element_dos = dos.get_element_dos()
for element, element_dos_obj in element_dos.items():
    print(f"{element}: {element_dos_obj.get_gap():.3f} eV")

# Plot
plotter = DosPlotter()
plotter.add_dos("Total DOS", dos)
plotter.show()
```

**参考：** 参见 `references/analysis_modules.md`（Electronic Structure section）和 `references/io_formats.md`（VASP section）。

### 6. Surface and Interface Analysis

生成 slabs、分析 surfaces 并研究 interfaces。

**Slab generation：**
```python
from pymatgen.core.surface import SlabGenerator

# Generate slabs for specific Miller index
slabgen = SlabGenerator(
    struct,
    miller_index=(1, 1, 1),
    min_slab_size=10.0,      # Å
    min_vacuum_size=10.0,    # Å
    center_slab=True
)

slabs = slabgen.get_slabs()

# Write slabs
for i, slab in enumerate(slabs):
    slab.to(filename=f"slab_{i}.cif")
```

**Wulff shape construction：**
```python
from pymatgen.analysis.wulff import WulffShape

# Define surface energies
surface_energies = {
    (1, 0, 0): 1.0,
    (1, 1, 0): 1.1,
    (1, 1, 1): 0.9,
}

wulff = WulffShape(struct.lattice, surface_energies)
print(f"Surface area: {wulff.surface_area:.2f} Ų")
print(f"Volume: {wulff.volume:.2f} ų")

wulff.show()
```

**Adsorption site finding：**
```python
from pymatgen.analysis.adsorption import AdsorbateSiteFinder
from pymatgen.core import Molecule

asf = AdsorbateSiteFinder(slab)

# Find sites
ads_sites = asf.find_adsorption_sites()
print(f"On-top sites: {len(ads_sites['ontop'])}")
print(f"Bridge sites: {len(ads_sites['bridge'])}")
print(f"Hollow sites: {len(ads_sites['hollow'])}")

# Add adsorbate
adsorbate = Molecule("O", [[0, 0, 0]])
ads_struct = asf.add_adsorbate(adsorbate, ads_sites["ontop"][0])
```

**参考：** 参见 `references/analysis_modules.md`（Surface and Interface section）和 `references/transformations_workflows.md`（Workflows 3 and 9）。

### 7. Materials Project Database Access

以程序方式访问 Materials Project database。

**Setup：**
1. 从 https://next-gen.materialsproject.org/ 获取 API key
2. 设置 environment variable：`export MP_API_KEY="your_key_here"`

**Search and retrieve：**
```python
from mp_api.client import MPRester

with MPRester() as mpr:
    # Search by formula
    materials = mpr.materials.summary.search(formula="Fe2O3")

    # Search by chemical system
    materials = mpr.materials.summary.search(chemsys="Li-Fe-O")

    # Filter by properties
    materials = mpr.materials.summary.search(
        chemsys="Li-Fe-O",
        energy_above_hull=(0, 0.05),  # Stable/metastable
        band_gap=(1.0, 3.0)            # Semiconducting
    )

    # Get structure
    struct = mpr.get_structure_by_material_id("mp-149")

    # Get band structure
    bs = mpr.get_bandstructure_by_material_id("mp-149")

    # Get entries for phase diagram
    entries = mpr.get_entries_in_chemsys("Li-Fe-O")
```

**参考：** 参见 `references/materials_project_api.md`，了解完整 API documentation 和 examples。

### 8. Computational Workflow Setup

为各种 electronic structure codes 设置 calculations。

**VASP input generation：**
```python
from pymatgen.io.vasp.sets import MPRelaxSet, MPStaticSet, MPNonSCFSet

# Relaxation
relax = MPRelaxSet(struct)
relax.write_input("./relax_calc")

# Static calculation
static = MPStaticSet(struct)
static.write_input("./static_calc")

# Band structure (non-self-consistent)
nscf = MPNonSCFSet(struct, mode="line")
nscf.write_input("./bandstructure_calc")

# Custom parameters
custom = MPRelaxSet(struct, user_incar_settings={"ENCUT": 600})
custom.write_input("./custom_calc")
```

**其他 codes：**
```python
# Gaussian
from pymatgen.io.gaussian import GaussianInput

gin = GaussianInput(
    mol,
    functional="B3LYP",
    basis_set="6-31G(d)",
    route_parameters={"Opt": None}
)
gin.write_file("input.gjf")

# Quantum ESPRESSO
from pymatgen.io.pwscf import PWInput

pwin = PWInput(struct, control={"calculation": "scf"})
pwin.write_file("pw.in")
```

**参考：** workflow examples 见 `references/io_formats.md`（Electronic Structure Code I/O section）和 `references/transformations_workflows.md`。

### 9. Advanced Analysis

**Diffraction patterns：**
```python
from pymatgen.analysis.diffraction.xrd import XRDCalculator

xrd = XRDCalculator()
pattern = xrd.get_pattern(struct)

# Get peaks
for peak in pattern.hkls:
    print(f"2θ = {peak['2theta']:.2f}°, hkl = {peak['hkl']}")

pattern.plot()
```

**Elastic properties：**
```python
from pymatgen.analysis.elasticity import ElasticTensor

# From elastic tensor matrix
elastic_tensor = ElasticTensor.from_voigt(matrix)

print(f"Bulk modulus: {elastic_tensor.k_voigt:.1f} GPa")
print(f"Shear modulus: {elastic_tensor.g_voigt:.1f} GPa")
print(f"Young's modulus: {elastic_tensor.y_mod:.1f} GPa")
```

**Magnetic ordering：**
```python
from pymatgen.transformations.advanced_transformations import MagOrderingTransformation

# Enumerate magnetic orderings
trans = MagOrderingTransformation({"Fe": 5.0})
mag_structs = trans.apply_transformation(struct, return_ranked_list=True)

# Get lowest energy magnetic structure
lowest_energy_struct = mag_structs[0]['structure']
```

**参考：** 参见 `references/analysis_modules.md`，了解 comprehensive analysis module documentation。

## Bundled Resources

### Scripts (`scripts/`)

用于 common tasks 的 executable Python scripts：

- **`structure_converter.py`**：在 structure file formats 之间转换
  - 支持 batch conversion 和 automatic format detection
  - Usage: `python scripts/structure_converter.py POSCAR structure.cif`

- **`structure_analyzer.py`**：Comprehensive structure analysis
  - Symmetry、coordination、lattice parameters、distance matrix
  - Usage: `python scripts/structure_analyzer.py structure.cif --symmetry --neighbors`

- **`phase_diagram_generator.py`**：从 Materials Project 生成 phase diagrams
  - Stability analysis 和 thermodynamic properties
  - Usage: `python scripts/phase_diagram_generator.py Li-Fe-O --analyze "LiFeO2"`

所有 scripts 都包含详细 help：`python scripts/script_name.py --help`

### References (`references/`)

按需加载到 context 中的 comprehensive documentation：

- **`core_classes.md`**：Element、Structure、Lattice、Molecule、Composition classes
- **`io_formats.md`**：File format support 和 code integration（VASP、Gaussian 等）
- **`analysis_modules.md`**：Phase diagrams、surfaces、electronic structure、symmetry
- **`materials_project_api.md`**：完整 Materials Project API guide
- **`transformations_workflows.md`**：Transformations framework 和 common workflows

当需要特定 modules 或 workflows 的详细信息时，加载 references。

## 常见 Workflows

### High-Throughput Structure Generation

```python
from pymatgen.transformations.standard_transformations import SubstitutionTransformation
from pymatgen.io.vasp.sets import MPRelaxSet

# Generate doped structures
base_struct = Structure.from_file("POSCAR")
dopants = ["Mn", "Co", "Ni", "Cu"]

for dopant in dopants:
    trans = SubstitutionTransformation({"Fe": dopant})
    doped_struct = trans.apply_transformation(base_struct)

    # Generate VASP inputs
    vasp_input = MPRelaxSet(doped_struct)
    vasp_input.write_input(f"./calcs/Fe_{dopant}")
```

### Band Structure Calculation Workflow

```python
# 1. Relaxation
relax = MPRelaxSet(struct)
relax.write_input("./1_relax")

# 2. Static (after relaxation)
relaxed = Structure.from_file("1_relax/CONTCAR")
static = MPStaticSet(relaxed)
static.write_input("./2_static")

# 3. Band structure (non-self-consistent)
nscf = MPNonSCFSet(relaxed, mode="line")
nscf.write_input("./3_bandstructure")

# 4. Analysis
from pymatgen.io.vasp import Vasprun
vasprun = Vasprun("3_bandstructure/vasprun.xml")
bs = vasprun.get_band_structure()
bs.get_band_gap()
```

### Surface Energy Calculation

```python
# 1. Get bulk energy
bulk_vasprun = Vasprun("bulk/vasprun.xml")
bulk_E_per_atom = bulk_vasprun.final_energy / len(bulk)

# 2. Generate and calculate slabs
slabgen = SlabGenerator(bulk, (1,1,1), 10, 15)
slab = slabgen.get_slabs()[0]

MPRelaxSet(slab).write_input("./slab_calc")

# 3. Calculate surface energy (after calculation)
slab_vasprun = Vasprun("slab_calc/vasprun.xml")
E_surf = (slab_vasprun.final_energy - len(slab) * bulk_E_per_atom) / (2 * slab.surface_area)
E_surf *= 16.021766  # Convert eV/Ų to J/m²
```

**更多 workflows：** 参见 `references/transformations_workflows.md`，了解 10 个详细 workflow examples。

## Best Practices

### Structure Handling

1. **使用 automatic format detection**：`Structure.from_file()` 处理大多数 formats
2. **优先使用 immutable structures**：当 structure 不应改变时使用 `IStructure`
3. **检查 symmetry**：使用 `SpacegroupAnalyzer` 规约到 primitive cell
4. **验证 structures**：检查 overlapping atoms 或不合理 bond lengths

### File I/O

1. **使用 convenience methods**：优先使用 `from_file()` 和 `to()`
2. **显式指定 formats**：当 automatic detection 失败时
3. **处理 exceptions**：用 try-except blocks 包裹 file I/O
4. **使用 serialization**：用 `as_dict()`/`from_dict()` 进行 version-safe storage

### Materials Project API

1. **使用 context manager**：始终使用 `with MPRester() as mpr:`
2. **Batch queries**：一次请求多个 items
3. **Cache results**：将 frequently used data 保存到本地
4. **Filter effectively**：使用 property filters 减少 data transfer

### Computational Workflows

1. **使用 input sets**：优先使用 `MPRelaxSet`、`MPStaticSet`，而不是手写 INCAR
2. **检查 convergence**：始终验证 calculations 已 converged
3. **Track transformations**：使用 `TransformedStructure` 记录 provenance
4. **Organize calculations**：使用清晰 directory structures

### Performance

1. **Reduce symmetry**：尽可能使用 primitive cells
2. **Limit neighbor searches**：指定合理 cutoff radii
3. **Use appropriate methods**：不同 analysis tools 有不同 speed/accuracy tradeoffs
4. **Parallelize when possible**：许多 operations 可并行化

## Units and Conventions

Pymatgen 全程使用 atomic units：
- **Lengths**：Angstroms（Å）
- **Energies**：Electronvolts（eV）
- **Angles**：Degrees（°）
- **Magnetic moments**：Bohr magnetons（μB）
- **Time**：Femtoseconds（fs）

需要时使用 `pymatgen.core.units` 转换 units。

## 与其他 Tools 的集成

Pymatgen 可与以下工具无缝集成：
- **ASE** (Atomic Simulation Environment)
- **Phonopy** (phonon calculations)
- **BoltzTraP** (transport properties)
- **Atomate/Fireworks** (workflow management)
- **AiiDA** (provenance tracking)
- **Zeo++** (pore analysis)
- **OpenBabel** (molecule conversion)

## Troubleshooting

**Import errors**：安装缺失 dependencies
```bash
uv pip install pymatgen[analysis,vis]
```

**API key not found**：设置 MP_API_KEY environment variable
```bash
export MP_API_KEY="your_key_here"
```

**Structure read failures**：检查 file format 和 syntax
```python
# Try explicit format specification
struct = Structure.from_file("file.txt", fmt="cif")
```

**Symmetry analysis fails**：Structure 可能存在 numerical precision issues
```python
# Increase tolerance
from pymatgen.symmetry.analyzer import SpacegroupAnalyzer
sga = SpacegroupAnalyzer(struct, symprec=0.1)
```

## 其他资源

- **Documentation**：https://pymatgen.org/
- **Materials Project**：https://materialsproject.org/
- **GitHub**：https://github.com/materialsproject/pymatgen
- **Forum**：https://matsci.org/
- **Example notebooks**：https://matgenb.materialsvirtuallab.org/

## Version Notes

此 skill 面向 pymatgen 2024.x 及以后版本设计。对于 Materials Project API，使用 `mp-api` package（与 legacy `pymatgen.ext.matproj` 分离）。

Requirements：
- Python 3.10 or higher
- pymatgen >= 2023.x
- mp-api (for Materials Project access)
