[HTML元素参考](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element)
这里列出了所有使用 标签 创建的 HTML 元素
### 根元素
元素|描述
---|----
`<html>`|HTML <html> 元素 表示一个HTML文档的根（顶级元素），所以它也被称为根元素。所有其他元素必须是此元素的后代。
### 文档元数据
元数据（Metadata）含有页面的相关信息，包括样式、脚本及数据，能帮助一些软件（例如 搜索引擎、浏览器 等等）更好地运用和渲染页面。对于样式和脚本的元数据，可以直接在网页里定义，也可以链接到包含相关信息的外部文件。
元素|描述
---|----
`<head>`|HTML head 元素 规定文档相关的配置信息（元数据），包括文档的标题，引用的文档样式和脚本等
`<link>`|HTML 中<link>元素规定了外部资源与当前文档的关系。这个元素最常于链接样式表，还能被用来创建站点图标(比如PC端的“favicon”图标和移动设备上用以显示在主屏幕的图标)甚至一些其他事情。
`<meta>`|HTML`<meta>`元素表示那些不能由其它HTML元相关元素 (`<base>, <link>, <script>, <style> 或 <title>`) 之一表示的任何元数据信息.
`<style>`|HTML的`<style>`元素包含文档的样式信息或者文档的部分内容。默认情况下，该标签的样式信息通常是CSS的格式。
`title`|HTML`<title>`元素 定义文档的标题，显示在浏览器的标题栏或标签页上。它只可以包含文本，若是包含有标签，则包含的任何标签都不会被解释。

**详细解析重要的元素：**
- `<head>`元素内的元素有: `<meta>`,`<title>`,`<link>`,`style`,`<script>`等
- `<link>`最常于链接样式表(stylesheet)
    要链接一个外部的样式表，你需要像这样在你的`<head>`中包含一个`<link>`标签:
    ```
    <link href="main.css" rel="stylesheet">
    ```
    在这个例子中，使用了`href`属性设置外部资源的路径，并设置rel属性的值为`stylesheet(样式表)`。rel 的主要功能是表明“关系”——被引用文档与当前文档的关系。[更多链接类型定义](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Link_types)
    再如网站图标的引用:
    ```
    <link rel="icon" href="favicon.ico">
    ```
    link的属性：rel,href,......
    例子:
    1.引入一个css文件
    ```
    <link href="style.css" rel="stylesheet">
    ```
    2.提供可替换的样式表
    ```
    <link href="default.css" rel="stylesheet" title="Default Style">
    <link href="fancy.css" rel="alternate stylesheet" title="Fancy">
    <link href="basic.css" rel="alternate stylesheet" title="Basic">
    ```
    3.样式表加载事件
    你能够通过监听发生在样式表上的事件知道什么时候样式表加载完毕。同样的，你能够通过监听error事件检测到是否在加载样式表的过程中出现错误。
    ```
    <script>
    function sheetLoaded() {
        // Do something interesting; the sheet has been loaded
    }

    function sheetError() {
        alert("An error occurred loading the stylesheet!");
    }
    </script>

    <link rel="stylesheet" href="mystylesheet.css"  onload="sheetLoaded()" onerror="sheetError()">
    ```
    4.预加载例子 [Preloading content with rel="preload"](https://developer.mozilla.org/en-US/docs/Web/HTML/Preloading_content)
    ```
    <head>
        <meta charset="utf-8">
        <title>JS and CSS preload example</title>

        <link rel="preload" href="style.css" as="style">
        <link rel="preload" href="main.js" as="script">

        <link rel="stylesheet" href="style.css">
    </head>

    <body>
        <h1>bouncing balls</h1>
        <canvas></canvas>
        <script src="main.js" defer></script>
    </body>
    ```
    注意：
    - `<link>`标签只能出现在head元素中，然而可以出现多个`<link>`标签
    - HTML 3.2只为link元素定义了href, methods, rel，rev，title，和urn属性
- `<style>`
    属性:type,media,title, scoped..
    示例:
    一个简单的样式表:
    ```
    <style type="text/css">
        body {
            color:blue;
        }
    </style>
    ```
    一个scoped的样式表:
    ```
    <article>
        <div>The scoped attribute allows for you to include style elements mid-document.
                Inside rules only apply to the parent element.</div>
        <section>
            <style>
                p {
                    color:red;
                }
            </style>
            <p>this should be red.</p>
        </section>
    </article>
    ```

### 分区根元素
元素|描述
---|----
`<body>`|HTML body 元素表示文档的内容。`document.body`属性提供了可以轻松访问文档的 body 元素的脚本。

### 内容分区
内容分区元素允许你将文档内容从逻辑上进行组织划分。使用包括页眉(header)、页脚(footer)、导航(nav)和标题(h1~h6)等分区元素，来为页面内容创建明确的大纲，以便区分各个章节的内容。
元素|描述
---|----
`<footer>`|HTML`<footer>`元素表示最近一个章节内容或者根节点（sectioning root ）元素的页脚。一个页脚通常包含该章节作者、版权数据或者与文档相关的链接等信息。
`<nav>`|HTML导航栏 (`<nav>`) 描绘一个含有多个超链接的区域，这个区域包含转到其他页面，或者页面内部其他部分的链接列表.
`<h1>, <h2>, <h3>, <h4>, <h5>, <h6>`|HTML`<h1>–<h6>`标题(Heading)元素呈现了六个不同的级别的标题，`<h1>`级别最高，而`<h6>`级别最低。

**详细解析重要的元素：**
- `<nav>`:HTML导航栏 (`<nav>`) 描绘一个含有多个超链接的区域，这个区域包含转到其他页面，或者页面内部其他部分的链接列表.
    示例:
    ```
    <nav>
        <ul>
            <li><a href="#">Home</a></li>
            <li><a href="#">About</a></li>
            <li><a href="#">Contact</a></li>
        </ul>
    </nav>
    ```
### 文本内容
元素|描述
---|----
`<div>`|HTML`<div>`元素(或 HTML 文档分区元素)是一个通用型的流内容容器，它在语义上不代表任何特定类型的内容，它可以被用来对其它元素进行分组，一般用于样式化相关的需求（使用`class` 或`id`特性) 或者对具有相同特性的一组元素进行分组 (比如 lang)，它应该在没有任何其它`语义元素`可用时才使用 (比如`<article>` 或 `<nav>`) 。
`<ol>`|HTML`<ol>`元素 表示多个有序列表项，通常渲染为有带编号的列表。
`<ul>`|HTML`<ul>`元素（或称 HTML 无序列表元素）表示一个内可含多个元素的无序列表或项目符号列表。
`<li>`|HTML`<li>`元素（或称 HTML 列表条目元素）用于表示列表里的条目。它必须包含在一个父元素里：一个有序列表(`<ol>`)，一个无序列表(`<ul>`)，或者一个菜单 (`<menu>`)。在菜单或者无序列表里，列表条目通常用点排列显示；在有序列表里，列表条目通常在左边显示按升序排列的计数，例如数字或者字母。
`<p>`|HTML`<p>`元素（或者说 HTML 段落元素）表示文本的一个段落。该元素通常表现为一整块与相邻文本分离的文本，或以垂直的空白隔离或以首行缩进。另外，`<p>`是块级元素。

- `<div>`:
    <div>
    <p>这里可以是任何内容，比如 &lt;p&gt;, &lt;table&gt;，一切由你作主。</p>
    </div>

    示例：
    ```
    <div class="divclass">
        <img src="imgs/firefox-icon.png" alt="这是一张图片">
        <p>Beware of the leopard</p>
    </div
    ```
    在 HTML5  中， `<div>` 的 align  特性已经 
    `<p>` 元素的 align 属性已被弃用，请不要使用。

### 内联文本语义
元素|描述
---|----
`<a>`|HTML `<a>` 元素（或称锚元素）可以创建通向其他网页、文件、同一页面内的位置、电子邮件地址或任何其他 URL 的超链接。
`<span>`|HTML`<span>`元素是短语内容的通用行内容器，并没有任何特殊语义。可以使用它来编组元素以达到某种样式意图（通过使用类或者Id属性），或者这些元素有着共同的属性，比如lang。应该在没有其他合适的语义元素时才使用它。`<span>` 与`<div>`元素很相似，但`<div>`是一个 `块元素` 而 `<span>`则是 `行内元素` .

### 图片和多媒体
元素|描述
---|----
`img`|HTML Image 元素（ `<img>` ）代表文档中的一个图像
`<audio>`|HTML `<audio>` 元素用于在文档中表示音频内容。 `<audio>` 元素可以包含多个音频资源， 这些音频资源可以使用 `src` 属性或者`<source>` 元素来进行描述； 浏览器将会选择最合适的一个来使用。对于不支持`<audio>`元素的浏览器，`<audio`>元素也可以作为浏览器不识别的内容加入到文档中。
`<video>`|HTML `<video>`元素 用于在HTML或者XHTML文档中嵌入媒体播放器，用于支持文档内的视频播放。

### 内嵌内容
元素|描述
---|----
`<iframe>`|HTML内联框架元素`<iframe>`表示嵌套的浏览上下文，有效地将另一个HTML页面嵌入到当前页面中。
