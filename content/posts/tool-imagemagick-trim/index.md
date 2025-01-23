---
date: '2025-01-23'
draft: false
title: '使用 ImageMagick 批量裁剪图片白边'
categories: [Tool]
tags: [Tool,ImageMagick,图片]
---

MacOS 安装：

```bash
brew install imagemagick
```

命令行使用：

```bash
magick convert 1.png -trim 1.png
```

Python 批量裁剪脚本：

```python
import os

for filename in os.listdir("./"):
    if filename.endswith(".png"):
        # run trim command
        os.system(f"magick convert {filename} -trim {filename}")
```
