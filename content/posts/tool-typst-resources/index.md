---
date: '2025-01-23'
draft: false
title: 'Typst 相关资源'
categories: [Tool]
tags: [Tool,Typst,文字]
---

Typst是一个Latex的替代品，相比Latex的最大优势是简洁快速。比较适合一些输出pdf的写作场景，如一些作业、文档和slides。

以下一些最近使用过程中有用的资源，涉及文档、CV模版、Slides模版格式转换。

### 文档

[Typst Documents](https://typst.app/docs/tutorial/writing-in-typst/)

[中文文档](https://typst-doc-cn.github.io/docs/)

[中文用户指南](https://typst-doc-cn.github.io/docs/chinese/)

### CV 模版

个人比较喜欢的CV模版。

[Typst CV Template](https://github.com/LaurenzV/simplecv/tree/main)

### Slides 模版

[Typst Slides Template](https://github.com/glambrechts/slydst)

我个人比较喜欢的一套Slides模版，只需要在文档的开头加上一段内容就能讲一个文档转换成PPT，样式也比较美观，如果内容过长还支持自动分页，比之前使用的Marp（Markdown 转PPT）好用一些。

```rust
#import "@preview/slydst:0.1.0": *

// <https://github.com/glambrechts/slydst>

#show: slides.with(
  title: "title", // Required
  subtitle: none,
  date: none,
  authors: (),
  layout: "small",
  ratio: 16/9,
  title-color: none,
)

```

### Typst to markdown

Typst自己定义了一套公式语法，与传统的Latex公式语法不兼容，但是使用Pandoc能够将Typst公式转换为Latex公式，还可以同时将文档排版转换成Markdown或Latex，参考：

- [pandoc 文档](https://pandoc.org/MANUAL.html)
- `pandoc -f typst -t latex main.typ -o main.tex`
- `pandoc -f typst -t markdown main.typ -o main.md`

### 字体

Typst默认的英文字体是Linux Libertine，我很喜欢这套字体。但是中文默认是黑体，想要设置为宋体可以使用字体选择的fallback机制，在文档中使用如下命令：

`#set text(font: ("Linux Libertine", "Songti SC"))`

### VS Code 扩展

我平时主要在VS Code上写Typst，主要是用如下的扩展：

- Tinymist Typst: 支持语法高亮、自动编译生成pdf
- Typst Companion: 支持自动添加成对符号，如括号等

