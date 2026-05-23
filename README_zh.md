# 糖葫芦MarkDown

![THLMarkDown logo](https://raw.githubusercontent.com/never88gone/THLMarkDown/main/images/icon_256x256.png)

欢迎使用 **糖葫芦MarkDown**，一款专为 macOS 平台打造的专业 Markdown 编辑器。

本帮助文档将引导您了解编辑器的各项功能和基础用法。



## 关于 Markdown

**Markdown** 是一种轻量级标记语言，由 John Gruber 创立，旨在提供一种易读易写的无格式文本格式。原始的 Markdown 语法规范可以在 [这里](https://daringfireball.net/projects/markdown/syntax) 查阅。

**糖葫芦MarkDown** 提供直观的 Markdown 编辑体验。它能在您编辑时实时将 Markdown 内容渲染为 HTML，并在右侧预览窗格中即时呈现。

在未打开任何文件时，界面呈现极简的空白状态：
![THLMarkDown 首页空白](https://raw.githubusercontent.com/never88gone/THLMarkDown/main/images/%E9%A6%96%E9%A1%B5-%E7%A9%BA%E7%99%BD.png)

当您开始编写时，左侧为支持语法高亮的编辑器，右侧为实时预览：
![THLMarkDown 首页内容](https://raw.githubusercontent.com/never88gone/THLMarkDown/main/images/%E9%A6%96%E9%A1%B5-%E5%86%85%E5%AE%B9.png)

除了完全支持标准 Markdown 语法外，应用还提供了丰富的扩展功能。在 [**Markdown** 偏好设置面板](#markdown-pane) 中，您可以轻松开启或关闭各种高级语法扩展。

您也可以在 [**渲染 (Rendering)** 偏好设置面板](#rendering-pane) 中，自定义 HTML 渲染的样式和选项。

在 [**编辑器 (Editor)** 偏好设置面板](#editor-pane) 中，您可以根据个人习惯对编辑界面进行个性化配置。

关于应用程序的全局行为，可以在 [**通用 (General)** 偏好设置面板](#general-pane) 中进行设定。

在 [**快捷键 (Shortcuts)** 偏好设置面板](#shortcuts-pane) 中，您可以自定义各种常用操作的快捷键。

在 [**第三方组件 (Third-Party)** 偏好设置面板](#third-party-pane) 中，您可以查看应用所使用的开源组件及其许可协议。

在 [**隐私政策 (Privacy)** 偏好设置面板](#privacy-pane) 中，您可以查阅我们的隐私政策，并配置相关的网络访问选项。

## 基础语法
在深入了解高级扩展之前，本节将为您介绍 Markdown 的必备基础。如果您熟悉 Markdown 语法，可以跳过此章节，直接查看 [**Markdown** 偏好设置面板](#markdown-pane)。  

### 换行 (Line Breaks)
要强制换行，请在句末键入两个空格并按下回车键（Newline）。

* 这段两行的文本 
没有换行

* 这段两行的文本  
将会换行

具体的代码对照如下：

```
* 这段两行的文本 
没有换行

* 这段两行的文本  
将会换行
```

### 粗体与斜体 (Strong and Emphasize)

**粗体**: `**粗体文字**` 或 `__粗体文字__` (快捷键 Command-B)  
*斜体*: `*斜体文字*` 或 `_斜体文字_`[^emphasize] (快捷键 Command-I)

### 标题 (Headers)

	一级标题
	========

	二级标题
	--------

或者

	# 一级标题
	## 二级标题
	### 三级标题
	#### 四级标题
	##### 五级标题
	###### 六级标题



### 链接与电子邮件 (Links and Email)
#### 行内标记
只需使用尖括号包裹邮箱地址，它就会变成可点击的链接: <never88gone@gmail.com>  
`<never88gone@gmail.com>`  

网站 URL 的方法相同: <https://github.com/never88gone/thlmarkdown>  
` <https://github.com/never88gone/thlmarkdown>`  

也许您希望将特定文字作为链接: [糖葫芦MarkDown 主页](https://github.com/never88gone/thlmarkdown "这是一个标题")  
`[糖葫芦MarkDown 主页](https://github.com/never88gone/thlmarkdown "这是一个标题")` (标题文字是可选的)  


#### 引用标记
有时候将又长又乱的网址直接放在正文里显得太杂乱了，或者您只是想把所有的网址链接统一放在一起管理。

您可以像这样创建一个带有引用 ID 的链接 [我是一个链接][arbitrary_id]，即 `[我是一个链接][arbitrary_id]`，然后在文档任意其他地方单独起一行写下：  
`[arbitrary_id]: https://github.com/never88gone/thlmarkdown "这是一个标题"`
  
如果链接的文字本身就很适合做为您设定的 ID，您也可以这样标记 [比如我][]，即 `[比如我][]`，然后在文档其他地方另起一行写下：  
`[比如我]: https://github.com/never88gone/thlmarkdown`  

[arbitrary_id]: https://github.com/never88gone/thlmarkdown "这是一个标题"
[比如我]: https://github.com/never88gone/thlmarkdown  


### 图片 (Images)
#### 行内标记
`![图片的替代文本](path/or/url/to.jpg "可选的标题文字")`
#### 引用标记
`![图片的替代文本][image-id]`  
然后在文档其他地方另起一行：  
`[image-id]: path/or/url/to.jpg "可选的标题文字"`


### 列表 (Lists)

* 列表的前一行必须是一个空行（或者是一个块级元素）
* 无序列表中的每一项以 `*` 开头
- 使用 `-` 也同样起效
	* 缩进一个层级以创建一个嵌套列表
		1. 我也支持有序列表。
		2. 每一项以 (数字+小数点+空格) 开始，像 `1. `
		42. 实际书写的数字并不重要，系统会自动按顺序渲染
		1. 因此您可以全部使用 `1.` 开头，编辑器会自动处理排序

具体的代码展示：

```
* 列表的前一行必须是一个空行（或者是一个块级元素）
* 无序列表中的每一项以 `*` 开头
- 使用 `-` 也同样起效
	* 缩进一个层级以创建一个嵌套列表
		1. 我也支持有序列表。
		2. 每一项以 (数字+小数点+空格) 开始，像 `1. `
		42. 实际书写的数字并不重要，系统会自动按顺序渲染
		1. 因此您可以全部使用 `1.` 开头，编辑器会自动处理排序
```



### 引用块 (Block Quote)

> 尖括号 `>` 通常用于标记引用块落。  
从技术上讲，只要段落之间没有空行，并不是每一行都需要以 `>` 开头。  
> 虽然那样看起来可能有点丑。
> > 引用也可以被嵌套。  
> > > 并且支持多个层级
>
> 绝大多数常规 Markdown 语法也可以在引用块内使用。
>
> * 比如列表
> * [比如链接][arbitrary_id]
> * 等等等等。

代码展示如下：

```
> 尖括号 `>` 通常用于标记引用块落。  
从技术上讲，只要段落之间没有空行，并不是每一行都需要以 `>` 开头。  
> 虽然那样看起来可能有点丑。
> > 引用也可以被嵌套。  
> > > 并且支持多个层级
>
> 绝大多数常规 Markdown 语法也可以在引用块内使用。
>
> * 比如列表
> * [比如链接][arbitrary_id]
> * 等等等等。
```
  
  
### 行内代码 (Inline Code)
您可以在需要高亮的单词首尾加上重音符号（也就是小圆点或者反引号），将其标记为 `一行代码`：  
`` `一行代码` ``

如果您的代码内本就含有重音符号 `像这样`，那么您可以使用两对重音符号将它包围起来：  
```` ``这个代码里 有 `重音符号` `` ````  (留意前后包围符号内部预留的空格)


### 块级代码 (Block Code)
只要您对某几行内容进行至少 4 个空格或 1 个 Tab 制表符的缩进，我就会将其渲染为一个块级代码块。

	print('我是一个独立的代码逻辑区')
	print('但必须保证我在正文换行之后出现')
	print('然后你只需要按下至少一次 Tab 键进行缩进')
		print('嵌套没啥用，你的代码会被原样输出')

对了，我还能解析被称为 [围栏代码块 (Fenced Code Blocks)](#fenced-code-block) 的标记，这点我稍后再向您仔细说明。

### 分割线 (Horizontal Rules)
如果在单独的一行里输入三个星号 `***`，或者三个破折号 `---`，我就会为您绘制一条水平分割线：

***


## <a name="markdown-pane"></a>Markdown 偏好设置面板
我在这个选项卡里记录了把 Markdown 解析成 HTML 的所有相关配置。  
![Markdown 偏好设置](https://raw.githubusercontent.com/never88gone/THLMarkDown/main/images/%E5%81%8F%E5%A5%BD%E8%AE%BE%E7%BD%AE-MarkDown.png)

### 文档格式化 (Document Formatting)
***Smartypants*** 扩展可以根据当前的语境，自动将文本当中的直引号（`"` 和 `'`）转化为标准的印刷界弯引号（`“`，`”`，`‘` 和 `’`）。这对于提升排版质量非常有帮助。提示：`Quote` 语法和 `Smartypants` 互相排斥，若同时开启，`Quote` 的优先级更高。


### 块级格式化 (Block Formatting)

#### 表格 (Table)

我支持这样的表格编写：

我是表头第一行  | 这是第二行表头
------------- | -------------
我是单元格之一  | 我也一样
内容单元格     | 内容单元格

同时可以利用这一语法指定单元格内容的对齐方式：

| 左侧对齐      |     居中对齐    | 靠右对齐 |
|:------------- |:---------------:| -------------:|
| 第三列表示       | 一些特别长的文字 |         $1600 |
| 第二列是      | 被居中显示的    |           $12 |
| 斑马条纹 | 看起来很酷       |            $1 |

可以看到最左边和最右边的管道符（`|`）其实完全仅仅出于美观存在，您并非必须要输入它们。空格的多少也不会影响什么。唯一被拿来决定该怎么对齐的，是冒号 `:` 。

#### <a name="fenced-code-block">围栏代码块 (Fenced Code Block)</a>

以下是一段围栏代码块：

```
print('Hello world!')
```

您也可以使用波浪线 (`~`) 代替反引号 (`` ` ``):

~~~
print('Hello world!')
~~~


您可以在第一行的末尾附加一个语言 ID。如果您勾选了 ***启用代码块内语法高亮 (Enable highlighting in code blocks)*** 选项，该语言 ID 将专项指引并渲染代码块内的高亮样式。

除此之外，编辑器内置支持海量的流行语言高亮。如果您感兴趣，可以访问 [官网的这一章节](https://github.com/never88gone/thlmarkdown/features/) 查看全部受支持语法列表。


### 行内格式化 (Inline Formatting)

以下是我支持且可选开启的一些内联扩展语法：

功能名称             | 书写语法            | 启用状态下的表现       |
--------------------|------------------|-----------------------|
词内斜体 (Intra-word)| So A\*maz\*ing   | So A<em>maz</em>ing   |
删除线 (Strikethrough) | \~~Much wow\~~   | <del>Much wow</del>   |
下划线 (Underline) [^under]| \_So doge\_      | <u>So doge</u>        |
引用 (Quote) [^quote] | \"Such editor\"  | <q>Such editor</q>    |
高亮 (Highlight)      | \==So good\==    | <mark>So good</mark>  |
上标 (Superscript)    | hoge\^(fuga)     | hoge<sup>fuga</sup>   |
短链接 (Autolink)     | http://t.co      | <http://t.co>         |
尾注标明 (Footnotes)   | [\^4] 和 [\^4]: | [^4] 和 footnote 4    |

[^4]: 您不必一定使用数字。随便写诸如 `[^我是尾注文本4]` 和 `[^我是尾注文本4]:` 也是完全允许的。由于它是尾注，最终依然将被*渲染*成带数字序号的脚注。此外，不必苛求编写脚注出现的先后顺序，我会根据当前在文中的引用顺序为您自动进行排序整理。您甚至可以把一些脚注直接放在它们在文中的出处附近，但它们仍会在文末的页脚区统一集结。 




## <a name="rendering-pane"></a>渲染体验面板 (Rendering)
渲染面板记录了我应该如何解析内容并为您描绘预览窗口所有的样式。  
![Rendering 偏好设置](https://raw.githubusercontent.com/never88gone/THLMarkDown/main/images/%E5%81%8F%E5%A5%BD%E8%AE%BE%E7%BD%AE-%E6%B8%B2%E6%9F%93.png)

### 样式表 (CSS)
您可以为通过我导出的 HTML 文件直接指定多套不同风格的 CSS 素材文件，甚至支持高度化定制或者将原本独有的个人样式文件加入进来。

### 语法高亮体系 (Syntax Highlighting)
编辑器内置了多种不同风格的语法高亮主题，适用于各种代码展示场景。

### 类似 TeX 的数学公式 (TeX-like Math Syntax)
编辑器支持解析和渲染类似 TeX 的数学公式。[^math]  
例如渲染这种行内公式： \\( 1 + 1 \\) ，或者这个（用 MathML 编写）： <math><mn>1</mn><mo>+</mo><mn>1</mn></math>，以及块级数学公式：

\\[
    A^T_S = B
\\]

或者（用 MathML）：

<math display="block">
    <msubsup><mi>A</mi> <mi>S</mi> <mi>T</mi></msubsup>
    <mo>=</mo>
    <mi>B</mi>
</math>



### 任务清单体系 (Task List Syntax)
1. [x] 完美具备复选框解析的能力
	* [x] 支持层次分明的多级复选嵌套
	* [x] 我甚至支持结合使用在 有序 *及* 无序的列表中
2. [ ] 在这里我不支持直接于预览窗口的 HTML 中通过鼠标点击实现对选框状态的切换


### Jekyll front-matter 元素
支持将 Jekyll 标头属性 (front-matter) 渲染为清晰的表格。请确保将其放置在文档的最开头，并使用 `---` 划定边界：

```
---
title: "糖葫芦MarkDown 是您的好朋友"
date: 2014-06-06 20:00:00
---
```

### 硬回车渲染新行 (Render newline literally)
标准语法建议使用两个空格加回车来换行。若开启此选项，直接按下回车即可换行。请注意，开启此功能可能导致文档在其他严格遵循标准的 Markdown 阅读器中排版不一致。


## <a name="general-pane"></a>常规设置面板 (General)

在此处配置应用程序的整体运行行为。  
![General 偏好设置](https://raw.githubusercontent.com/never88gone/THLMarkDown/main/images/%E5%81%8F%E5%A5%BD%E8%AE%BE%E7%BD%AE-%E9%80%9A%E7%94%A8.png)

您可以设置是否在启动时创建新文档，选择实时更新预览或手动刷新 (`Command-R`)。还可以调整编辑器与预览框的左右位置，以及是否在底部显示字数统计等功能。

## <a name="editor-pane"></a>编辑偏好配置面板 (Editor)
在此可以配置编辑器窗口的字体、主题和排版风格。  
![Editor 偏好设置](https://raw.githubusercontent.com/never88gone/THLMarkDown/main/images/%E5%81%8F%E5%A5%BD%E8%AE%BE%E7%BD%AE-%E7%BC%96%E8%BE%91%E5%99%A8.png)


### 外观展现 (Styling)

您可以自由定义编辑器的字体大小和高亮配色体系，内置了多种精心设计的主题供您选择。

如果需要自定义主题，可以点击 ***Reveal*** 打开主题文件夹并自行修改。请确保自定义主题的文件扩展名为 `.styles`。

此外，您还可以设置自动补全、自动缩进等选项，以优化您的编辑体验。


## <a name="shortcuts-pane"></a>快捷键设置面板 (Shortcuts)

在此可以自定义和管理各种常用操作的键盘快捷键，以完美契合您的输入习惯。  
![Shortcuts 偏好设置](https://raw.githubusercontent.com/never88gone/THLMarkDown/main/images/%E5%81%8F%E5%A5%BD%E8%AE%BE%E7%BD%AE-%E5%BF%AB%E6%8D%B7%E9%94%AE.png)

您可以直接录制或修改特定功能的快捷组合键，提高输入效率。

## <a name="third-party-pane"></a>第三方组件面板 (Third-party)

糖葫芦MarkDown 的开发离不开众多优秀开源社区的支持。在此可以查看我们引用的所有第三方库及其对应许可证。  
![Third-party 偏好设置](https://raw.githubusercontent.com/never88gone/THLMarkDown/main/images/%E5%81%8F%E5%A5%BD%E8%AE%BE%E7%BD%AE-%E7%AC%AC%E4%B8%89%E6%96%B9%E7%BB%84%E4%BB%B6.png)

## <a name="privacy-pane"></a>隐私政策面板 (Privacy)

我们高度重视您的隐私。在这个面板，您可以查阅完整的隐私政策声明。  
![Privacy 偏好设置](https://raw.githubusercontent.com/never88gone/THLMarkDown/main/images/%E5%81%8F%E5%A5%BD%E8%AE%BE%E7%BD%AE-%E9%9A%90%E7%A7%81%E6%94%BF%E7%AD%96.png)

为了给您提供数学公式解析（KateX/MathJax等依赖CDN）以及自动更新检查功能，应用可能需要网络连接。在此面板中，您可以清晰了解我们如何保障您的数据安全和隐私，并根据偏好设定相关网络选项。


## 探索与客制化进阶

对于高级用户，如果需要调试预览页面的 HTML 和 CSS，可以通过终端输入以下命令来开启内置的 WebKit 开发者工具：

```
defaults write com.never88gone.thlmarkdown WebKitDeveloperExtras -bool true
```

大功告成后，现在在渲染区域尝试通过点击鼠标右键点击“检查元素 (Inspect Element)”——您将看到 Safari 浏览器那个令人着迷的全套工具面板。


## 享受创造之旅！

以上就是 糖葫芦MarkDown 的主要功能介绍。您可以开始探索并建立属于自己的工作流。

祝写作愉快！


[^emphasize]: 如果 **被配置为了特殊的 Underlines (下划线解析)** 模型, 那么带有下划线的 `_这句文案_` 将直接转化为标准的页面带下划线，不再作为强调/斜体元素。 

[^under]: 反之如果关闭了这个特定下划线选项的话 `_这个样子_` 将被照旧渲染成 *斜体* 而不是下方的长划线。

[^quote]: **引用 (Quote)** 语序可以将直文字字符的 `"` 双边引用符号智能转化为 html 代码下的 `<q>` 标签。由于 **引用标记 (Quote)** 以及 **(Smartypants)** 从词法上严重不相容。当您强制它们被双双激活下, 最终起死回生生效的主体只会保留 **Quote** 标记。务必当心的是，此处的 **Quote** 与标准 Markdown 概念中所涵盖的 *blockquote (长引用块)* 的功能天差地别。

[^math]: 这个操作仅供拥有实时强力的外部稳定网络连接下才能保证正常运转。
[README_zh.md](README_zh.md)