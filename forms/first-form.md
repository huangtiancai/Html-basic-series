### 使用HTML实现我们的表单
为了构建我们的联系人表单，我们将使用以下HTML元素:`<form>`, `<label>`, `<input>`, `<textarea>`, and `<button>`.
```
<form action="/my-handling-form-page" method="POST">
    <div>
        <label for="name">Name:</label>   
        <input type="text" id="name">
    </div>
    <div>
        <label for="mail">E-mail:</label>
        <input type="email" id="mail">
    </div>
    <div>
        <label for="msg">Message:</label>
        <textarea id="msg"></textarea>
    </div>
    <div class="button">
        <button type="submit">提交</button>
    </div>
</form>
```

1. 所有HTML表单都以一个`<form>`元素开始;
2. 支持一些特定的属性来`配置表单`的行为方式。它的所有属性都是`可选`的，但`至少`要设置`action`属性和`method`属性;
- action 属性定义了在提交表单时,应该把所收集的数据送给谁(/那个模块)(URL)去处理。.
- method 属性定义了发送数据的HTTP方法(它可以是“get”或“post”).
3. 使用`<div>`元素可以使我们更加方便地构造我们自己的代码，并且更容易`样式化`
4. 注意在所有`<label>`元素上使用for属性
5. `<input>`元素中，最重要的属性是`type`属性
- 在示例中，我们使用值`text`作为第一个输入——这个`属性的默认值`。它表示一个`基本的单行文本字段`，接受任何类型的文本输入。
- 对于第二个输入，我们使用值`email`，它定义了一个`只接受格式良好`的`电子邮件地址的单行文本字段`。
- 最后一个值将一个基本的文本字段转换为一种“智能”字段，该字段将对用户输入的数据进行一些`检查`。在稍后的表单数据验证文章中，您将了解到表单验证的更多信息
6. 注意`<input/>`和`<textarea></textarea>`的语法。这是HTML的一个奇怪之处。`<input>`标签是一个`空元素`，这意味着它不需要关闭标签。相反， `<textarea>`不是一个空元素，因此必须使用适当的结束标记来关闭它
7. `<input/>`和`<textarea></textarea>`定义默认值的方式不同:
要定义`<input>`的默认值，你必须使用`value`属性;
```
<input type="text" value="default value"/>
```
相反，如果您想定义`<textarea>`的默认值，您只需在`<textarea>`元素的开始和结束标记之间放置默认值，就像这样:
```
<textarea>default value</textarea>
```
8. `<button>`元素
用户在填写完表单后发送数据,这是通过使用`<button>`元素完成的
`<button>`元素也接受一个`type`属性，它接受三个值中的一个:submit, reset或者 button。
- 单击`submit`按钮发送表单的数据到`<form>`元素的action 属性所定义的网页。
- 单击`reset`按钮将所有表单小部件`重新设置为它们的默认值`。从用户体验的角度来看，这被认为是一种糟糕的做法。
- 单击`button`按钮……不会发生任何事！这听起来很傻，但是用JavaScript构建定制按钮非常有用。 

### 向您的web服务器发送表单数据
1. `<form>`元素将定义如何通过`action`属性和`method`属性来发送数据的位置和方式
2. 需要为我们的数据提供一个`名称`(name属性),这些名字对双方都很重要：在`浏览器端`，它告诉浏览器哪个名称提供每个数据，在`服务器端`，它允许服务器按名称处理每个数据块。
3. 在我们的例子中，表单会发送三个已命名的数据块`"user_name"`, `"user_email"`,和`"user_message"`。这些数据将用使用`HTTP POST` 方法,把信息发送到`URL`为 `"/my-handling-form-page`"目录下。

```
<form action="/my-handling-form-page" method="POST">
    <div>
        <label for="name">Name:</label>   
        <input type="text" id="name" name="user_name">
    </div>
    <div>
        <label for="mail">E-mail:</label>
        <input type="email" id="mail" name="user_email">
    </div>
    <div>
        <label for="msg">Message:</label>
        <textarea id="msg" name="user_message"></textarea>
    </div>
    <div class="button">
        <button type="submit">提交</button>
    </div>
    </form>
```





