### 基础: 标题和段落
HTML的主要工作是编辑文本结构和文本内容（也称为语义semantics），以便浏览器能正确的显示。
大部分的文本结构由标题和段落组成。内容结构化会使读者的阅读体验更轻松，更愉快。
在HTML中，每个段落是通过`<p>`元素标签进行定义的, 比如下面这样：
```
<p>我是段落</p>
```
每个标题（Heading）是通过“标题标签”进行定义的：
```
<h1>我是文章的标题</h1>
```
这里有六个标题元素标签 —— `<h1>、<h2>、<h3>、<h4>、<h5>、<h6>`。每个元素代表文档中不同级别的内容; `<h1>` 表示主标题（the main heading），`<h2>` 表示二级子标题（subheadings），`<h3> `表示三级子标题（sub-subheadings），等等。
#### 编辑结构层次
举例：`<h1>`表示故事的名字，`<h2>`表示每个章节的标题,`<h3>`表示每个章节下的子标题，以此类推。
```
<h1>我是文章的标题</h1>
    <p>我是段落</p>
    <h1>三国演义</h1>
    <p>罗贯中</p>
    <h2>第一回 宴桃园豪杰三结义 斩黄巾英雄首立功</h2>
    <p>话说天下大势，分久必合，合久必分。周末七国分争，并入于秦。及秦灭之后，楚、汉分争，又并入于汉……</p>
    <h2>第二回 张翼德怒鞭督邮 何国舅谋诛宦竖</h2>
    <p>且说董卓字仲颖，陇西临洮人也，官拜河东太守，自来骄傲。当日怠慢了玄德，张飞性发，便欲杀之……</p>
    <h3>却说张飞</h3>
    <p>却说张飞饮了数杯闷酒，乘马从馆驿前过，见五六十个老人，皆在门前痛哭。飞问其故，众老人答曰：“督邮逼勒县吏，欲害刘公；我等皆来苦告，不得放入，反遭把门人赶打！”……</p>
```

#### 为什么我们需要结构化?
文档示例：
```
Quick hummus recipe

This recipe makes quick, tasty hummus, with no messing. It has been adapted from a number of different recipes that I have read over the years.

Hummus is a delicious thick paste used heavily in Greek and Middle Eastern dishes. It is very tasty with salad, grilled meats and pitta breads.

Ingredients

1 can (400g) of chick peas (garbanzo beans)
175g of tahini
6 sundried tomatoes
Half a red pepper
A pinch of cayenne pepper
1 clove of garlic
A dash of olive oil

Instructions

Remove the skin from the garlic, and chop coarsely
Remove all the seeds and stalk from the pepper, and chop coarsely
Add all the ingredients into a food processor
Process all the ingredients into a paste.
If you want a coarse "chunky" hummus, process it for a short time
If you want a smooth hummus, process it for a longer time

For a different flavour, you could try blending in a small measure of lemon and coriander, chili pepper, lime and chipotle, harissa and mint, or spinach and feta cheese. Experiment and see what works for you.

Storage

Refrigerate the finished hummus in a sealed container. You should be able to use it for about a week after you've made it. If it starts to become fizzy, you should definitely discard it.

Hummus is suitable for freezing; you should thaw it and use it within a couple of months.
```
这个文档的主体 （body）中包含了多个内容 — 这些内容`没有做任何标记`，但是编辑时使用了`换行` (输入回车/换行跳转到下一行)处理。然而，当您在浏览器中打开文档时，您会看到文本显示为一整块！
![](http://pt2sht59w.bkt.clouddn.com/blog_imgs/2019-6-15-p1.jpg)
这是因为没有元素给内容结构，所以浏览器不知道什么是标题，什么是段落。此外：
- 用户在阅读网页时，往往会快速浏览以查找相关内容，经常只是阅读开头的标题（我们通常在一个网页上会花费很少的时间 spend a very short time on a web page)。如果用户不能在几秒内看到一些有用的内容，他们很可能会感到沮丧并离开。
- 对您的网页建立索引的搜索引擎将标题的内容视为影响网页搜索排名的重要关键字。没有标题，您的网页在SEO（搜索引擎优化）方面效果不佳。
- 严重视力障碍者通常不会阅读网页；他们用听力来代替。完成这项工作的软件叫做屏幕阅读器（screen reader）。该软件提供了快速访问给定文本内容的方法。在使用的各种技术中，它们通过朗读标题来提供文档的概述，让用户能快速找到他们需要的信息。如果标题不可用，用户将被迫听到整个文档的大声朗读。
- 使用CSS样式化内容，或者使用JavaScript做一些有趣的事情，你需要包含相关内容的元素，所以CSS / JavaScript可以有效地定位它。
因此，我们需要给我们的内容结构标记。

#### 为什么我们需要语义？
我们需要确保使用了正确的元素来给予内容正确的意思、作用以及外形。在这里，`<h1>`元素也是一个语义元素，它给出了包裹在您的页面上用来表示顶级标题的角色（或意义）的文本。
```
<h1>这是一个顶级标题</h1>
```
一般来说，浏览器会给它一个更大的字形来让它看上去像个标题（虽然你可以使用CSS让它变成任何你想要的样式。更重要的是，它的语义值将以多种方式被使用，比如通过搜索引擎和屏幕阅读器（上文提到过的）。

在另一方面，你可以让任一元素看起来像一个顶级标题，如下:
```
<span style="font-size: 32px; margin: 21px 0;">这是顶级标题吗？</span>
```
这是一个`<span>`元素，它没有语义。当您想要对它用CSS（或者JS）时，您可以用它包裹内容，且不需要附加任何额外的意义,我们已经对它使用了CSS来让它看起来像一个顶级标题。然而，由于它没有语义值，所以它不会有任何上文提到的帮助。最好的方法是使用相关的HTML元素来标记这个项目。

--------------------

### 列表 Lists
#### 无序-Unordered
无序的列表被用来标记每个项目。在这里，项目的顺序并不重要 — 让我们看下面的早点清单的例子
```
豆浆
油条
豆汁
焦圈
```
每份无序的清单从`<ul>`元素开始——这元素包裹了清单上所有被列出的项目：
```
<ul>
豆浆
油条
豆汁
焦圈
</ul>
```
效果：
<ul>
豆浆
油条
豆汁
焦圈
</ul>

最后一步就是用`<li>`元素把每个列出的项目分别包裹起来：
```
<ul>
    <li>豆浆</li>
    <li>油条</li>
    <li>豆汁</li>
    <li>焦圈</li>
</ul>
```
效果：
<ul>
    <li>豆浆</li>
    <li>油条</li>
    <li>豆汁</li>
    <li>焦圈</li>
</ul>


#### 有序-Ordered
有序的列表是根据项目的顺序列出来的——让我们以一组方向为例
```
沿着条路走到头
右转
直行穿过第一个十字路口
在第三个十字路口处左转
继续走 300 米，学校就在你的右手边
```
这个标记的结构和无序列表一样，除了你需要用`<ol>`元素将所有项目包裹, 而不是用`<ul>`：
```
<ol>
    <li>沿着条路走到头</li>
    <li>右转</li>
    <li>直行穿过第一个十字路口</li>
    <li>在第三个十字路口处左转</li>
    <li>继续走 300 米，学校就在你的右手边</li>
</ol>
```
效果：
<ol>
    <li>沿着条路走到头</li>
    <li>右转</li>
    <li>直行穿过第一个十字路口</li>
    <li>在第三个十字路口处左转</li>
    <li>继续走 300 米，学校就在你的右手边</li>
</ol>

#### 嵌套列表-Nesting lists
有序列表中嵌套一个无序列表：
```
<ol>
    <li>先用蛋白一个、盐半茶匙及淀粉两大匙搅拌均匀，调成“腌料”，鸡胸肉切成约一厘米见方的碎丁并用“腌料”搅拌均匀，腌渍半小时。</li>
    <li>用酱油一大匙、淀粉水一大匙、糖半茶匙、盐四分之一茶匙、白醋一茶匙、蒜末半茶匙调拌均匀，调成“综合调味料”。</li>
    <li>鸡丁腌好以后，色拉油下锅烧热，先将鸡丁倒入锅内，用大火快炸半分钟，炸到变色之后，捞出来沥干油汁备用。</li>
    <li>在锅里留下约两大匙油，烧热后将切好的干辣椒下锅，用小火炒香后，再放入花椒粒和葱段一起爆香。随后鸡丁重新下锅，用大火快炒片刻后，再倒入“综合调味料”继续快炒。</li>
    <ul>
        <li>如果你采用正宗川菜做法，最后只需加入花生米，炒拌几下就可以起锅了。</li>
        <li>如果你在北方，可加入黄瓜丁、胡萝卜丁和花生米，翻炒后起锅。</li>
    </ul>
</ol>
```
效果：
<ol>
    <li>先用蛋白一个、盐半茶匙及淀粉两大匙搅拌均匀，调成“腌料”，鸡胸肉切成约一厘米见方的碎丁并用“腌料”搅拌均匀，腌渍半小时。</li>
    <li>用酱油一大匙、淀粉水一大匙、糖半茶匙、盐四分之一茶匙、白醋一茶匙、蒜末半茶匙调拌均匀，调成“综合调味料”。</li>
    <li>鸡丁腌好以后，色拉油下锅烧热，先将鸡丁倒入锅内，用大火快炸半分钟，炸到变色之后，捞出来沥干油汁备用。</li>
    <li>在锅里留下约两大匙油，烧热后将切好的干辣椒下锅，用小火炒香后，再放入花椒粒和葱段一起爆香。随后鸡丁重新下锅，用大火快炒片刻后，再倒入“综合调味料”继续快炒。</li>
    <ul>
        <li>如果你采用正宗川菜做法，最后只需加入花生米，炒拌几下就可以起锅了。</li>
        <li>如果你在北方，可加入黄瓜丁、胡萝卜丁和花生米，翻炒后起锅。</li>
    </ul>
</ol>

### 重点强调
#### 强调(斜体)
在HTML中我们用`<em>`（emphasis）元素来标记这样的情况。
```
<p>I am <em>glad</em> you weren't late.</p>
```
<p>I am <em>glad</em> you weren't late.</p>

#### 非常重要（加粗）
在HTML中我们用`<strong>`(strong importance) 元素来标记这样的情况。
```
<P>I am <strong>glad</strong> you weren't late.</P>
```
<P>I am <strong>glad</strong> you weren't late.</P>












