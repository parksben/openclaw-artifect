# openclaw-artifect

OpenClaw 文件产物存储仓库

## 功能

通过 OpenClaw agent 上传的文件会自动存储到这个仓库，并通过 `assets.parksben.xyz` 域名对外提供访问。

## 目录结构

文件按类型自动分类存储：

- `images/` - 图片文件（jpg, png, gif, webp, svg 等）
- `documents/` - 文档文件（pdf, doc, txt, md 等）
- `videos/` - 视频文件（mp4, avi, mov, webm 等）
- `audios/` - 音频文件（mp3, wav, flac 等）
- `archives/` - 压缩文件（zip, tar, gz 等）
- `others/` - 其他类型文件

## 文件命名

所有文件会使用内容的 SHA256 hash 值（前16位）重命名，确保：
- 文件唯一性
- 避免文件名冲突
- 内容去重（相同内容只存储一次）

## 访问方式

文件上传后可通过以下 URL 访问：

```
https://assets.parksben.xyz/{category}/{hash}.{ext}
```

例如：
- `https://assets.parksben.xyz/images/a1b2c3d4e5f6g7h8.png`
- `https://assets.parksben.xyz/documents/1234567890abcdef.pdf`

## 特性

- ✅ Web 支持的文件类型直接渲染（图片、视频、PDF 等）
- ✅ 不支持的文件类型自动下载
- ✅ 长期缓存（1年）
- ✅ CORS 支持

## 使用

在 OpenClaw 中使用 `upload_artifact` 工具上传文件即可。
