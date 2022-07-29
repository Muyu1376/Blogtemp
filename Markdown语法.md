# Markdown语法



## 标题语法

标题语法是使用#，一级标题一个#，二级标题两个#，以此类推、

通常要求在#后添加一个空格之后再写标题



## 段落语法

Markdown的段落即在正文后添加一个空行即可。



## 换行语法

换行语法通常为在文字后添加两个或以上空格之后回车

或者使用`html`语言的`</br> `标签



## 强调语法

**粗体使用两个星号**`*`，`typora`快捷键是**`CTRL+B`**

*斜体使用一个星号*，快捷键是*CTRL+I*

同时使用粗体和斜体***可以使用三个星号***



## 引用语法

创建块引用，在段落前添加一个`>`

> 你好哇

多个段落进行块引用时，在空行添加一个`>`

块引用支持嵌套使用

> >
> >
> >>
> >>
> >>>
> >>>
> >>>>
> >>>>
> >>>>

在块引用中能添加其他元素语法



## 列表语法



### 有序列表

在每个列表项前添加数字并跟一个英文句点。

数字不必按数学顺序排列，但是列表应当以数字 1 起始

1. hello

1. world

1. hi

### 无序列表

添加破折号`-`



要在保留列表连续性的同时在列表中添加另一种元素，请将该元素缩进四个空格或一个制表符

有序列表可以和无序列表嵌套



## 代码语法

将文字显示为代码，需要使用反引号``

typora快捷键为`CTRL+shift+\``

代码块使用使用三个反引号（```）或三个波浪号（~~~）

反引号之后添加语言名称，可以有语法高亮显示

typora代码块快捷键为`ctrl+shift+M`



## 分隔线语法

三个或多个星号 (`***`)、破折号 (`---`) 或下划线 (`___`) ，在分隔线前后添加空行



## 链接语法

`[超链接显示名](超链接地址 "超链接title")`

例如 [暮雨的个人网站](https://muyu1376.xyz "很好的个人网站")

对于直接的网址和邮箱地址，使用尖括号

强调链接, 在链接语法前后增加星号。 

将链接表示为代码，在方括号中添加反引号。

typora快捷键`ctrl+k`

### 引用类型的链接

以下内容出自[Markdown官方教程]([Markdown 链接语法 | Markdown 官方教程](https://markdown.com.cn/basic-syntax/links.html))

**链接第一部分格式**

引用类型的链接的第一部分使用两组括号进行格式设置。第一组方括号包围应显示为链接的文本。第二组括号显示了一个标签，该标签用于指向您存储在文档其他位置的链接。

尽管不是必需的，可以在第一组和第二组括号之间包含一个空格。第二组括号中的标签不区分大小写，可以包含字母，数字，空格或标点符号。

以下示例格式对于链接的第一部分效果相同：

- `[hobbit-hole][1]`
- `[hobbit-hole] [1]`

**链接的第二部分格式**

引用类型链接的第二部分使用以下属性设置格式：

1. 放在括号中的标签，其后紧跟一个冒号和至少一个空格（例如`[label]:`）。
2. 链接的URL，可以选择将其括在尖括号中。
3. 链接的可选标题，可以将其括在双引号，单引号或括号中。

以下示例格式对于链接的第二部分效果相同：

- `[1]: https://en.wikipedia.org/wiki/Hobbit#Lifestyle`
- `[1]: https://en.wikipedia.org/wiki/Hobbit#Lifestyle "Hobbit lifestyles"`
- `[1]: https://en.wikipedia.org/wiki/Hobbit#Lifestyle 'Hobbit lifestyles'`
- `[1]: https://en.wikipedia.org/wiki/Hobbit#Lifestyle (Hobbit lifestyles)`
- `[1]: <https://en.wikipedia.org/wiki/Hobbit#Lifestyle> "Hobbit lifestyles"`
- `[1]: <https://en.wikipedia.org/wiki/Hobbit#Lifestyle> 'Hobbit lifestyles'`
- `[1]: <https://en.wikipedia.org/wiki/Hobbit#Lifestyle> (Hobbit lifestyles)`

可以将链接的第二部分放在Markdown文档中的任何位置。有些人将它们放在出现的段落之后，有些人则将它们放在文档的末尾（例如尾注或脚注）。



## 图片语法

插入图片Markdown语法代码：`![图片alt](图片链接 "图片title")`

给图片增加链接，将图像的Markdown语句 括在方括号中，然后将链接添加在圆括号中。

`[![图片alt](图片链接)](图片附加的链接)`



## 表格语法

使用三个及以上的`---`创建每列标题，使用`|`分割每列

**Tip:** 使用连字符和管道创建表可能很麻烦。为了加快该过程，请尝试使用[Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables)。使用图形界面构建表，然后将生成的Markdown格式的文本复制到文件中。

可以通过在标题行中的连字符的左侧，右侧或两侧添加冒号（`:`），将列中的文本对齐到左侧，右侧或中心。

## 脚注

[^1]: My footnote.



## 删除线

在单词前后使用两个波浪号`~~`



## 任务列表

~~~markdown
- [x] Write the press release
~~~

破折号+空格+方括号

- [x] 学习Markdown
