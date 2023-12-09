---
author: "Yuchao"
date: 2023-12-09
linktitle: Typora修改字体样式
menu:
  main:
    parent: tutorials
next: /tutorials/github-pages-blog
prev: /tutorials/automated-deployments
title: Typora修改字体样式
weight: 10
---

# Typora修改字体样式（含代码块中的字体）

## 1. 修改页面文字体显示

**偏好设置 →外观**，找到主题一栏，打开主题文件夹，选择你当前主题下的**.CSS**文件。如我使用的是github主题，则我打开github.css文件。

找到以下代码，将你想用的字体放在**font-family**的第一个位置。如我使用的就是**华康手札体W5P**。同样你可以换成微软雅黑、华文行楷等字体（看个人喜好）。自己系统里存的字体可以在**C:\Windows\Fonts**下看，选择自己喜欢的字体。

```html
body {
    font-family: "华康手札体W5P","Clear Sans", "Helvetica Neue", Helvetica, Arial, 'Segoe UI Emoji', sans-serif;
    color: rgb(51, 51, 51);
    line-height: 1.6;
}
```

## 2. 代码块文字体修改

上述字体样式的修改只会修改正常页面下的字体样式，并不会改变代码块中的字体。代码块中的字体样式的修改，同样在对应主题文件夹下的**.CSS**文件中。找到以下代码，在原代码中加入**font-family**设置，如下所示。

```html
# 复制如下命令进.css文件中，font-family为你在代码块中想用的字体
.CodeMirror-wrap .CodeMirror-code pre {	
	font-family: "华康手札体W5P", "JetBrains Mono", "Microsoft YaHei"
}
```



```html
# 在以下代码中加入font-family属性
.md-fences,
code,
tt {
    border: 1px solid #e7eaed;
    background-color: #f8f8f8;
    border-radius: 3px;
    padding: 0;
    padding: 2px 4px 0px 4px;
    font-size: 0.9em;
    font-family: "华康手札体W5P"
}
```

上述修改完成后重启Typora，字体样式就修改好了。
