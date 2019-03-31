# pandoc模板

## 快速开始
以`windows 10`为例，演示如何使用。

### 安装软件

- 下载[msys2](https://www.msys2.org/) 并安装
- 下载[texlive](http://mirror.ctan.org/systems/texlive/Images/) 2018或以上版本并安装
- 下载[pandoc](https://pandoc.org/installing.html) 2.7.1或以上版本并安装

### 下载本项目

打开msys2，假设工作目录为/d/dev

```
$ cd /d/dev
$ git clone https://github.com/annProg/pandoc-template
```

### 设置环境变量
需要将本项目，`texlive`及`pandoc`加入环境变量，编辑`~/.bashrc`，加入以下内容

```
$ tail -n 1 ~/.bashrc
export PATH=$PATH:/d/texlive/2018/bin/win32:/d/dev/pandoc-template:/c/Users/myname/AppData/Local/Pandoc
```

### 开始使用
假设电子书目录为 `/d/dev/mybook`

```
$ cd /d/dev/mybook
$ panbook init                  # 初始化工作环境
$ panbook epub                  # 生成epub电子书
$ panbook pdf                   # 生成pdf电子书
$ panbook html                  # 生成html电子书
$ panbook pdf d                 # 生成pdf电子书(d选项意为debug模式，仅生成一种样式)
$ TPL=elegantbook panbook pdf   #指定模板
```

之后在`src`目录进行写作, `src/images`目录存放图片

## 注意事项
- 在Windows上使用pandoc需要将markdown文件保存为UTF-8格式
- 按章节拆分的多个markdown文件，开头需要空一行，否则pandoc可能不能正确识别标题

## 模板说明
本项目使用了一些开源模板，列表如下

- [ElegantBook](https://github.com/ElegantLaTeX/ElegantBook)

## 演示

使用本项目编译的书籍

- [人人都能用英语 李笑来](https://github.com/annProg/everyone-can-use-english)