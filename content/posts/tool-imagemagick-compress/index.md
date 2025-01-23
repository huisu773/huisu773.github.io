---
date: '2025-01-23'
draft: false
title: '使用 ImageMagick 批量压缩图片'
categories: [Tool]
tags: [Tool,ImageMagick,图片]
---

MacOS 安装：

```bash
brew install imagemagick
```
命令行：

```bash
magick input.png -quality 50% output.png
```

Bash 脚本：

```bash
#!/bin/bash

# Check if ImageMagick is installed
if ! command -v magick &> /dev/null
then
    echo "ImageMagick is not installed. Please install it and try again."
    exit 1
fi

# Loop through all jpg files in the current directory
for file in *.JPG
do
    if [ -f "$file" ]; then
        # Compress the image
        magick "$file" -quality 85% "compressed_$file"
        echo "Compressed: $file -> compressed_$file"
    fi
done

echo "Compression complete!"
```