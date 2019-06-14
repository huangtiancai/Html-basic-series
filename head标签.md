#### 什么是HTML头部?
```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>My test page</title>
  </head>
  <body>
    <p>This is my page</p>
  </body>
</html>
```
HTML头部是包含在`<head>`元素里面的内容。不像`<body>`元素的内容可以显示在浏览器中，元素head 里面的内容不会在浏览器中显示，它的作用是包含一些页面的元数据.

#### 增加一个标题
我们之前已经看到了`<title>`，它可以用来给 html 文档添加一个标题。你可能会将它和给 body 添加标题的`<h1>`元素混淆，有些时候 h1 也会被称作网页标题。但是它们是不同的。
当被加载到浏览器中的时候，元素`<h1>`会出现在页面中 —— 通常它应该在一个页面中只被使用一次，它被用来标记你的页面内容的标题（故事的标题，新闻标题或者任何适当的方式）。
元素`<title>`是用来表示整个HTML文档大致内容的元数据（不是文档的内容）。

#### 元数据：<meta>元素
元数据就是描述数据的数据，而HTML有一个“官方的”方式来为一个文档添加元数据——`<meta>`元素。当然，其他在这篇文章中提到的东西也可以被当作元数据。有很多不同种类的`<meta>`元素可以被包含进你的页面的`<head>`元素.
##### 指定你的文档中字符的编码:
```
<meta charset="utf-8">
```
这个元素简单的指定了文档的字符编码 —— 在这个文档中被允许使用的字符集。 utf-8 是一个通用的字符集，它包含了任何人类语言中的大部分的字符。 这意味着你的web页面可以显示任意的语言；所以对于你的每一个页面，使用这个设置是很好的!
比如说，如果你将你的字符集设置为 ISO-8859-1 （拉丁字母的字符集），那么你的页面会是乱码的：
```
<p>Japanese example: ご飯が熱い。</p>
```

##### 添加作者和描述
许多`<meta>`元素包含了name和content特性：
- name:指定了meta 元素的类型； 说明该元素包含了什么类型的信息。
- content:指定了实际的元数据内容。
这两个meta 元素对于定义你的页面的作者和提供页面的内容描述是很有用的 。让我们看一个例子：
```
<meta name="author" content="Chris Mills">
<meta name="description" content="The MDN Learning Area aims to provide
complete beginners to the Web with all they need to know to get
started with developing web sites and applications.">
```

指定作者在某些情况下是很有用的：如果你需要联系页面的作者，问一些关于页面内容的问题。 一些内容管理系统能够自动获取页面作者的信息，然后用于某种目的。
指定包含关于页面内容的关键字的页面内容的描述是很有用的，因为它可能或让你的页面在搜索引擎的相关的搜索出现得更多 （这些行为术语上被称为 Search Engine Optimization, or `SEO`.）

##### 实践操作:在搜索引擎中description的使用
`description`也被使用在搜索引擎显示的结果页中。下面通过一个例子来说明:
1. 访问[MDN Web Docs](https://developer.mozilla.org/zh-CN/)
2. 查看网页源代码
3. 找到description的meta标签。就和如下展示的这样:
```
<title>MDN Web 文档</title>

<meta name="description" content="MDN Web Docs 网站提供开放网络（Open Web）技术有关的信息，包括用于网站和渐进式网络应用的 HTML、CSS 和 API。它还记录了一些用于 Mozilla 产品的面向开发者的文档，例如 Firefox 开发者工具。">
```
4.上述的description`<meta>`and`<title>`元素将在搜索结果里显示

##### 其他类型的metadata
当你在网站上查看源码时，你也会发现其他类型的元数据。你在网站上看到的许多功能都是专有创作，旨在向某些网站(如社交网站)提供可使用的特定信息。
例如，Facebook 编写的元数据协议为网站提供了更丰富的元数据。在 MDN 源代码中，你会发现：
```
<meta property="og:image" content="https://developer.mozilla.org/static/img/opengraph-logo.72382e605ce3.png">

<meta property="og:description" content="MDN Web Docs 网站提供开放网络（Open Web）技术有关的信息，包括用于网站和渐进式网络应用的 HTML、CSS 和 API。它还记录了一些用于 Mozilla 产品的面向开发者的文档，例如 Firefox 开发者工具。">

<meta property="og:title" content="MDN Web Docs">
```
上面代码展现的一个效果就是，当你在Facebook上链接到MDN时，该链接将显示一个图像和描述：这为用户提供更丰富的体验。

Twitter 还拥有自己的类型的专有元数据协议，当网站的 URL 显示在 twitter.com 上时，它具有相似的效果。例如下面：
```
<meta name="twitter:title" content="MDN Web Docs">
```

#### 在你的站点增加自定义图标
为了进一步丰富你的网站设计，你可以在元数据中添加对自定义图标的引用，这些将在特定的场合中显示。
这个不起眼的图标已经存在很多很多年了，16 x 16 像素是这种图标的第一种类型。你可以看见这些图标出现在浏览器每一个打开的页面中的标签页中中以及在书签面板中的书签页面中。
将以下行添加到HTML`<head>`中以引用它：
```
<link rel="shortcut icon" href="favicon.ico" type="image/x-icon">
or
<link rel="icon" href="favicon.ico" type="image/x-icon" />
```
如今还有很多其他的图标类型可以考虑。 例如，你可以在 MDN 主页的源代码中找到它：
```
<!-- third-generation iPad with high-resolution Retina display: -->
<link rel="apple-touch-icon-precomposed" sizes="144x144" href="https://developer.mozilla.org/static/img/favicon144.e7e21ca263ca.png">
<!-- iPhone with high-resolution Retina display: -->
<link rel="apple-touch-icon-precomposed" sizes="114x114" href="https://developer.mozilla.org/static/img/favicon114.d526f38b09c5.png">
<!-- first- and second-generation iPad: -->
<link rel="apple-touch-icon-precomposed" sizes="72x72" href="https://developer.mozilla.org/static/img/favicon72.cc65d1d762a0.png">
<!-- non-Retina iPhone, iPod Touch, and Android 2.1+ devices: -->
<link rel="apple-touch-icon-precomposed" href="https://developer.mozilla.org/static/img/favicon57.de33179910ae.png">
<!-- basic favicon -->
<link rel="shortcut icon" href="https://developer.mozilla.org/static/img/favicon32.7f3da72dcea1.png">
```















