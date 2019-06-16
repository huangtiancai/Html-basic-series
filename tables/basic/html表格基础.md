### 什么是表格？
`表格`是由`行`和`列`组成的`结构化`数据集(表格数据)，它能够使你简捷迅速地查找某个表示不同类型数据之间的某种关系的值 
`HTM`L的创建者们提供了一种方法来`构建和呈现web上的表格数据`
### 表格如何工作？
`表格`的一个特点就是`严格`. 通过在`行`和`列`的`标题`之间进行`视觉关联`的方法，就可以让信息能够很简单地被解读出来。
### 创建你的第一个表格
1. 每一个表格的内容都包含在`这两个标签中` : `<table></table>`. 在你的 HTML 的 `<body>` 中添加这些内容。
2. 在表格中，`最小的内容容器`是`单元格`, 是通过 `<td>` 元素创建的 ('td' 代表 'table data'). 把下面的内容添加到你的表格标签(`<table></table>`)中
```
<td>这是第一个单元格</td>
```
如果我们想要一行四个单元格，我们需要把这组标签拷贝三次，更新你表中的内容，让它看起来是这样的:
```
<td>这是第一个单元格</td>
<td>这是第二个单元格</td>
<td>这是第三个单元格</td>
<td>这是第四个单元格</td>
```
你会看到, 单元格不会放置在彼此的下方, 而是自动与同一行上的其他`单元格对齐`. 每个 `<td>` 元素 创建一个`单独单元格`，它们共同组成了第一行。我们添加的每个单元格都使行的长度变长。

如果想让这一行停止增加，并让单元格从第二行开始，我们需要使用 `<tr>`元素 ('tr' 代表 'table row'). 让我们现在来证实一下。

`每一行`都需要一个额外的 `<tr>` 元素来`包装`，`每个单元格`的内容都应该写在 `<td>`中
```
<tr>
    <td>这是第一个单元格</td>
    <td>这是第二个单元格</td>
    <td>这是第三个单元格</td>
    <td>这是第四个单元格</td>
</tr>
<tr>
    <td>这是第二行第一个单元格</td>
    <td>这是第二行第二个单元格</td>
    <td>这是第二行第三个单元格</td>
    <td>这是第二行第四个单元格</td>
</tr>
```

### 使用 `<th>` 元素添加标题
表格中的`标题`是特殊的`单元格`，通常在`行`或`列`的开始处，定义`行`或`列`包含的`数据类型` (举个例子, 看到本篇文章中第一个示例中的 "单数" 或者 "Object"  ). 
为了将表格的标题在`视觉上`和`语义上`都能被识别为`标题`，你可以使用 `<th>` 元素 ('th' 代表 'table header'). 用法和 `<td>`是一样的，除了它表示为标题，不是普通的单元格以外。进入你的 HTML 文件, 将表格中应该是标题的 `<td>` 元素标记的内容，都改为用 `<th>` 元素标记。
原始表格代码：
```
<table>
    <tr>
        <td>Person</td>
        <td>Age</td>
        <td>Score</td>
    </tr>
    <tr>
        <td>Tom</td>
        <td>18</td>
        <td>80</td>
    </tr>
    <tr>
        <td>cat</td>
        <td>20</td>
        <td>78</td>
    </tr>   
</table>
```
效果：
<table>
    <tr>
        <td>Person</td>
        <td>Age</td>
        <td>Score</td>
    </tr>
    <tr>
        <td>Tom</td>
        <td>18</td>
        <td>80</td>
    </tr>
    <tr>
        <td>cat</td>
        <td>20</td>
        <td>78</td>
    </tr>   
</table>
修改后表格的代码：

```
<table>
        <tr>
            <th>Person</th>
            <th>Age</th>
            <th>Score</th>
        </tr>
        <tr>
            <td>Tom</td>
            <td>18</td>
            <td>80</td>
        </tr>
        <tr>
            <td>cat</td>
            <td>20</td>
            <td>78</td>
        </tr>   
    </table>
```
效果（标题明显突出）：
<table>
    <tr>
        <th>Person</th>
        <th>Age</th>
        <th>Score</th>
    </tr>
    <tr>
        <td>Tom</td>
        <td>18</td>
        <td>80</td>
    </tr>
    <tr>
        <td>cat</td>
        <td>20</td>
        <td>78</td>
    </tr>   
</table>

**为什么标题是有用的?**
当标题明显突出的时候，你可以更加简单地找到你想找的数据，设计上也会看起来更好。
注意：
即使你不给表格添加你自己的样式，表格标题也会带有一些默认样式：`加粗`和`居中`，让标题可以`突出显示`。

### 允许单元格跨越多行和列
 表格中的标题和单元格有 `colspan` 和 `rowspan` 属性，这两个属性可以帮助我们实现这些效果。这两个属性接受一个没有单位的数字值，数字决定了它们的`宽度`或`高度`是几个单元格。比如, `colspan="2"` 使一个单元格的宽度是`两个单元格`。
 - `colspan`:合并列（横向合并）
 - `rowspan`:合并行（上下合并）

 ### 为表格中的`列`提供共同的样式
HTML有一种方法可以定义整列数据的样式信息：就是 `<col>` 和 `<colgroup>` 元素。 它们存在是因为如果你想让`一列`中的每个数据的样式都一样，那么你就要为每个数据都添加一个样式，通常需要在列中的每个 `<td>` 或 `<th>` 上定义样式，或者使用一个`复杂的选择器`，比如 :`nth-child()`。
```
<table>
    <tr>
        <th>Person</th>
        <th style="background-color: tomato">Age</th>
    </tr>
    <tr>
        <td>Tom</td>
        <td style="background-color: tomato">18</td>
    </tr>
    <tr>
        <td>cat</td>
        <td style="background-color: tomato">20</td>
    </tr>   
</table>
```
效果：
<table>
    <tr>
        <th>Person</th>
        <th style="background-color: tomato">Age</th>
    </tr>
    <tr>
        <td>Tom</td>
        <td style="background-color: tomato">18</td>
    </tr>
    <tr>
        <td>cat</td>
        <td style="background-color: tomato">20</td>
    </tr>   
</table>
使用colgroup-col:
```
<table>
    <colgroup>
        <col style="background-color: yellow" span="2">
    </colgroup>
    <tr>
        <th>Person</th>
        <th>Age</th>
    </tr>
    <tr>
        <td>Tom</td>
        <td>18</td>
    </tr>
    <tr>
        <td>cat</td>
        <td>20</td>
    </tr>   
</table>
```
<table>
    <colgroup>
        <col style="background-color: yellow" span="2">
    </colgroup>
    <tr>
        <th>Person</th>
        <th>Age</th>
    </tr>
    <tr>
        <td>Tom</td>
        <td>18</td>
    </tr>
    <tr>
        <td>cat</td>
        <td>20</td>
    </tr>   
</table>

#### 动手练习: colgroup and col
