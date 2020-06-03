<p align="center">
  <img height="220" src="src/images/logo.png">
</p>

[![Build Status](https://ci.annhe.net/api/badges/annProg/PanBook/status.svg)](https://ci.annhe.net/annProg/PanBook)

## 简介
`PanBook`基于`Pandoc`的`lua filter`功能，适配各种书籍，论文，幻灯片及简历的`LaTeX`或`EPUB`模板。
目标是使用`Pandoc's Markdown`作为写作语言，实现**一次编写 多次生成**。

预览

| Book                                                                              | Article                                                                    | Thesis                                                                                | Slide                                                                       | CV                                                                                  |
| --------------------------------------------------------------------------------- | -------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- | --------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| [ElegantBook](https://panbook.annhe.net/pub/PanBook-book-elegantbook-pc.pdf)      | [ctexart](https://panbook.annhe.net/pub/article-art-ctexart.pdf)           | [Demo Thesis](https://panbook.annhe.net/pub/thesis-thesis-thesis.pdf)                 | [metropolis](https://panbook.annhe.net/pub/beamer-slide-metropolis.pdf)     | [moderncv-classic](https://panbook.annhe.net/pub/cv-cv-moderncv-classic-blue.pdf)   |
|                                                                                   | [elegantnote](https://panbook.annhe.net/pub/article-art-elegantnote.pdf)   | [湖南大学（WIP）](https://panbook.annhe.net/pub/thesis-thesis-hnuthesis.pdf)          | [solarized](https://panbook.annhe.net/pub/beamer-slide-solarized.pdf)       | [resume](https://panbook.annhe.net/pub/cv-cv-resume.pdf)                            |
| [CTeXBook](https://panbook.annhe.net/pub/PanBook-book-ctexbook-pc.pdf)            | [elegantpaper](https://panbook.annhe.net/pub/article-art-elegantpaper.pdf) | [清华大学（WIP）](https://panbook.annhe.net/pub/thesis-thesis-thuthesis.pdf)          | [material](https://panbook.annhe.net/pub/beamer-slide-material.pdf)         | [TMR](https://panbook.annhe.net/pub/cv-cv-tmr.pdf)                                  |
| [CTeXBook-mobile](https://panbook.annhe.net/pub/PanBook-book-ctexbook-mobile.pdf) |                                                                            | [上海交通大学（WIP）](https://panbook.annhe.net/pub/thesis-thesis-sjtuthesis.pdf)     | [Execushares](https://panbook.annhe.net/pub/beamer-slide-Execushares.pdf)   | [moderncv-fancy](https://panbook.annhe.net/pub/cv-cv-moderncv-fancy-blue.pdf)       |
| [Epub](https://panbook.annhe.net/pub/PanBook.epub)                                |                                                                            | [南京大学（WIP）](https://panbook.annhe.net/pub/thesis-thesis-njuthesis.pdf)          | [classyslides](https://panbook.annhe.net/pub/beamer-slide-classyslides.pdf) | [moderncv-banking](https://panbook.annhe.net/pub/cv-cv-moderncv-banking-blue.pdf)   |
|                                                                                   |                                                                            | [山东大学（WIP）](https://panbook.annhe.net/pub/thesis-thesis-sduthesis.pdf)          | [elegance](https://panbook.annhe.net/pub/beamer-slide-elegance.pdf)         | [moderncv-casual](https://panbook.annhe.net/pub/cv-cv-moderncv-casual-blue.pdf)     |
|                                                                                   |                                                                            | [中国科学院大学（WIP）](https://panbook.annhe.net/pub/thesis-thesis-ucasthesis.pdf)   | [Hest](https://panbook.annhe.net/pub/beamer-slide-Hest.pdf)                 | [moderncv-oldstyle](https://panbook.annhe.net/pub/cv-cv-moderncv-oldstyle-blue.pdf) |
|                                                                                   |                                                                            | [电子科技大学（WIP）](https://panbook.annhe.net/pub/thesis-thesis-uestcthesis.pdf)    | [opensuse](https://panbook.annhe.net/pub/beamer-slide-opensuse.pdf)         |                                                                                     |
|                                                                                   |                                                                            | [北京航空航天大学（WIP）](https://panbook.annhe.net/pub/thesis-thesis-buaathesis.pdf) | [Xiaoshan](https://panbook.annhe.net/pub/beamer-slide-Xiaoshan.pdf)         |                                                                                     |
|                                                                                   | [more](https://github.com/annProg/PanBook/tree/master/demo/article)        | [more](https://github.com/annProg/PanBook/tree/master/demo/thesis)                    | [more](https://github.com/annProg/PanBook/tree/master/demo/beamer)          | [more](https://github.com/annProg/PanBook/tree/master/demo/cv)                      |

## 快速开始
以`Windows 10`为例，演示如何使用。首先安装以下依赖软件

- [msys2](https://www.msys2.org/)（ Linux 及 OS X 请忽略此步骤）
- [texlive](http://mirror.ctan.org/systems/texlive/Images/) 2018 或以上版本
- [Pandoc](https://pandoc.org/installing.html) 2.9 或以上版本
- [pandoc-crossref](https://github.com/lierdakil/pandoc-crossref/releases) 对应版本并安装到`path`目录下（建议和`Pandoc`放同一目录，即`/c/Users/yourname/AppData/Local/Pandoc`）

然后下载本项目，打开`msys2`，假设工作目录为`/d/dev`

```
# 首先安装 git，msys2 包管理工具为 pacman
$ pacman -Ss git     # 查询软件包
$ pacman -S git      # 安装软件包
$ cd /d/dev
$ git clone https://github.com/annProg/PanBook
```

### 设置环境变量
需要将本项目，`texlive`及`Pandoc`加入环境变量，编辑`~/.bashrc`，加入以下内容

```
$ tail -n 1 ~/.bashrc
export PATH=$PATH:/d/texlive/2018/bin/win32:/d/dev/PanBook:/c/Users/myname/AppData/Local/Pandoc
```

### 开始使用

```bash
# 新建项目目录
$ mkdir /d/dev/mybook
$ cd /d/dev/mybook
# 生成示例 book 文档，编译结果在 build 目录
$ panbook book
# 查看帮助
$ panbook -h
```
然后编写 `src` 目录下的 `Markdown` 源文件。图片放在 `src/images` 下。

### 紧急情况

如果时间紧迫且 `Panbook` 生成失败时，可以在 `build` 文件夹下使用 `xelatex` 或 `latexmk` 手动编译，可考虑使用 `-interaction=nonstopmode`

## 升级指南

本包的主要升级内容在于 elegantbook.cls 等文件，
- 作用： 在 texlive 升级后保持匹配
- 来源： (elegantbook.cls from github)[https://github.com/ElegantLaTeX/ElegantBook/blob/master/elegantbook.cls] 

### temp patch
#### texlive2020 
报错信息: ! You can't use `\relax' after \the.

```styles/book/elegantbook/elegantbook.cls:88
\usepackage{longtable,booktabs,tabu} % TODO: temp fix for tabu issue
%issue https://github.com/tabu-issues-for-future-maintainer/tabu/issues/24
``` 

## 贡献指南
欢迎提交`Issue`和`Pull Request`。`extensions`, `styles`开发流程请参考 [PanBook 手册](https://panbook.annhe.net/pub/PanBook-book-elegantbook-pc.pdf) 第四章。

## 演示

使用本项目编译的书籍（欢迎加入此列表）

- [PanBook 手册](https://panbook.annhe.net/pub/PanBook-book-elegantbook-pc.pdf)
- [Go by example](https://github.com/pandoc-ebook/gobyexample-zh)

## 免责声明

请仔细阅读本软件 [Licence](https://github.com/annProg/PanBook/blob/master/LICENCE)

本软件不提供任何保证。在任何情况下，版权所有者或贡献者都不承担责任。

因此，当用于正式场合（比如学位论文）时，请您自行评估风险。

## 致谢
`PanBook`适配了一些开源`LaTeX`模板，列表如下：

| Book                                                       | Article                                                      | Thesis | Slide                                                               | CV                                                        |
| ---------------------------------------------------------- | ------------------------------------------------------------ | ------ | ------------------------------------------------------------------- | --------------------------------------------------------- |
| [ElegantBook](https://github.com/ElegantLaTeX/ElegantBook) | [ElegantNote](https://github.com/ElegantLaTeX/ElegantNote)   |        |                                                                     | [moderncv](https://github.com/xdanaux/moderncv)           |
|                                                            | [ElegantPaper](https://github.com/ElegantLaTeX/ElegantPaper) |        | [more](https://github.com/annProg/PanBook/tree/master/styles/slide) | [resume](https://github.com/billryan/resume)              |
|                                                            |                                                              |        |                                                                     | [tmr](https://github.com/TheMartianLife/TheMartianResume) |
