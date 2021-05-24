# syntax for markdown

## 标题

### 可选语法

还可以在文本下方添加任意数量的 == 号来标识一级标题，或者 -- 号来标识二级标题。

e,g.

<!--

Heading level 1
=====

Heading level 2
------ 

-->

这也是为什么

`MD022 - Headings should be surrounded by blank lines`
（标题的上下行必须都是空格）

另外，有 `MD001： 标题等级需要递增`。

### 注意

不同的 Markdown 应用程序处理 # 和标题之间的空格方式并不一致。为了兼容考虑，请用一个空格在 # 和标题之间进行分隔。

即 `MD018 : one space after heading`

### 自定义标题ID {#1}

许多Markdown处理器支持标题的自定义ID , 一些Markdown处理器会自动添加它们。添加自定义ID允许您直接链接到标题并使用CSS对其进行修改。  

要添加自定义标题ID，请在与标题相同的行上用大括号括起该自定义ID。

#### 链接到标题ID (#head_id)

。。。。。。  
不过上述功能均不支持，甭看了。

## 段落

要创建段落，请使用空白行将一行或多行文本进行分隔

### 建议

不要用空格或者制表符缩进段落 （暂时不知道为啥

## 换行

在一行的末尾添加两个或多个空格，然后按回车键,即可创建一个换行(`<br>`)。

所以 `MD009: No trailing space` , 即行尾要么两空格表示换行要么就别空，否则会产生歧义。  
我通过行尾双空格换行了\
反斜杠也能换行
直接回车换不了行

使用 `<br>` HTML标签也能换行，但这不符合规范 `MD033: No inline html`.

## 强调

### 粗体（Bold）

粗文本，请在单词或短语的前后各添加两个星号（asterisks）或下划线（underscores）。如需加粗一个单词或短语的中间部分用以表示强调的话，请在要加粗部分的两侧各添加两个星号（asterisks）。

e.g.

**星号加粗**  
__下划线加粗__

`MD037: No space in emphasis`.

Markdown 应用程序在如何处理单词或短语中间部分时使用下划线有时无效，所以为了兼容性考虑，一律采用 `**` .

Leo**Nardoo**

### 斜体（Italic）

要用斜体显示文本，请在单词或短语前后添加一个星号（asterisk）或下划线（underscore）。要斜体突出单词的中间部分，请在字母前后各添加一个星号，中间不要带空格。

e.g.

这是 *星号斜体*

这是 _下划线斜体_

我不斜_我斜_  

我不斜*我斜*

可见为兼容性考虑，仍采用 `*`。

***另外，三个星号表示我又粗又斜***

## 引用

要创建块引用，请在段落前添加一个 > 符号。

>我是一段话

块引用可以包含多个段落。为段落之间的空白行添加一个 > 符号。

>我是第一段
>
>我是第三段

块引用可以嵌套。在要嵌套的段落前添加一个 >> 符号。

>我是外层块引用
>>我是内层块引用
>>>套，就硬套

### 带有其它元素的块引用

块引用可以包含其他 Markdown 格式的元素。并非所有元素都可以使用，你需要进行实验以查看哪些元素有效。

> #### 标题可以
>
> -列表也可以  
> ***粗斜体也行***

## 列表

可以将多个条目组织成有序或无序列表。

### 有序列表

要创建有序列表，请在每个列表项前添加数字并紧跟一个英文句点。数字不必按数学顺序排列，但是列表应当以数字 1 起始。

1. First item
2. Second item
3. Third item
    1. Indented item
    2. Indented item
4. Fourth item

<!-- 

1. First item
1. Second item
1. Third item
1. Fourth item 

-->

`MD029 - Ordered list item prefix`  
有序列表的前缀序号格式必须只用1或者从1开始的加1递增数字.  
实际上就算瞎写，md也只会按照顺序输出，∴只是规范。

### 无序列表

要创建无序列表，请在每个列表项前面添加破折号 (-)、星号 (*) 或加号 (+) 。缩进一个或多个列表项可创建嵌套列表。

- First item
- Second item
  - 2.5
  - 2.99
    - 2.99999
      - 2.999999999999
- Third item
- Fourth item
  
<!-- 
* First item
* Second item
* Third item
* Fourth item

+ First item
+ Second item
+ Third item
+ Fourth item 

-->

`MD004/ul-style: Unordered list style [Expected: dash; Actual: asterisk,plus]`

另，  
`MD032/blanks-around-lists: Lists should be surrounded by blank lines`

`MD030/list-marker-space: Spaces after list markers [Expected: 1; Actual: 3]`

所以，应只使用 `-` 来表示无序列表，其后紧跟一个空格，且周围像标题一样环绕空行

### 在列表中嵌套其他元素

要在保留列表连续性的同时在列表中添加另一种元素，请将该元素缩进四个空格或一个制表符，

#### 列表中嵌套段落

- This is the first list item.
- Here's the second list item.

    I need to add another paragraph below the second list item.

- And here's the third list item.

#### 列表中嵌套引用

- This is the first list item.
- Here's the second list item.

    > A blockquote would look great below the second list item.

- And here's the third list item.

##### 列表中嵌套代码块

代码块通常采用四个空格或一个制表符缩进。当它们被放在列表中时，请将它们缩进八个空格或两个制表符。

e.g.  

1. Open the file.
2. Find the following code block on line 21:

        <html>
          <head>
            <title>Test</title>
          </head>

3. Update the title to match the name of your website.

#### 列表中嵌套图片

1. Open the file containing the Linux mascot.
2. Marvel at its beauty.

    ![LoL](lol.jpg "英雄联盟")

3. Close the file.

#### 列表套列表

You can nest an unordered list in an ordered list, or vice versa.

1. First item
2. Second item
3. Third item
    - Indented item
    - Indented item
4. Fourth item

#### 列表中不能嵌套标题

∵ `MD023/heading-start-left/header-start-left: Headings must start at the beginning of the line`
∴

### 任务列表

创建带有复选框的项目列表。  
在任务列表项之前添加破折号（-）和方括号，并[ ]在其前面加上空格。要选择一个复选框，请在方括号（[ ]）之间添加 `x`  。

e.g.

- [x] Study Markdown's Syntax
- [ ] Write English paper
- [ ] Practice body by running
- [ ] quit Internet addiction

### 定义描述列表

一些Markdown处理器允许您创建术语及其对应定义的定义列表。  

即HTML中  

- `<dl>` 描述列表
- `<dt>` 要描述的术语
- `<dd>` 描述内容
  
e.g.
<h1>Sample Description List</h1>
<dl>
    <dt>TCP</dt>
    <dd>TCP（Transmission Control Protocol 传输控制协议）是一种面向连接的、
        可靠的、基于字节流的传输层通信协议，
        由IETF的RFC 793定义。在简化的计算机网络OSI模型中，
        它完成第四层传输层所指定的功能，用户数据报协议（UDP）是同一层内另一个重要的传输协议。
        在因特网协议族（Internet protocol suite）中，TCP层是位于IP层之上，应用层之下的中间层。
        不同主机的应用层之间经常需要可靠的、
        像管道一样的连接，但是IP层不提供这样的流机制，而是提供不可靠的包交换。</dd>
    <dt>IP</dt>
    <dd>IP协议是将多个包交换网络连接起来，它在源地址和目的地址之间传送一种称之为数据包的东西，它还提供对数据大小的重新组装功能，以适应不同网络对包大小的要求。
        IP不提供可靠的传输服务，它不提供端到端的或（路由）结点到（路由）结点的确认，对数据没有差错控制，它只使用报头的校验码，它不提供重发和流量控制。
        如果出错可以通过ICMP报告，ICMP在IP模块中实现。</dd>
</dl>

要创建定义列表，请在第一行上键入术语。在下一行，键入一个冒号，后跟一个空格和定义。

i.e.

```bird language
term  
: definition of it.
```

<!-- 
First Term
: This is the definition of the first term. 
-->

显然，我们的vscode似乎并不支持这一特性，所以需要描述列表时，请使用HTML的特性以作代替。

## 代码

要将单词或短语表示为代码，请将其包裹在反引号 (`) 中。

### 转义反引号

如果你要表示为代码的单词或短语中包含一个或多个反引号，则可以通过将单词或短语包裹在双反引号(``)中。

e.g.  
`` 我是一个反引号` ``

### 代码块

要创建代码块，请将代码块的每一行缩进至少四个空格或一个制表符。

    <html>
      <head>
      </head>
    </html>

### 围栏代码块

Markdown基本语法允许您通过将行缩进四个空格或一个制表符来创建代码块。如果发现不方便，请尝试使用受保护的代码块。根据Markdown处理器或编辑器的不同，您将在代码块之前和之后的行上使用三个反引号（(```）或三个波浪号（~~~）。

<!-- 

~~~
{
  "firstName": "John",
  "lastName": "Smith",
  "age": 25
}
~~~ 

-->

`MD040/fenced-code-language: Fenced code blocks should have a language specified`

`MD046 - Code block style`  
即，代码块风格应一致，要么全部是缩进四格（制表符）表示的Indented，要么是 ``` 表示的Fenced,

#### 语法高亮

许多Markdown处理器都支持受围栏代码块的语法突出显示。使用此功能，您可以为编写代码的任何语言添加颜色突出显示。要添加语法突出显示，请在受防护的代码块之前的反引号旁边指定一种语言。

```json
{
  "firstName": "John",
  "lastName": "Smith",
  "age": 25
}
```

## 分隔线语法

要创建分隔线，请在单独一行上使用三个或多个星号 (***)、破折号 (---) 或下划线 (___) ，并且不能包含其他内容。

***

`MD035: Horizontal rule style [Expected: ***; Actual: ---.___]`

### 实践

为了兼容性，请在分隔线的前后均添加空白行。

## 链接

链接文本放在中括号内，链接地址放在后面的括号中，链接title可选。

超链接Markdown语法代码：  
`[超链接显示名](超链接地址 "超链接title")`

e.g.

[这是一个链接](https://cn.bing.com/ "点我去一个好地方")

### 网址和Email地址

使用尖括号可以很方便地把URL或者email地址变成可点击的链接。

e.g.  

 <https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint>

<381460965@qq.com>

#### 自动网址链接

许多Markdown处理器会自动将URL转换为链接。这意味着如果您输入 `http://www.example.com`，即使您未使用方括号，您的Markdown处理器也会自动将其转换为链接。

但∵ `MD034/no-bare-urls: Bare URL used` ，理应规范化添加尖括号。

##### 禁用自动URL链接

如果您不希望自动链接URL，则可以通过将URL表示为带反引号的代码来删除该链接。

`www.baidu.com`

### 带格式化的链接

强调 链接, 在链接语法前后增加星号。  
要将链接表示为代码，请在方括号中添加反引号。

e,g,

***[我是一个又粗又斜的链接](lol.jpg "点我")***

[`print("Hello,world!"`](https://baidu.com)

TODO

### 引用样式链接

引用样式链接是一种特殊的链接，它使URL在Markdown中更易于显示和阅读。参考样式链接分为两部分：与文本保持内联的部分以及存储在文件中其他位置的部分，以使文本易于阅读。

#### 链接的第一部分格式

引用类型的链接的第一部分使用两组括号进行格式设置。第一组方括号包围应显示为链接的文本。第二组括号显示了一个标签，该标签用于指向您存储在文档其他位置的链接。

尽管不是必需的，可以在第一组和第二组括号之间包含一个空格。第二组括号中的标签不区分大小写，可以包含字母，数字，空格或标点符号

[Hobbit-hole][1]

#### 链接的第二部分格式

引用类型链接的第二部分使用以下属性设置格式：

- 放在括号中的标签，其后紧跟一个冒号和至少一个空格（例如[label]:）。
- 链接的URL，可以选择(实际上也应该）将其括在尖括号中。
- 链接的可选标题，可以将其括在双引号，单引号或括号中。

以下示例格式对于链接的第二部分效果相同：

- [Hobbit-hole][1]: <https://en.wikipedia.org/wiki/Hobbit#Lifestyle> "Hobbit lifestyles"

- [Hobbit-hole][1]: <https://en.wikipedia.org/wiki/Hobbit#Lifestyle> 'Hobbit lifestyles'
- [Hobbit-hole][1]: <https://en.wikipedia.org/wiki/Hobbit#Lifestyle> (Hobbit lifestyles)

## 图片

要添加图像，请使用感叹号 (!), 然后在方括号增加替代文本，图片链接放在圆括号里，括号里的链接后可以增加一个可选的图片标题文本。

插入图片Markdown语法代码：
`![图片alt](图片链接 "图片title")`

对应的HTML代码：`<img src="图片链接" alt="图片alt" title="图片title">`

e.g.
![这是图片](lol.jpg "wuhu!
")

### 链接图片

给图片增加链接，请将图像的Markdown 括在方括号中，然后将链接添加在圆括号中。

e,g,
[![这是图片](lol.jpg "wuhu!
")](https://lol.qq.com/main.shtml)

### 直接复制

![](../../resources/pictures/2021-05-19-22-55-18.png)

## 转义字符

要显示原本用于格式化 Markdown 文档的字符，请在字符前面添加反斜杠字符 \ 。

e.g.  
\*\*一闪一闪亮晶晶**

FIXME

### 特殊字符自动转义

在 HTML 中，某些字符是预留的。
比如不能使用小于号（<）和大于号（>），这是因为浏览器会误认为它们是标签。  
如果希望正确地显示预留字符，我们必须在 HTML 源代码中使用字符实体（character entities）。  
比如要写这篇日志在前端展现出大于号（>），小于号（<）等就必须在后台数据库中把这些对象保存成字符实体的形式。
字符实体类似这样：

- &entity_name;
- &#entity_number;
  
如需显示小于号，我们必须这样写：

- `&lt`;
- `&#60`;
  
提示：使用实体名而不是数字的好处是，名称易于记忆。不过坏处是，浏览器也许并不支持所有实体名称（对实体数字的支持却很好）。

#### 常见HTML特殊字符

- < 小于号`&lt`;`&#60`;
- \>大于号`&gt`;`&#62`;
- & 和号`&amp`;`&#38`;

Markdown 允许你直接使用这些符号，它帮你自动转义字符。
如果你使用 & 符号的作为 HTML 实体的一部分，那么它不会被转换，
而在其它情况下，它则会被转换成 `&amp`;。

所以你如果要在文件中插入一个著作权的符号，你可以这样写：
`&copy`;

Markdown 将不会对这段文字做修改，但是如果你这样写:

`AT&T`

Markdown 就会将它转为：

`AT&T`

类似的状况也会发生在 < 符号上，因为 Markdown 支持 行内 HTML ，如果你使用 < 符号作为 HTML 标签的分隔符，那 Markdown 也不会对它做任何转换，但是如果你是写：

`4 < 5`  
Markdown 将会把它转换为：

`4 &lt; 5`

需要特别注意的是，在 Markdown 的块级元素和内联元素中， < 和 & 两个符号都会被自动转换成 HTML 实体，这项特性让你可以很容易地用 Markdown 写 HTML。（在 HTML 语法中，你要手动把所有的 < 和 & 都转换为 HTML 实体。）

## 内嵌HTML标签

对于 Markdown 涵盖范围之外的标签，都可以直接在文件里面用 HTML 本身。如需使用 HTML，不需要额外标注这是 HTML 或是 Markdown，只需 HTML 标签添加到 Markdown 文本中即可。

### 行级內联标签

HTML 的行级內联标签如 `<span>`、`<cite>`、`<del>` 不受限制，可以在 Markdown 的段落、列表或是标题里任意使用。依照个人习惯，甚至可以不用 Markdown 格式，而采用 HTML 标签来格式化。例如：如果比较喜欢 HTML 的 `<a>`或 `<img>` 标签，可以直接使用这些标签，而不用 Markdown 提供的链接或是图片语法。当你需要更改元素的属性时（例如为文本指定颜色或更改图像的宽度），使用 HTML 标签更方便些。

HTML 行级內联标签和区块标签不同，在內联标签的范围内， Markdown 的语法是可以解析的。

`This **word** is bold. This <em>word</em> is italic.`

`MD033/no-inline-html: Inline HTML [Element: em]`  
但是MD规范禁止如此做。

### 区块标签

区块元素──比如 `<div>`、`<table>`、`<pre>`、`<p>` 等标签，必须在前后加上空行，以便于内容区分。而且这些元素的开始与结尾标签，不可以用 tab 或是空白来缩进。Markdown 会自动识别这区块元素，避免在区块标签前后加上没有必要的 `<p>` 标签。

例如，在 Markdown 文件里加上一段 HTML 表格：

This is a regular paragraph.

```html
<table>
    <tr>
        <td>Foo</td>
    </tr>
</table>
```

This is another regular paragraph.  
请注意，Markdown 语法在 HTML 区块标签中将不会被进行处理。例如，你无法在 HTML 区块内使用 Markdown 形式的*强调*。

### 最佳实践

出于安全原因，并非所有 Markdown 应用程序都支持在 Markdown 文档中添加 HTML。

对于 HTML 的块级元素 `<div>`、`<table>`、`<pre>`和 `<p>`，请在其前后使用空行（blank lines）与其它内容进行分隔。尽量不要使用制表符（tabs）或空格（spaces）对 HTML 标签做缩进，否则将影响格式。

在 HTML 块级标签内不能使用 Markdown 语法。例如 `<p>`italic and **bold**</p> 将不起作用。

## 扩展语法

并非所有Markdown应用程序都支持扩展语法元素。您需要检查您的应用程序所使用的轻量级标记语言是否支持您要使用的扩展语法元素。如果没有，那么仍然有可能在Markdown处理器中启用扩展。

### 轻量标记语言

有几种轻量级标记语言是Markdown的超集。它们包含Gruber的基本语法，并通过添加其他元素（例如表，代码块，语法突出显示，URL自动链接和脚注）在此基础上构建。许多最受欢迎的Markdown应用程序使用以下轻量级标记语言之一：

- CommonMark
- GitHub Flavored Markdown (GFM)
- Markdown Extra
- MultiMarkdown
- R Markdown

### Markdown 处理器

有许多[Markdown处理器](https://github.com/markdown/markdown.github.com/wiki/Implementations)可用。它们中的许多允许您添加启用扩展语法元素的扩展。查看您所使用处理器的文档以获取更多信息。

### Emoji

有两种方法可以将表情符号添加到Markdown文件中：将表情符号复制并粘贴到Markdown格式的文本中，或者键入emoji shortcodes。

#### 复制表情

在大多数情况下，您可以简单地从[Emojipedia](https://emojipedia.org/) 等来源复制表情符号并将其粘贴到文档中。  
且，许多Markdown应用程序会自动以Markdown格式的文本显示表情符号。从Markdown应用程序导出的HTML和PDF文件应显示表情符号。

e.g.
😂

Tip: 如果您使用的是静态网站生成器，请确保将HTML页面编码为UTF-8.

#### 使用表情符号简码

一些Markdown应用程序允许您通过键入表情符号短代码来插入表情符号。这些以冒号开头和结尾，并包含表情符号的名称。

e,g.
难受了！ :cry:

## 删除线

若要删除单词，请~~在单词前后使用两个波浪号。  
此功能使您可以指示某些单词是一个错误，并不表示要包含在文档中

e.g.
~~我已无敌~~ , 事实上并不是 :flags:

First Term
: This is the definition of the first term.

## 脚注

脚注使您可以添加注释和参考，而不会使文档正文混乱。

在需要添加注脚的文字后加上： `[^1]` 。 然后在文本的任意位置(一般在最后)添加脚注：`[^1]: 脚注内容`。

读者就可以单击链接以跳至页面底部的脚注内容。

### 具体语法

要创建脚注参考，请在方括号 `[ ]`内添加 插入符号`^` 和标 识符。
e.g. `[^1]` .

标识符可以是数字或单词，但不能包含空格或制表符。  
标识符仅将脚注参考与脚注本身相关联

在输出中，脚注按顺序编号。

您不必在文档末尾添加脚注。您可以将它们放在除列表，块引号和表之类的其他元素之外的任何位置。

e.g.

使用 Markdown可以效率的书写文档, 直接转换成 HTML[^2], 你可以使用 Typora[^T] 编辑器进行书写。

[^2]: HyperText Markup Language 超文本标记语言

[^T]: NEW WAY TO READ & WRITE MARKDOWN.

FIXME

## 表格

要添加表，请使用三个或多个连字符（---）创建每列的标题，并使用管道（|）分隔每列。您可以选择在表的任一端添加管道。

| Syntax      | Description |
| ----------- | ----------- |
| Header      | Title       |
| Paragraph   | Text        |

单元格宽度可以变化，如下所示。呈现的输出将看起来相同。

| Syntax | Description |
| --- | ----------- |
| Header | Title |
| Paragraph | Text |

所以不用太处女座，意思意思即可

Tip: 使用连字符和管道创建表可能很麻烦。为了加快该过程，请尝试使用[Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables)。使用图形界面构建表，然后将生成的Markdown格式的文本复制到文件中。

### 对齐

您可以通过在标题行中的连字符的左侧，右侧或两侧添加冒号`:`，将列中的文本对齐到左侧，右侧或中心。

e.g.

| Syntax      | Description | Test Text     |
| :---        |    :----:   |          ---: |
| Header      | Title       | Here's this   |
| Paragraph   | Text        | And more      |

### 表内乾坤

您可以在表格中设置文本格式。例如，您可以添加链接，代码（仅反引号（`）中的单词或短语，而不是代码块）和强调。

您不能添加标题，块引用，列表，水平规则，图像或HTML标签。

### 在表中转义管道字符

您可以使用表格的HTML字符代码（`&#124;`）在表中显示竖线`|`字符。

e.g.

| num | name|
|--|---|
|19321124|Xie &#124; Zhixuan|
