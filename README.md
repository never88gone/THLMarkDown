# 糖葫芦MarkDown

![THLMarkDown logo](https://raw.githubusercontent.com/never88gone/THLMarkDown/main/images/icon_256x256.png)

Welcome to **糖葫芦MarkDown**, a professional Markdown editor designed for macOS.

This documentation will help you understand its features and basics.



## About Markdown

**Markdown** is a plain text formatting syntax created by John Gruber, aiming to provide a easy-to-read and feasible markup. The original Markdown syntax specification can be found [here](https://daringfireball.net/projects/markdown/syntax).

**糖葫芦MarkDown** provides an intuitive Markdown editing experience. It renders your Markdown contents in real-time into HTML and displays them in a preview panel.

When no document is open, the interface stays in a minimalist blank state:
![THLMarkDown Blank page](https://raw.githubusercontent.com/never88gone/THLMarkDown/main/images/%E9%A6%96%E9%A1%B5-%E7%A9%BA%E7%99%BD.png)

Once you start writing, the editor on the left highlights markdown syntax, and the preview panel on the right displays the rendered HTML instantly:
![THLMarkDown Content page](https://raw.githubusercontent.com/never88gone/THLMarkDown/main/images/%E9%A6%96%E9%A1%B5-%E5%86%85%E5%AE%B9.png)

In addition to standard Markdown, the application supports numerous popular extensions. These can be enabled or disabled in the [**Markdown** preference pane](#markdown-pane).

You can customize HTML rendering styles in the [**Rendering** preference pane](#rendering-pane).

The editor's appearance and behavior can be configured in the [**Editor** preferences pane](#editor-pane).

General application behavior can be configured in the [**General** preference pane](#general-pane).

Custom shortcut bindings can be configured in the [**Shortcuts** preference pane](#shortcuts-pane).

Open-source third-party dependencies can be viewed in the [**Third-Party** preference pane](#third-party-pane).

Privacy policy and network preferences can be reviewed in the [**Privacy** preference pane](#privacy-pane).

## The Basics
Before diving into advanced features, this section introduces standard Markdown basics. If you are already familiar with Markdown, you can skip directly to the [**Markdown** preference pane](#markdown-pane).  

### Line Breaks
To force a line break, put two spaces and a newline (return) at the end of the line.

* This two-line bullet 
won't break

* This two-line bullet  
will break

Here is the code:

```
* This two-line bullet 
won't break

* This two-line bullet  
will break
```

### Strong and Emphasize

**Strong**: `**Strong**` or `__Strong__` (Command-B)  
*Emphasize*: `*Emphasize*` or `_Emphasize_`[^emphasize] (Command-I)

### Headers (like this one!)

	Header 1
	========

	Header 2
	--------

or

	# Header 1
	## Header 2
	### Header 3
	#### Header 4
	##### Header 5
	###### Header 6



### Links and Email
#### Inline
Just put angle brackets around an email and it becomes clickable: <never88gone@gmail.com>  
`<never88gone@gmail.com>`  

Same thing with urls: <https://github.com/never88gone/thlmarkdown>  
` <https://github.com/never88gone/thlmarkdown>`  

Perhaps you want to link some text like this: [糖葫芦MarkDown Website](https://github.com/never88gone/thlmarkdown "Title")  
`[糖葫芦MarkDown Website](https://github.com/never88gone/thlmarkdown "Title")` (The title is optional)  


#### Reference style
Sometimes it looks too messy to include big long urls inline, or you want to keep all your urls together.  

Make [a link][arbitrary_id] `[a link][arbitrary_id]` then on it's own line anywhere else in the file:  
`[arbitrary_id]: https://github.com/never88gone/thlmarkdown "Title"`
  
If the link text itself would make a good id, you can link [like this][] `[like this][]`, then on it's own line anywhere else in the file:  
`[like this]: https://github.com/never88gone/thlmarkdown`  

[arbitrary_id]: https://github.com/never88gone/thlmarkdown "Title"
[like this]: https://github.com/never88gone/thlmarkdown  


### Images
#### Inline
`![Alt Image Text](path/or/url/to.jpg "Optional Title")`
#### Reference style
`![Alt Image Text][image-id]`  
on it's own line elsewhere:  
`[image-id]: path/or/url/to.jpg "Optional Title"`


### Lists

* Lists must be preceded by a blank line (or block element)
* Unordered lists start each item with a `*`
- `-` works too
	* Indent a level to make a nested list
		1. Ordered lists are supported.
		2. Start each item (number-period-space) like `1. `
		42. It doesn't matter what number you use, I will render them sequentially
		1. So you might want to start each line with `1.` and let me sort it out

Here is the code:

```
* Lists must be preceded by a blank line (or block element)
* Unordered lists start each item with a `*`
- `-` works too
	* Indent a level to make a nested list
		1. Ordered lists are supported.
		2. Start each item (number-period-space) like `1. `
		42. It doesn't matter what number you use, I will render them sequentially
		1. So you might want to start each line with `1.` and let me sort it out
```



### Block Quote

> Angle brackets `>` are used for block quotes.  
Technically not every line needs to start with a `>` as long as
there are no empty lines between paragraphs.  
> Looks kinda ugly though.
> > Block quotes can be nested.  
> > > Multiple Levels
>
> Most markdown syntaxes work inside block quotes.
>
> * Lists
> * [Links][arbitrary_id]
> * Etc.

Here is the code:

```
> Angle brackets `>` are used for block quotes.  
Technically not every line needs to start with a `>` as long as
there are no empty lines between paragraphs.  
> Looks kinda ugly though.
> > Block quotes can be nested.  
> > > Multiple Levels
>
> Most markdown syntaxes work inside block quotes.
>
> * Lists
> * [Links][arbitrary_id]
> * Etc.
```
  
  
### Inline Code
`Inline code` is indicated by surrounding it with backticks:  
`` `Inline code` ``

If your ``code has `backticks` `` that need to be displayed, you can double backticks:  
```` ``Code with `backticks` `` ````  (mind the spaces preceding the final set of backticks)


### Block Code
If you indent at least four spaces or one tab, I'll display a code block.

	print('This is a code block')
	print('The block must be preceded by a blank line')
	print('Then indent at least 4 spaces or 1 tab')
		print('Nesting does nothing. Your code is displayed Literally')

I also know how to do something called [Fenced Code Blocks](#fenced-code-block) which I will tell you about later.

### Horizontal Rules
If you type three asterisks `***` or three dashes `---` on a line, I'll display a horizontal rule:

***


## <a name="markdown-pane"></a>The Markdown Preference Pane
This is where I keep all preferences related to how I parse markdown into html.  
![Markdown preferences pane](https://raw.githubusercontent.com/never88gone/THLMarkDown/main/images/%E5%81%8F%E5%A5%BD%E8%AE%BE%E7%BD%AE-MarkDown.png)

### Document Formatting
The ***Smartypants*** extension automatically transforms straight quotes (`"` and `'`) in your text into typographer’s quotes (`“`, `”`, `‘`, and `’`) according to the context. Very useful if you’re a typography freak like I am. Quote and Smartypants are syntactically incompatible. If both are enabled, Quote takes precedence.


### Block Formatting

#### Table

This is a table:

First Header  | Second Header
------------- | -------------
Content Cell  | Content Cell
Content Cell  | Content Cell

You can align cell contents with syntax like this:

| Left Aligned  | Center Aligned  | Right Aligned |
|:------------- |:---------------:| -------------:|
| col 3 is      | some wordy text |         $1600 |
| col 2 is      | centered        |           $12 |
| zebra stripes | are neat        |            $1 |

The left- and right-most pipes (`|`) are only aesthetic, and can be omitted. The spaces don’t matter, either. Alignment depends solely on `:` marks.

#### <a name="fenced-code-block">Fenced Code Block</a>

This is a fenced code block:

```
print('Hello world!')
```

You can also use waves (`~`) instead of back ticks (`` ` ``):

~~~
print('Hello world!')
~~~


You can add an optional language ID at the end of the first line. The language ID will only be used to highlight the code inside if you tick the ***Enable highlighting in code blocks*** option.

I support many popular languages as well as some generic syntax descriptions that can be used if your language of choice is not supported. See [relevant sections on the official site](https://github.com/never88gone/thlmarkdown/features/) for a full list of supported syntaxes.


### Inline Formatting

The following is a list of optional inline markups supported:

Option name         | Markup           | Result if enabled     |
--------------------|------------------|-----------------------|
Intra-word emphasis | So A\*maz\*ing   | So A<em>maz</em>ing   |
Strikethrough       | \~~Much wow\~~   | <del>Much wow</del>   |
Underline [^under]  | \_So doge\_      | <u>So doge</u>        |
Quote [^quote]      | \"Such editor\"  | <q>Such editor</q>    |
Highlight           | \==So good\==    | <mark>So good</mark>  |
Superscript         | hoge\^(fuga)     | hoge<sup>fuga</sup>   |
Autolink            | http://t.co      | <http://t.co>         |
Footnotes           | [\^4] and [\^4]: | [^4] and footnote 4   |

[^4]: You don't have to use a number. Arbitrary things like `[^footy note4]` and `[^footy note4]:` will also work. But they will *render* as numbered footnotes. Also, no need to keep your footnotes in order, I will sort out the order for you so they appear in the same order they were referenced in the text body. You can even keep some footnotes near where you referenced them, and collect others at the bottom of the file in the traditional place for footnotes. 




## <a name="rendering-pane"></a>The Rendering Preference Pane
This is where I keep preferences relating to how I render and style the parsed markdown in the preview window.  
![Rendering preferences pane](https://raw.githubusercontent.com/never88gone/THLMarkDown/main/images/%E5%81%8F%E5%A5%BD%E8%AE%BE%E7%BD%AE-%E6%B8%B2%E6%9F%93.png)

### CSS
You can choose different css files for me to use to render your html. You can even customize or add your own custom css files.

### Syntax Highlighting
You have already seen how I can syntax highlight your fenced code blocks. See the [Fenced Code Block](#fenced-code-block) section if you haven’t! You can also choose different themes for syntax highlighting.

### TeX-like Math Syntax
I can also render TeX-like math syntaxes, if you allow me to.[^math] I can do inline math like this: \\( 1 + 1 \\) or this (in MathML): <math><mn>1</mn><mo>+</mo><mn>1</mn></math>, and block math:

\\[
    A^T_S = B
\\]

or (in MathML)

<math display="block">
    <msubsup><mi>A</mi> <mi>S</mi> <mi>T</mi></msubsup>
    <mo>=</mo>
    <mi>B</mi>
</math>



### Task List Syntax
1. [x] I can render checkbox list syntax
	* [x] I support nesting
	* [x] I support ordered *and* unordered lists
2. [ ] I don't support clicking checkboxes directly in the html window


### Jekyll front-matter
If you like, I can display Jekyll front-matter in a nice table. Just make sure you put the front-matter at the very beginning of the file, and fence it with `---`. For example:

```
---
title: "糖葫芦MarkDown is my friend"
date: 2014-06-06 20:00:00
---
```

### Render newline literally
Normally I require you to put two spaces and a newline (aka return) at the end of a line in order to create a line break. If you like, I can render a newline any time you end a line with a newline. However, if you enable this, markdown that looks lovely when I render it might look pretty funky when you let some *other* program render it.


## <a name="general-pane"></a>The General Preferences Pane

This is where I keep preferences related to application behavior.  
![General preferences pane](https://raw.githubusercontent.com/never88gone/THLMarkDown/main/images/%E5%81%8F%E5%A5%BD%E8%AE%BE%E7%BD%AE-%E9%80%9A%E7%94%A8.png)

The General Preferences Pane allows you to tell me how you want me to behave. For example, do you want me to make sure there is a document open when I launch? You can also tell me if I should constantly update the preview window as you type, or wait for you to hit `command-R` instead. Maybe you prefer your editor window on the right? Or to see the word-count as you type. This is also the place to tell me if you are interested in pre-releases of me, or just want to stick to better-tested official releases.  

## <a name="editor-pane"></a>The Editor Preference Pane
This is where I keep preferences related to the behavior and styling of the editing window.  
![Editor preferences pane](https://raw.githubusercontent.com/never88gone/THLMarkDown/main/images/%E5%81%8F%E5%A5%BD%E8%AE%BE%E7%BD%AE-%E7%BC%96%E8%BE%91%E5%99%A8.png)


### Styling

You can customize the editor's base font, sizing, and color themes. Several built-in themes are provided.

To customize themes, click the ***Reveal*** button to open the theme folder. Please ensure custom themes use the `.styles` extension.

Additionally, you can toggle smart features like auto-completion to optimize your workflow.


## <a name="shortcuts-pane"></a>The Shortcuts Preference Pane

Configure and customize keyboard shortcuts for various operations to fit your typing habits.  
![Shortcuts preferences pane](https://raw.githubusercontent.com/never88gone/THLMarkDown/main/images/%E5%81%8F%E5%A5%BD%E8%AE%BE%E7%BD%AE-%E5%BF%AB%E6%8D%B7%E9%94%AE.png)

You can record or update specific combinations to boost your writing efficiency.

## <a name="third-party-pane"></a>The Third-party Preference Pane

糖葫芦MarkDown is built with the help of excellent open-source communities. You can review the list of third-party libraries and their licenses here.  
![Third-party preferences pane](https://raw.githubusercontent.com/never88gone/THLMarkDown/main/images/%E5%81%8F%E5%A5%BD%E8%AE%BE%E7%BD%AE-%E7%AC%AC%E4%B8%89%E6%96%B9%E7%BB%84%E4%BB%B6.png)

## <a name="privacy-pane"></a>The Privacy Preference Pane

We highly value your privacy. In this pane, you can read our full privacy policy statement.  
![Privacy preferences pane](https://raw.githubusercontent.com/never88gone/THLMarkDown/main/images/%E5%81%8F%E5%A5%BD%E8%AE%BE%E7%BD%AE-%E9%9A%90%E7%A7%81%E6%94%BF%E7%AD%96.png)

Network connections may be used to fetch resources for TeX-like math rendering (CDN-dependent libraries) and auto-update checks. Here, you can learn how we protect your data and configure related options.


## Hack On

That’s about it. Thanks for listening. I’ll be quiet from now on (unless there’s an update about the app—I’ll remind you for that!).

Happy writing!


[^emphasize]: If **Underlines** is turned on, `_this notation_` will render as underlined instead of emphasized 

[^under]: If **Underline** is disabled `_this_` will be rendered as *emphasized* instead of being underlined.

[^quote]: **Quote** replaces literal `"` characters with html `<q>` tags. **Quote** and **Smartypants** are syntactically incompatible. If both are enabled, **Quote** takes precedence. Note that **Quote** is different from *blockquote*, which is part of standard Markdown.

[^math]: Internet connection required.
