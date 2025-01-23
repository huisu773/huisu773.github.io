---
date: '2025-01-23'
draft: false
title: '使用 honkit 将 Markdown 文件转换成 pdf/epub 电子书'
categories: [Tool]
tags: [Tool,honkit,文字]
---

## **起因**

在 Github 上有许多电子书是以 Markdown 文件形式编写的，它们通常是由若干个文件夹包括若干个 md 文件构成的。这种 Repo 可以使用 GitBook 构建成网页，可供在线浏览。我想将这些文件转换成 epub 格式并导入到自己的阅读器中阅读，以便更方便地管理注释。

在网页上查询后发现 gitbook 有[命令行](https://github.com/GitbookIO/gitbook)版本，可以生成 html/pdf/epub。下载之后发现初始化的时候会报错：

```bash
Installing GitBook 3.2.3/opt/homebrew/lib/node_modules/gitbook-cli/node_modules/npm/node_modules/graceful-fs/polyfills.js:287      if (cb) cb.apply(this, arguments)                 ^TypeError: cb.apply is not a function    at /opt/homebrew/lib/node_modules/gitbook-cli/node_modules/npm/node_modules/graceful-fs/polyfills.js:287:18    at FSReqCallback.oncomplete (node:fs:192:5)Node.js v19.7.0
```

查了一下报错，发现是 gitbook 命令行的依赖版本太老了，而且 gitbook 命令行已经不再开发更新。在 Stack Overflow 上发现有人推荐了 [honkit](https://github.com/honkit/honkit)，一个 gitbook 的 fork。

## **流程**

### **安装 honkit**

在使用 honkit 之前，需要先安装 Node.js。

安装 honkit：

```bash
npm init --yes$ npm install honkit --save-dev
```

### **安装 Calibre**

下载 [Calibre](https://calibre-ebook.com/download) 并安装。

Windows 下需要将 Calibre 安装路径添加到环境变量。

Mac 下需要使用如下命令：

```bash
sudo ln -s /Applications/calibre.app/Contents/MacOS/ebook-convert /usr/local/bin
```

### **转换：**

在文件夹内初始化：

```bash
npx honkit init
```

会生成如下形式的文件结构：

```bash
.
├── files
├── README.md
└── SUMMARY.md
```

其中，`README.md` 文件包含书籍的前言或介绍信息，`SUMMARY.md` 文件则包含书籍的内容目录。

接下来，可以根据书籍的内容编写目录。假设该书的内容结构如下：

```bash
.
├── ch1
│   ├── ch1.1.md
│   └── ch1.2.md
└── ch2
    └── ch2.1.md
```

`SUMMARY.md`的内容应该是

```bash
# Summary

### ch1

* [ch1](ch1/ch1.1.md)
* [ch1](ch1/ch1.2.md)

### ch2

* [ch2](ch2/ch2.1.md)
```

如果书籍内容较多，可以使用 ChatGPT 来加速目录文件的构建。使用 `tree` 命令获取文件结构，将目录要求和文件结构发送给 ChatGPT，就可以生成目录文件了。

如果需要自定义书籍元信息，需要在当前文件夹下新建 `book.json` 文件。

以下是一个示例：

```json
{
	"root": "./",
	"title": "xxx",
	"author": "xxx"
}
```

更多自定义选项可以参考[官方文档](https://honkit.netlify.app/config.html)。

在我的经验中，如果在元数据中使用中文可能会出现一些问题。因此，我建议使用默认设置生成电子书，并将电子书导入到 Calibre 中编辑元数据。编辑完成后，转换书籍即可应用元数据。这样更为直观和简单。

如果想要添加封面，可以在目录下添加 `cover.jpg` 文件。

设置完成后，即可构建电子书。命令如下：

```bash
npx honkit build
npx honkit pdf
npx honkit epub
```

这样可以生成 html/pdf/epub 文件了。

### **Docker 使用**

我更推荐直接使用 Docker 版本，更加方便，只需在目录下执行命令即可。

```bash
docker pull honkit/honkit
docker run -v `pwd`:`pwd` -w `pwd` --rm -it honkit/honkit honkit build
docker run -v `pwd`:`pwd` -w `pwd` --rm -it honkit/honkit honkit pdf
docker run -v `pwd`:`pwd` -w `pwd` --rm -it honkit/honkit honkit epub
```

## **其他**

这个方法也可以用来把一些网页专栏制作成 epub 电子书。流程是先用 简悦 将网页转换成 Markdown 文件并保存，然后再用 Honkit 将其转换成 epub，这样就可以导入到 Apple Books/Readwise Reader 等阅读器中查看并管理标注。
