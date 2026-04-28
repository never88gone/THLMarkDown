# 糖葫芦MarkDown

![糖葫芦MarkDown logo](https://raw.githubusercontent.com/never88gone/THLMarkDown/main/images/icon_256x256.png)

你好呀！我是 **糖葫芦MarkDown**，一款 macOS 平台的开源 Markdown 编辑器。

请允许我为您做一个简短的自我介绍。



## Markdown 与我

**Markdown** 是一种轻量级标记语言，由 John Gruber 创立，旨在提供一种易读易写的无格式文本格式。原始的 Markdown 语法规范可以在 [这里](https://daringfireball.net/projects/markdown/syntax) 查阅。

**糖葫芦MarkDown** 是一款旨在让 Markdown 编写变得更加简单的文档编辑器。我可以在您编辑时将 Markdown 内容实时渲染为 HTML，并在右侧预览窗格中完美呈现。

![糖葫芦MarkDown Screenshot](https://raw.githubusercontent.com/never88gone/THLMarkDown/main/images/screenshot.png)

除了完全支持标准 Markdown 的所有语法，我能做的还有很多！在我的 [**Markdown** 偏好设置面板](#markdown-pane) 中，您可以轻松切换许多流行但不属于标准语法的扩展功能标记。

您也可以在大本营——[**渲染 (Rendering)** 偏好设置面板](#rendering-pane) 中，自定义额外的 HTML 渲染选项。

在 [**编辑器 (Editor)** 偏好设置面板](#editor-pane) 中，您可以根据自己的喜好对编辑窗口进行自定义配置。

而关于我（这款应用）的各类运行行为，都能在 [**一般 (General)** 偏好设置面板](#general-pane) 中进行设定。

## 基础语法
在向您展示我的各种高级扩展语法和能力之前，我将先为您介绍 Markdown 的必备基础。如果您早已是一位 Markdown 熟手，并希望直接了解我更强大的功能，建议您跳过此章节直奔 [**Markdown** 偏好设置面板](#markdown-pane)。现在，让我们直接开始吧。  

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

网站 URL 的方法相同: <https://github.com/never88gone>  
` <https://github.com/never88gone>`  

也许您希望将特定文字作为链接: [糖葫芦MarkDown 主页](https://github.com/never88gone "这是一个标题")  
`[糖葫芦MarkDown 主页](https://github.com/never88gone "这是一个标题")` (标题文字是可选的)  


#### 引用标记
有时候将又长又乱的网址直接放在正文里显得太杂乱了，或者您只是想把所有的网址链接统一放在一起管理。

您可以像这样创建一个带有引用 ID 的链接 [我是一个链接][arbitrary_id]，即 `[我是一个链接][arbitrary_id]`，然后在文档任意其他地方单独起一行写下：  
`[arbitrary_id]: https://github.com/never88gone "这是一个标题"`
  
如果链接的文字本身就很适合做为您设定的 ID，您也可以这样标记 [比如我][]，即 `[比如我][]`，然后在文档其他地方另起一行写下：  
`[比如我]: https://github.com/never88gone`  

[arbitrary_id]: https://github.com/never88gone "这是一个标题"
[比如我]: https://github.com/never88gone  


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
		42. 当然，您实际上写了什么数字并不重要，我会自动按照顺序为您渲染它们
		1. 所以您大可全部以 `1.` 偷懒开头，把排序查数的活儿全交给我吧

具体的代码展示：

```
* 列表的前一行必须是一个空行（或者是一个块级元素）
* 无序列表中的每一项以 `*` 开头
- 使用 `-` 也同样起效
	* 缩进一个层级以创建一个嵌套列表
		1. 我也支持有序列表。
		2. 每一项以 (数字+小数点+空格) 开始，像 `1. `
		42. 当然，您实际上写了什么数字并不重要，我会自动按照顺序为您渲染它们
		1. 所以您大可全部以 `1.` 偷懒开头，把排序查数的活儿全交给我吧
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
![Markdown preferences pane](https://raw.githubusercontent.com/never88gone/THLMarkDown/main/images/markdown_preferences.png)

### 文档格式化 (Document Formatting)
***Smartypants*** 扩展可以根据当前的语境，自动将文本当中的直引号（`"` 和 `'`）转化为标准的印刷界弯引号（`“`，`”`，`‘` 和 `’`）。如果您和我一样有着近乎挑剔的排版强迫症，这就非常好用了。提示：`Quote` 语法和 `Smartypants` 互相排斥。如果它们俩同时生效，`Quote` 优先级会更高。


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


您可以在第一行的末尾附加一个语言 ID。如果您勾选了 ***启用代码块内语法高亮 (Enable highlighting in code blocks)*** 选项，该语言 ID 将专项指引并渲染代码块内的高亮样式。启用后是这个样子的：

![Syntax highlighting example](https://raw.githubusercontent.com/never88gone/THLMarkDown/main/images/syntax_highlighting.png)

除此之外，我其实开箱即用地支持海量的流行语言以及一些可以通用泛用的描述性语法类别。如果您感兴趣，可以访问 [官网的这一章节](https://github.com/never88gone) 查看全部受支持语法列表。


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
![Rendering preferences pane](https://raw.githubusercontent.com/never88gone/THLMarkDown/main/images/rendering_preferences.png)

### 样式表 (CSS)
您可以为通过我导出的 HTML 文件直接指定多套不同风格的 CSS 素材文件，甚至支持高度化定制或者将原本独有的个人样式文件加入进来。

### 语法高亮体系 (Syntax Highlighting)
我猜您已经见识过我在处理围栏代码块方面有过多强大了吧。其实对于不同场景的语法高亮，我在内部准备了各异的主题配色供君选用。

### 类似 TeX 的数学公式 (TeX-like Math Syntax)
如果您不介意，我非常乐意渲染类似 TeX 这种理工科的数学公式解析操作。[^math]  
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
如果能够帮助到您工作的话，利用漂亮的表格为您描画 Jekyll 标头属性 (front-matter) 当仁不让。您只需要时刻确保将它们放在全文的最开头，并且使用 `---` 划定其边界即可。例如：

```
---
title: "糖葫芦MarkDown 是您的好朋友"
date: 2014-06-06 20:00:00
---
```

### 硬回车渲染新行 (Render newline literally)
通常我强烈建议您养成良好的文学习惯，必须使用两个连续的空格以及按下回车符才能创建一个真正的文字换行。一旦开启此功能，无论任何时候只要您按下回车我便立刻为您换行。请知悉，这样不仅会导致输出的结果变得比较失控不规整，也无法兼容当您利用*别的* Markdown 阅读器继续查看文档时的体验。


## <a name="general-pane"></a>常规设置面板 (General)

这里的各类设置决定着我的应用程序整体日常行为。  
![General preferences pane](https://raw.githubusercontent.com/never88gone/THLMarkDown/main/images/general_preferences.png)

您可以通过选项教导我该具备怎样的习惯。例如，是否要求在启动的那刻保证存在一份新建打开的空白文档？您也需要决定，在您忘情输入文字的那刻，是希望实时且持续顺滑地同时更新右侧排版，还是干脆由您亲自主导进度通过按快捷键 `Command-R` 再行刷新呢。或许有那么几位强迫症会更偏爱把编辑源文件框放在屏幕偏右的部分。又或者每打出一段字都需要看到实时字数统计浮现……总而言之，这里还可以让我们决定是跟随更平顺安稳的官方正式版本、还是紧紧拥抱测试阶段那些激动人心的预发新特征体验！

## <a name="editor-pane"></a>编辑偏好配置面板 (Editor)
这是设定当前编辑主视窗风格及习惯的重要关卡。  
![Editor preferences pane](https://raw.githubusercontent.com/never88gone/THLMarkDown/main/images/editor_preferences.png)


### 外观展现 (Styling)

基于当前默认提供的自动语法高亮，您还能完全自由定义基础字号的大小或者配色体系（得特别感谢提供精美预设主题的 [Mou](http://mouapp.com) 软件的创造者 - 罗晨）。

您觉得预设还是太土？没关系，直接点击 ***Reveal*** 打开源文件库然后像艺术生一样涂涂抹抹吧。切记只能并且必须让它们的后缀一直处在正确的文件拓展名（`.styles`）之下。在这件事上我异常看重！

另外别忘啦，自动全拼提示、关联语法缩写等等诸多极大优化编辑手感的选项，在此也静候差遣，按您的脾性完全可以尽数关毕。


## 探索与客制化进阶

另外向极客们透露一个好玩的方法：想要直观地查看最终那些输出被排版成了哪一种 HTML 代码吗？现在您只需通过在系统的终端工具中输入下面这行命令行指令即可启动 macOS 全局针对我的 “WebKit 原生开发者元素工具面板”。

```
defaults write com.uranusjr.thlmarkdown WebKitDeveloperExtras -bool true
```

大功告成后，现在在渲染区域尝试通过点击鼠标右键点击“检查元素 (Inspect Element)”——您将看到 Safari 浏览器那个令人着迷的全套工具面板。


## 隐私政策

本应用非常重视您的隐私保护。有关我们的数据处理方式以及我们对“无服务器通信”及“不收集个人信息”的承诺，请参阅我们的详细[隐私政策](PrivacyPolicy_zh.md)。

## 享受创造之旅！

我要说的这就是全部了。听我絮絮叨叨这么多也实属不易，接下来我一定会安安静静、踏踏实实地在背后完成排版工作。（除非我有了极大的应用升级包要更新提醒您）。

祝写作愉快！


[^emphasize]: 如果 **被配置为了特殊的 Underlines (下划线解析)** 模型, 那么带有下划线的 `_这句文案_` 将直接转化为标准的页面带下划线，不再作为强调/斜体元素。 

[^under]: 反之如果关闭了这个特定下划线选项的话 `_这个样子_` 将被照旧渲染成 *斜体* 而不是下方的长划线。

[^quote]: **引用 (Quote)** 语序可以将直文字字符的 `"` 双边引用符号智能转化为 html 代码下的 `<q>` 标签。由于 **引用标记 (Quote)** 以及 **(Smartypants)** 从词法上严重不相容。当您强制它们被双双激活下, 最终起死回生生效的主体只会保留 **Quote** 标记。务必当心的是，此处的 **Quote** 与标准 Markdown 概念中所涵盖的 *blockquote (长引用块)* 的功能天差地别。

[^math]: 这个操作仅供拥有实时强力的外部稳定网络连接下才能保证正常运转。
