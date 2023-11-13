---
title: MkDocs 基础语法
subtitle: 
description: 梳理 Markdown 中通用的基础语法， 并增加 MkDocs 中部分增强语法，作为 markdown 文档编写的参考。
status: 
tags: 
    - Markdown
    - MkDocs
---

# MkDocs 基础语法

Markdown 是一种轻量级标记语言，它允许人们使用易读易写的纯文本格式编写文档，然后转换为对应的 HTML以及其他更适合线上传播的格式。

Markdown 的主要特点包括：

* 易读性：Markdown 的语法简洁明了，即使在没有任何格式化的情况下，也能够使文档保持可读性。
* 易写性：Markdown 的语法非常简单，学习曲线平缓，使得编写文档变得更加轻松。
* 易转性：Markdown 文档可以轻松地转换为 HTML、PDF 或其他格式，使其具有很高的可用性。

Markdown 已经在大多数的线上编辑器中得到了良好的支持，大多数语法可以不加修改的在各种编辑器中通用。

而 MkDocs 是一个基于 Markdonw 文档、可以快速且完全可定制的静态站点生成器，它的主要用途是用于构建线上项目文档。

Material for MkDocs 是 MkDocs 的一个美化加强版本，它为 MkDocs 提供了一个美观且响应式的界面，以及丰富多样的 Markdown 加强语法。

本文介绍的基础语法，主要是 Markdown 的通用语法，以及少数 Material for MkDocs 中的特有语法。关于 Material for MkDocs 加强语法的详细说明，请参见 [MkDocs加强语法](mkdocsadvanced.md)。

## 标题

写文档，最高境界就是能做到层级分明结构清晰。合理使用标题，是构建清晰的金字塔结构的不二法门。

以下是从实践中总结出来的标题用法，自认为很适合中文文档的书写，欢迎大家参考使用：

* H1，用来做文章输出时候的大标题
* H2，划分文档的主要层级，和中文的编号一、二、三 …… 配合使用
* H3，作为次级层级标识使用，和数字编号 1、2、3 …… 配合使用
* H4~H6，展示的区分度不高，尽量避免使用

## 字体

Markdown 中也支持对文字进行单独的格式化，和 Word 中的常见格式保持一致。

```Markdown title="字体风格"
**强调，加粗**
*解释，斜体*
~~删除，划线~~
^^专有名词，下划线^^
==突出，高亮==
```

* **强调，用于强调正文中需要注意的内容。**
* *解释，用于标注需要注意的解释性内容。*
* ~~删除，用于标注删除或者完成的内容。~~
* ^^专有名词，下划线^^
* ==突出，高亮==

## 链接

Markdown 是发源于互联网的原生标记语言，因此天然对链接就有完备的支持。不仅支持线上的 HTTP 链接，也能支持本地的绝对路径和相对路径。

从本质上说，一个 Markdown 文档其实对应的就是一个 HTML 文档，所以这么理解起来是不是觉得支持本地路径也是理所当然的事了？

```Markdown title="链接"
<http://zhuanlan.zhihu.com/yunying/20281645>
[App Store 审核指南中英文对照版](http://zhuanlan.zhihu.com/yunying/20281645)
```

需要给阅读者提供快速访问方式的链接，直接以左右尖括号包围链接即可，如: <http://zhuanlan.zhihu.com/yunying/20281645>

如果想有文字链的需求，则可以使用方括号包围显示文字，后跟圆括号包围的链接，如: [App Store 审核指南中英文对照版](http://zhuanlan.zhihu.com/yunying/20281645)

对于特别长的链接，或者包含中文会生成转义符的链接，为了保障正文部分的干净清爽，也可以采用文尾统一赋值的方式来实现链接效果。需要注意的是，在进行赋值的时候需要在文字和链接部分添加 `:` 。

```Markdown title="链接"
[App Store 审核指南中英文对照版]

[App Store 审核指南中英文对照版]:(http://zhuanlan.zhihu.com/yunying/20281645)
```

在 MkDocs 中，链接的语法也得到了一些增加，例如通过在链接的最后添加 `"说明文本"`，可以在鼠标悬停的时候显示一个 Tips，进一步对链接进行说明。

```Markdown title="链接说明"
[App Store 审核指南中英文对照版](http://zhuanlan.zhihu.com/yunying/20281645 "苹果规则变化比较频繁，请注意持续关注")
```

[App Store 审核指南中英文对照版](http://zhuanlan.zhihu.com/yunying/20281645 "苹果规则变化比较频繁，请注意持续关注")

## 图片

由于 Markdown 文件是纯文本文件，因此文档中的图片本质上也就是一个链接。

图片的语法和链接的语法基本一样，唯一的差别就在最前面增加了 `!` 这个符号。这个符号的作用是告诉解析器，这是一个图片链接，需要将其渲染为图片。

![](../../media/img/20231110155240.png)

## 引用

引用可以将他人的观点或言论以差异性的方式呈现出来，语法也很简单，在原文前使用 `>` 开头即可：

```Markdown title="引用"
> 引用原文
```

> 感谢你参与到 iOS 的开发。虽然此文档是一份 “禁止事宜” 的列表，但也请将那份短得多的 “必做事宜” 列表牢记于心。最重要的是，用我们共同的努力让用户感到惊奇和欣喜，用创新方式向他们展示世界，让他们用前所未有的方式与之互动。 <br>根据我们的经验，无论是应用功能还是用户界面，用户确实会对精良的应用有所回应。让我们更进一步，给他们超越预期的东西，带他们去从未去过的地方。我们时刻准备着提供帮助。

## 列表

列表的合理化使用，是将文档结构化的另一个重要手段。使用时建议遵守以下原则：

* 相互之间是次序关系，或者存在重要级差异，优先使用有序列表。
* 相互之间是平行关系，或者差异性不大，优先使用无序列表。

有序列表的创建方式是在行首使用 `阿拉伯数字` ，后跟一个 `.` ，再加上一个半角空格，如果有多个层级，则用空格进行缩进。具体语法如下：

```Markdown title="有序列表"
1. 第一个项目
    1. 准备
    2. 策划
2. 第二个项目
    1. 准备
    2. 策划
    3. 执行
4. 第三个项目
```

其中，数字是否递增并不重要，解析时会自动按照递次数字顺序递增，同时根据层级关系自动调整编号的类型。例如，上述 Markdown 文本的最终显示的效果如下：

1. 第一个项目
    1. 准备
    2. 策划
2. 第二个项目
    1. 准备
    2. 策划
    3. 执行
3. 第三个项目
    1. 测试

无序列表的创建方式则是在行首使用 `*` ，后跟一个空格， 语法如下：

```Markdown  title="无序列表"
* I love Apple
  + I love iPhone
    - And I love Mac
* I love Markdown
  + And I use VSCode
```

* I love Apple
  + I love iPhone
    - And I love Mac
* I love Markdown
  + And I use VSCode

## 待办

打工人永远有干不完的活，永远有勾不完的待办事项。Markdown 语法能完美支持待办事项，让你找不到任何偷懒划水的理由。

```markdown title="待办事项"
* [ ] 永远干不完的活
    - [ ] 永远可以提升的效率
    - [X] ~~*永远不够用的薪水*~~ [2021-12-24]
```

* [ ] 永远干不完的活
  + [ ] 永远可以提升的效率
  + [x] ~~_永远不够用的薪水_~~ [2021-03-11]

## 代码

在技术类文档中，代码块是必不可少的。Markdown 中的代码块语法非常简单，只需要在代码块前后各加上三个反引号 ``` 即可。

```Python title="代码块"
    ```Python title="代码块"
    def getkey(user_file):
        '''清理非标准化的微博地址，提取用户的 UID 或者个性化域名'''
        url_key_list = []
        listnum = 0
        with open(user_file, 'r') as url_list:
            for url in url_list:
                listnum += 1
                try:
                    keyword = re.search(r'\/(\d{10})|com\/(\w{4,32})|\/p\/\d{6}(\d{10})|^(\d{5,10})$', url).groups()
                    url_key_list.append([key for key in keyword if key is not None][0])
                except AttributeError:
                    print('第 %d 行格式有误：' % listnum, url)
            if listnum != len(url_key_list):
                unuseful = listnum - len(url_key_list)
                print('\n注意：总计发现%d个错误格式，请修正后再执行' % unuseful)
                sys.exit()
        return url_key_list
    ```
```

除了大块成段的引用之外， 还可以在行内进行引用。

```Markdown title="行内引用"
在行内使用`引用`语法，可以起到比加粗更引人注意的强调效果。
```

在行内使用 `引用` 语法，可以起到比加粗更引人注意的强调效果。

## 表格

EXCEL 是每个打工人爱与恨永恒的根源之一。在 Markdown 基础语法中，这份爱与恨也比较简单，只能满足简单的纯展示型需求。

表格语法的注意事项和展示效果如下：

* 表头属性下方，必须有 `----` 的分隔行
* 列的对齐方式可以通过在分割线前后添加 `:` 来实现。

```Markdown
| 表头属性 1 | 表头属性 3 | 表头属性 2 |
| :--------: | ---------: | :--------: |
|   左对齐   |     右对齐 |    居中    |
|   左对齐   |          ^ |    居中    |
|   左对齐   |   向上合并 |  向右合并  |
```

| 表头属性 1 | 表头属性 2 | 表头属性 3 |
| :--------- | :--------: | ---------: |
| 左对齐     |    居中    |     右对齐 |
| 左对齐     |    居中    |     右对齐 |
| 左对齐     |    居中    |     右对齐 |


## 角标

Markdown 里面还可以便捷支持上标、下标格式，能够满足科学符号的基本使用需求。

相关的语法和效果如下：

```markdown
* 30^th^
* INFINITI^@^
* H~2~O
```

* 30^th^
* INFINITI^@^
* H~2~O

## 公式

MkDocs 中对于 [数学符号](https://squidfunk.github.io/mkdocs-material/reference/math/#katex-mkdocsyml) 的支持也很完备，可以在网页中实现全面和完美的展现。

行内模式式使用 `$...$` ，即可在文本之间插入公式；而如果要在单独的一行里使用，则需要使用标示符 `$$...$$` 。

具体的符号的使用参见 [整理 Markdown 公式编辑常用数学符号](https://www.cnblogs.com/ywsun/p/14271547.html)，在这里仅做一下简单但酷酷的展示 ${}_1^2\!X_3^4$。

```markdown title="数学公式"
$$
f(x) = \int_{-\infty}^\infty \hat f(\xi)\,e^{2 \pi \xi x} \,d\xi
$$
```

$$
f(x) = \int_{-\infty}^\infty \hat f(\xi)\,e^{2 \pi \xi x} \,d\xi
$$

## 脚注

[脚注](https://squidfunk.github.io/mkdocs-material/reference/footnotes/) 是一种很有用的功能，可以用来在文档中添加一些额外的说明，但又不会打断正文的阅读体验。

```markdown
- Content [^1]

[^1]: 嗨！这是一个孤独的脚注
```

* This the real Content [^1]

[^1]: 嗨！这是一个孤独的脚注

## 缩写

[缩写](https://squidfunk.github.io/mkdocs-material/reference/tooltips/#adding-abbreviations) 同样可以用来在文档中添加一些额外的说明。和脚注相比缩写是一种全局的说明，可以在一个文件中汇总管理。

```markdown
The HTML specification is maintained by the W3C.

*[HTML]: Hyper Text Markup Language
*[W3C]: World Wide Web Consortium
```

* The HTML specification is maintained by the W3C.

*[HTML]: Hyper Text Markup Language
*[W3C]: World Wide Web Consortium

## 分隔

某些时候，为了更好的分割内容，可以使用三个或者更多个短横线 `-` 来生成一条分隔线。

虽然我个人不太喜欢在文档中使用这样的分隔方式，但毕竟是原生的语法，还是在这里提一下：

```Markdown title="分隔线"
---
```

## 换行

上面提到过，Markdown 文档本质上对应的是一个 HTML 文件，因此其实可以通过直接嵌入 HTML 代码的方式直接对文档进行各种格式化操作。

在 MkDocs 中，有部分的独有样式是通过这样的方式实现的。最简单的应用就是换行符 `<br/>` ，如果觉得两段之间的正常间隔高度不够，可以直接在文档中用 `<br>` 换行符来增加一个空行。

<br/>

本段和上段之间的距离，就比正常的段落之间要多出了一个空行，这个小技巧也可以用在文档的任何位置中。<br/> (比如这里的换行就是在一段文字中间添加了一个换行代码)

## 注释

和换行类似，Markdown 的备注功能也是通过 HTML 的注释代码来实现的。

```Markdown
<!-- 这个里面是隐藏的备注文字 -->
```

在个人配置中，任务管理的方式使用了注释的方式来变通实现，详细的配置说明参见 [VS Code 任务管理](../vscode/vscode任务管理.md)。
