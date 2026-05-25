---
name: image-enhancer
description: 通过提升分辨率、锐度和清晰度来改善图像质量，尤其适合 screenshots。非常适合为 presentations、documentation 或 social media posts 准备图片。
---

# 图像增强器

此 skill 会让你的图片和 screenshots 看起来更好——更锐利、更清晰、更专业。

## 何时使用此 Skill

- 为 blog posts 或 documentation 改善 screenshot 质量
- 在 social media 分享前增强图片
- 为 presentations 或 reports 准备图片
- 放大低分辨率图片
- 锐化模糊照片
- 清理被压缩过的图片

## 此 Skill 做什么

1. **分析图像质量**：检查分辨率、锐度和压缩伪影
2. **增强分辨率**：智能放大图片
3. **提升锐度**：增强边缘和细节
4. **减少伪影**：清理压缩伪影和噪点
5. **按使用场景优化**：根据预期用途（web、print、social media）调整

## 如何使用

### 基础增强

```
Improve the image quality of screenshot.png
```

```
Enhance all images in this folder
```

### 特定改进

```
Upscale this image to 4K resolution
```

```
Sharpen this blurry screenshot
```

```
Reduce compression artifacts in this image
```

### 批量处理

```
Improve the quality of all PNG files in this directory
```

## 示例

**User**: "Improve the image quality of screenshot-2024.png"

**Output**:
```
Analyzing screenshot-2024.png...

Current specs:
- Resolution: 1920x1080
- Format: PNG
- Quality: Good, but slight blur

Enhancements applied:
✓ Upscaled to 2560x1440 (retina)
✓ Sharpened edges
✓ Enhanced text clarity
✓ Optimized file size

Saved as: screenshot-2024-enhanced.png
Original preserved as: screenshot-2024-original.png
```

**灵感来源：** Lenny Rachitsky 在其 newsletter 中的 workflow - 用于文章里的 screenshots

## 提示

- 始终保留原始文件作为备份
- 最适合 screenshots 和数字图片
- 可以批量处理整个 folders
- 如有需要请指定输出格式（PNG 质量更高，JPG 体积更小）
- 用于 social media 时，请说明平台以获得最佳尺寸

## 常见用例

- **Blog Posts**：发布前增强 screenshots
- **Documentation**：让 UI screenshots 清晰锐利
- **Social Media**：为 Twitter、LinkedIn、Instagram 优化图片
- **Presentations**：为大屏幕放大图片
- **Print Materials**：为实体媒介提升分辨率
