##  Bootstrap学习笔记(二) 表单

表单主要功能是用来与用户做交流的一个网页控件，良好的表单设计能够让网页与用户更好的沟通。表单中常见的元素主要包括：**文本输入框**、**下拉选择框、单选按钮、复选按钮**、**文本域**和**按钮**等。其中每个控件所起的作用都各不相同，而且不同的浏览器对表单控件渲染的风格都各有不同。

对于基础表单，Bootstrap并未对其做太多的定制性效果设计，仅仅对表单内的**fieldset**、**legend**、**label**标签进行了定制。

主要将这些元素的**margin**、**padding**和**border**等进行了细化设置。

当然表单除了这几个元素之外，还有**input**、**select**、**textarea**等元素，在Bootstrap框架中，通过定制了一个类名`**form-control**`，也就是说，如果这几个元素使用了类名“form-control”，将会实现一些设计上的定制效果。

**1、宽度变成了100%**

**2、设置了一个浅灰色（#ccc）的边框**

**3、具有4px的圆角**

**4、设置阴影效果，并且元素得到焦点之时，阴影和边框效果会有所变化**

**5、设置了placeholder的颜色为#999**

![img](http://img.mukewang.com/53b230bb0001cea602970184.jpg)

```
<form role="form">
    <div class="form-group">
        <label for="exampleInputEmail1">邮箱</label>
        <input type="email" class="form-control" id="exampleInputEmail" placeholder="请输入您的邮箱地址">
    </div>
    <div class="form-group">
        <label for="exampleInputPassword1">密码</label>
        <input type="password" class="form-control" id="exampleInputPassword1" placeholder="请输入您的邮箱密码">
    </div>
    <div class="checkbox">
        <label>
            <input type="checkbox" >记住密码
        </label>
    </div>
    <button type="submit" class="btn btn-default">进入邮箱</button>
</form>
```

**3-2 水平表单**

Bootstrap框架默认的表单是垂直显示风格，在Bootstrap框架中要实现水平表单效果，必须满足以下两个条件：
　　1、在<form>元素是使用类名“**form-horizontal**”。
　　2、配合Bootstrap框架的网格系统。

　　在<form>元素上使用类名“**form-horizontal**”主要有以下几个作用：
　　1、设置表单控件padding和margin值。
　　2、改变“form-group”的表现形式，类似于网格系统的“row”。

```
<form class="form-horizontal" role="form">
    <div class="form-group">
        <label for="inputEmail3" class="col-sm-2 control-label">邮箱</label>
        <div class="col-sm-10">
            <input type="email" class="form-control" id="inputEmail3" placeholder="请输入您的邮箱地址">
        </div>
    </div>
    <div class="form-group">
        <label for="inputPassword3" class="col-sm-2 control-label">密码</label>
        <div class="col-sm-10">
            <input type="password" class="form-control" id="inputPassword3" placeholder="请输入您的邮箱密码">
        </div>
    </div>
    <div class="form-group">
        <div class="col-sm-offset-2 col-sm-10">
            <div class="checkbox">
                <label>
                    <input type="checkbox">记住密码
                </label>
            </div>
        </div>
    </div>
    <div class="form-group">
        <div class="col-sm-offset-2 col-sm-10">
            <button type="submit" class="btn btn-default">进入邮箱</button>
        </div>
    </div>
</form><form class="form-horizontal" role="form">
    <div class="form-group">
        <label for="inputEmail3" class="col-sm-2 control-label">邮箱</label>
        <div class="col-sm-10">
            <input type="email" class="form-control" id="inputEmail3" placeholder="请输入您的邮箱地址">
        </div>
    </div>
    <div class="form-group">
        <label for="inputPassword3" class="col-sm-2 control-label">密码</label>
        <div class="col-sm-10">
            <input type="password" class="form-control" id="inputPassword3" placeholder="请输入您的邮箱密码">
        </div>
    </div>
    <div class="form-group">
        <div class="col-sm-offset-2 col-sm-10">
            <div class="checkbox">
                <label>
                    <input type="checkbox">记住密码
                </label>
            </div>
        </div>
    </div>
    <div class="form-group">
        <div class="col-sm-offset-2 col-sm-10">
            <button type="submit" class="btn btn-default">进入邮箱</button>
        </div>
    </div>
</form>
```

![img](https://images2015.cnblogs.com/blog/959898/201605/959898-20160519185846388-1190021874.png)

**3-3内联表单**

有时候我们需要将表单的控件都在一行内显示，类似这样的：![img](http://img.mukewang.com/53b2532a000107b003190032.jpg)

只需要在<form>元素中添加类名“form-inline”即可。
内联表单实现原理非常简单，欲将表单控件在一行显示，就需要将表单控件设置成内联块元素（display:inline-block）。

如果你要在input前面添加一个label标签时，会导致input换行显示。如果你必须添加这样的一个label标签，并且不想让input换行，你需要将label标签也放在容器“form-group”中，如：

```
<div class="form-group">
    <label class="sr-only" for="exampleInputEmail2">Email address</label>
</div>
<div class="form-group">
    <inputtype="email" class="form-control" id="exampleInputEmail2" placeholder="Enter email">
</div>
```

源码：

```
.sr-only {
position: absolute;
width: 1px;
height: 1px;
padding: 0;
margin: -1px;
overflow: hidden;
clip: rect(0, 0, 0, 0);
border: 0;
}
```

注意：如果没有为输入控件设置label标签，**屏幕阅读器**将无法正确识别。

**3-4表单控件(输入框input)**

每一个表单都是由表单控件组成。离开了控件，表单就失去了意义。在Bootstrap中使用input时也必须添加type类型，如果没有指定type类型，将无法得到正确的样式，因为Bootstrap框架都是通过**input[type=“?”]**(其中?号代表type类型，比如说text类型，对应的是**input[type=“text”]**)的形式来定义样式的。

为了让控件在各种表单风格中样式不出错，需要添加类名“**form-control**”，如：

```
<form role="form">
<div class="form-group">
<input type="email" class="form-control" placeholder="Enter email">
</div>
</form>
```

![img](https://images2015.cnblogs.com/blog/959898/201605/959898-20160519195646982-709166274.png)



**3-5表单控件(下拉选择框select)**

Bootstrap框架中的下拉选择框使用和原始的一致，多行选择设置**multiple**属性的值为**multiple**。Bootstrap框架会为这些元素提供统一的样式风格。如：

```
<form role="form">
<div class="form-group">
  <select class="form-control">
    <option>1</option>
    <option>2</option>
    <option>3</option>
    <option>4</option>
    <option>5</option>
  </select>
  </div>
  <div class="form-group">
  <select multiple class="form-control">
    <option>1</option>
    <option>2</option>
    <option>3</option>
    <option>4</option>
    <option>5</option>
  </select>
</div>
</form>
```

![img](http://img.mukewang.com/53b257ea000136bd02570072.jpg)

**3-6表单控件(文本域textarea)**

文本域和原始使用方法一样，设置**rows**可定义其高度，设置**cols**可以设置其宽度。但如果**textarea**元素中添加了类名“**form-control**”类名，则无需设置cols属性。因为Bootstrap框架中的“form-control”样式的表单控件宽度为**100%**或**auto**。

```
<form role="form">
  <div class="form-group">
    <textarea class="form-control" rows="3"></textarea>
  </div>
</form>
```

![img](http://img.mukewang.com/53b25d4d0001dbb503010055.jpg)

**3-7表单控件(复选框checkbox和单选择按钮radio)**

Bootstrap框架中checkbox和radio有点特殊，Bootstrap针对他们做了一些特殊化处理，主要是checkbox和radio与label标签配合使用会出现一些小问题（最头痛的是对齐问题）。使用Bootstrap框架，开发人员无需考虑太多，只需要按照下面的方法使用即可。

```
<form role="form">
	<div class="checkbox">
		<label>
			<input type="checkbox" value="">记住密码
		</label>
	</div>
	<div class="radio">
		<label>
			<input type="radio" name="optionsRadios" id="optionsRadios1" 				value="love" checked>喜欢
		</label>
	</div>
	<div class="radio">
		<label>
			<input type="radio" name="optionsRadios" id="optionsRadios2" 				value="hate">不喜欢
		</label>
	</div>
</form>
```

![img](http://img.mukewang.com/53b25edb0001faae02520102.jpg)

从上面的示例，我们可以得知：
1、不管是checkbox还是radio都使用label包起来了
2、checkbox连同label标签放置在一个名为“.checkbox”的容器内
3、radio连同label标签放置在一个名为“.radio”的容器内
在Bootstrap框架中，主要借助“.checkbox”和“.radio”样式，来处理复选框、单选按钮与标签的对齐方式。

 **3-8表单控件(复选框和单选框按钮水平排列)**

有时候，为了布局的需要，将复选框和单选按钮需要水平排列。Bootstrap框架也做了这方面的考虑：
**1、如果checkbox需要水平排列，只需要在label标签上添加类名“checkbox-inline”
2、如果radio需要水平排列，只需要在label标签上添加类名“radio-inline”**

```
<form role="form">
  <div class="form-group">
    <label class="checkbox-inline">
      <input type="checkbox"  value="option1">游戏
    </label>
    <label class="checkbox-inline">
      <input type="checkbox"  value="option2">摄影
    </label>
    <label class="checkbox-inline">
    <input type="checkbox"  value="option3">旅游
    </label>
  </div>
  <div class="form-group">
    <label class="radio-inline">
      <input type="radio"  value="option1" name="sex">男性
    </label>
    <label class="radio-inline">
      <input type="radio"  value="option2" name="sex">女性
    </label>
    <label class="radio-inline">
      <input type="radio"  value="option3" name="sex">中性
    </label>
  </div>
</form>
```

![img](http://img.mukewang.com/53b2649f00011bae01920069.jpg)

**3-9表单控件(按钮)**

按钮也是表单重要控件之一,制作按钮通常使用下面代码来实现：

 ![☑](https://www.imooc.com/static/moco/v1.0/images/face/36x36/2611.png) **input[type=“submit”]**

 ![☑](https://www.imooc.com/static/moco/v1.0/images/face/36x36/2611.png) **input[type=“button”]**

 ![☑](https://www.imooc.com/static/moco/v1.0/images/face/36x36/2611.png) **input[type=“reset”]**

 ![☑](https://www.imooc.com/static/moco/v1.0/images/face/36x36/2611.png) **<button>**

在Bootstrap框架中的按钮都是采用<button>来实现。

有关于Bootstrap中按钮如何制作，在这里不做过多阐述，因为按钮也是Bootstrap框架中核心部分之一，后面我们专门有一节内容来介绍Bootstrap的按钮。

这里先让大家看看Bootstrap的按钮长成什么样：

![img](http://img.mukewang.com/53b266f800010e4703160035.jpg)

```
<table class="table table-bordered table-striped">
        <thead>
            <tr>
                <th>Button</th>
                <th>class=""</th>
                <th>Description</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td><button class="btn" href="#">Default</button></td>
                <td><code>btn</code></td>
                <td>Standard gray button with gradient</td>
            </tr>
            <tr>
                <td><button class="btn btn-primary" href="#">Primary</button></td>
                <td><code>btn btn-primary</code></td>
                <td>Provides extra visul weight and identifies the primary action in a set of buttons</td>
            </tr>
            <tr>
                <td><button class="btn btn-info" href="#">Info</button></td>
                <td><code>btn btn-info</code></td>
                <td>Used as an alternative to the default styles</td>
            </tr>
            <tr>
                <td><button class="btn btn-success" href="#">Success</button></td>
                <td><code>btn btn-success</code></td>
                <td>Indicates a successful or positive action</td>
            </tr>
            <tr>
                <td><button class="btn btn-warning" href="#">Warning</button></td>
                <td><code>btn btn-warning</code></td>
                <td>Indicates caution should be taken with this action</td>
            </tr>
            <tr>
                <td><button class="btn btn-danger" href="#">Danger</button></td>
                <td><code>btn btn-danger</code></td>
                <td>Indicates a dangerous or potentially negative action</td>
            </tr>
            <tr>
                <td><button class="btn btn-inverse" href="#">Inverse</button></td>
                <td><code>btn btn-inverse</code></td>
                <td>Alternate dark gray button, not tied to a semantic action or use</td>
            </tr>
        </tbody>
    </table>
```

![img](https://images2015.cnblogs.com/blog/959898/201605/959898-20160519214653123-1373835166.png)

**3-10表单控件大小**

前面看到的表单控件都正常的大小。可以通过设置控件的**height，line-height，padding**和**font-size**等属性来实现控件的高度设置。不过Bootstrap框架还提供了两个不同的类名，用来控制表单控件的高度。这两个类名是：
**1、input-sm:让控件比正常大小更小
2、input-lg:让控件比正常大小更大**

这两个类适用于表单中的**input**，**textarea**和**select**控件，具体使用如下：

```
<input class="form-control input-lg" type="text" placeholder="添加.input-lg，控件变大">
<input class="form-control" type="text" placeholder="正常大小">
<input class="form-control input-sm" type="text" placeholder="添加.input-sm，控件变小">
```

源码：

```
.input-sm {
height: 30px;
padding: 5px 10px;
font-size: 12px;
line-height: 1.5;
border-radius: 3px;
}
select.input-sm {
height: 30px;
line-height: 30px;
}
textarea.input-sm,
select[multiple].input-sm {
height: auto;
}
.input-lg {
height: 46px;
padding: 10px 16px;
font-size: 18px;
line-height: 1.33;
border-radius: 6px;
}
select.input-lg {
height: 46px;
line-height: 46px;
}
textarea.input-lg,
select[multiple].input-lg {
height: auto;
}
```

从上面的源码中不难发现，不管是“input-sm”还是“input-lg”仅对控件高度做了处理。但往往很多时候，我们需要控件宽度也要做一定的变化处理。这个时候就要借住Bootstrap框架的**网格系统**。所以你要控制表单宽度，可以像下面这样使用：

```
<form role="form" class="form-horizontal">
  <div class="form-group">
  <div class="col-xs-4">
    <input class="form-control input-lg" type="text" placeholder=".col-xs-4">
  </div>
  <div class="col-xs-4">
    <input class="form-control input-lg" type="text" placeholder=".col-xs-4">
  </div>
  <div class="col-xs-4">
    <input class="form-control input-lg" type="text" placeholder=".col-xs-4">
  </div>
  </div>
    …
</form>
```

![img](https://images2015.cnblogs.com/blog/959898/201605/959898-20160519220948357-1601679423.png)

**3-11表单控件状态(焦点状态)**

**表单状态的作用：**

每一种状态都能给用户传递不同的信息，比如表单有焦点的状态可以告诉用户可以输入或选择东西，禁用状态可以告诉用户不可以输入或选择东西，还有就是表单控件验证状态，可以告诉用户的操作是否正确等。那么在Bootstrap框架中的表单控件也具备这些状态。

焦点状态是通过伪类“:focus”来实现。Bootstrap框架中表单控件的焦点状态删除了**outline**的默认样式，重新添加阴影效果。

要让控件在焦点状态下有上面样式效果，需要给控件添加类名“form-control”：![img](http://img.mukewang.com/53b271e700018f8a02780042.jpg)

在Bootstrap框架中，**file**、**radio**和**checkbox**控件在焦点状态下的效果也与普通的input控件不太一样，主要是因为Bootstrap对他们做了一些特殊处理：

```
input[type="file"]:focus,
input[type="radio"]:focus,
input[type="checkbox"]:focus {
outline: thin dotted;
outline: 5px auto -webkit-focus-ring-color;
outline-offset: -2px;
}
```

**3-12表单控件状态(禁用状态)**

Bootstrap框架的表单控件的禁用状态和普通的表单禁用状态实现方法是一样的，在相应的表单控件上添加属性“disabled”。和其他表单的禁用状态不同的是，Bootstrap框架做了一些样式风格的处理：

```
.form-control[disabled],
.form-control[readonly],
fieldset[disabled] .form-control {
cursor: not-allowed;
background-color: #eee;
opacity: 1;
}
```

使用方法为：只需要在需要禁用的表单控件上加上“disabled”即可：

```
<input class="form-control" type="text" placeholder="表单已禁用，不能输入" disabled>
```

**在Bootstrap框架中，如果fieldset设置了disabled属性，整个域都将处于被禁用状态。**![img](http://img.mukewang.com/53b27b2200010df702890118.jpg)

**对于整个禁用的域中，如果legend中有输入框的话，这个输入框是无法被禁用的。**

**3-13表单控件状态(验证状态)**

在制作表单时，不免要做表单验证。同样也需要提供验证状态样式，在Bootstrap框架中同样提供这几种效果。
1、.has-warning:警告状态（黄色）
2、.has-error：错误状态（红色）
3、.has-success：成功状态（绿色）
使用的时候只需要**在form-group容器上对应添加状态类名**。

很多时候，在表单验证的时候，不同的状态会提供不同的 icon，比如成功是一个对号（√），错误是一个叉号（×）等。在Bootstrap框中也提供了这样的效果。如果你想让表单在对应的状态下显示 icon 出来，只需要在对应的状态下添加类名“**has-feedback**”。请注意，此类名要与“**has-error**”、“**has-warning**”和“**has-success**”在一起。在 Bootstrap 的小图标都是使用**@font-face**来制作。而且必须在表单中添加了一个 span 元素。![img](https://images2015.cnblogs.com/blog/959898/201605/959898-20160520131143076-326761420.png)

**3-14表单提示信息**

平常在制作表单验证时，要提供不同的提示信息。在Bootstrap框架中也提供了这样的效果。使用了一个"help-block"样式，将提示信息以块状显示，并且显示在控件底部。在Bootstrap V2.x版本中还提供了一个行内提示信息，其使用了类名“help-inline”。一般让提示信息显示在控件的后面，也就是同一水平显示。如果你想在BootstrapV3.x版本也有这样的效果，你可以添加这段代码：

```
.help-inline{
  display:inline-block;
  padding-left:5px;
  color: #737373;
}
```

结束语：有关于Bootstrap框架中表单的运用除了按钮部分，到此就算是介绍完了。如果你觉得这样的表单效果并不是你需要的，你完全可以通过**forms.less**或者**_forms.scss**文件进行定制，然后重新编译就可以得到你需要的表单效果。在接下来的一节中，我们Bootstrap框架中另一个核心内容——**按钮**。![img](https://images2015.cnblogs.com/blog/959898/201605/959898-20160520134952294-938439402.png)

**3-15按钮**

按钮是Bootstrap框架核心内容之一

```
    <button class="btn" type="button">基础按钮.btn</button>
    <button class="btn btn-default" type="button">默认按钮.btn-default</button>
    <button class="btn btn-primary" type="button">主要按钮.btn-primary</button>
    <button class="btn btn-success" type="button">成功按钮.btn-success</button>
    <button class="btn btn-info" type="button">信息按钮.btn-info</button>
    <button class="btn btn-warning" type="button">警告按钮.btn-warning</button>
    <button class="btn btn-danger" type="button">危险按钮.btn-danger</button>
    <button class="btn btn-link" type="button">链接按钮.btn-link</button>
```

![img](https://images2015.cnblogs.com/blog/959898/201605/959898-20160520140013904-895164585.png)

**3-16基本按钮**

```
<button class="btn" type="button">我是一个基本按钮</button>
```

　　![img](https://images2015.cnblogs.com/blog/959898/201605/959898-20160520140423263-358535658.png)

**3-17多标签支持**

一般制作按钮除了使用<button>标签元素之外，还可以使用<input type="submit">和<a>标签等。同样，在Bootstrap框架中制作按钮时，除了刚才所说的这些标签元素之外，还可以使用在其他的标签元素上，唯一需要注意的是，要在制作按钮的标签元素上添加类名“btn”。如果不添加是不会有任何按钮效果。

```
<button class="btn btn-default" type="button">button标签按钮</button>
<input type="submit" class="btn btn-default" value="input标签按钮"/>
<a href="##" class="btn btn-default">a标签按钮</a>
<span class="btn btn-default">span标签按钮</span>
<div class="btn btn-default">div标签按钮</div>
```

运行效果如下或查看右侧结果窗口：

[![img](http://img.mukewang.com/53b287f800014bc402460068.jpg)](http://img.mukewang.com/53b287f800014bc402460068.jpg)

注意：虽然在Bootstrap框架中使用任何标签元素都可以实现按钮风格，但个人并不建议这样使用，为了避免浏览器兼容性问题，个人强烈建议使用**button**或**a**标签来制作按钮。

**3-18默认按钮**

ootstrap框架首先通过基础类名“**.btn**”定义了一个基础的按钮风格，然后通过“**.btn-default**”定义了一个默认的按钮风格。默认按钮的风格就是在基础按钮的风格的基础上修改了按钮的背景颜色、边框颜色和文本颜色。使用**默认按钮风格**也非常的简单，只需要在基础按钮“**btn**”的基础上增加类名“**btn-default**”即可：

```
<button class="btn btn-default" type="button">默认按钮</button>
```

　　显示效果如下图所示:

　　![img](https://images2015.cnblogs.com/blog/959898/201605/959898-20160520140916091-240653988.png)

**3-19定制风格**　

　　在Bootstrap框架中除了默认的按钮风格之外，还有其他六种按钮风格，每种风格的其实都一样，不同之处就是按钮的背景颜色、边框颜色和文本颜色。在Bootstrap框架中不同的按钮风格都是通过不同的类名来实现，在使用过程中，开发者只需要选择不同的类名即可。![img](http://img.mukewang.com/53b367d10001846a08020810.jpg)

使用起来就很简单，就像前面介绍的默认按钮一样的使用方法，只需要在基础按钮“.btn”基础上追加**对应的类名**，就可以得到需要的按钮风格

**3-20按钮大小**![img](http://img.mukewang.com/53b36a7600014af106910605.jpg)

从上表中不难发现，在Bootstrap框架中控制按钮的大小都是通过修改按钮的**padding**、**line-height**、**font-size**和**border-radius**几个属性。

**3-21块状按钮**

有时候在制作按钮的时候需要按钮宽度充满整个父容器**（width:100%）**，特别是在移动端的制作中,Bootstrap框架中提供了一个类名“**btn-block**”。按钮使用这个类名就可以让按钮充满整个容器，并且这个按钮不会有任何的padding和margin值。在实际当中，常把这种按钮称为块状按钮。

```
    <button class="btn btn-primary btn-lg btn-block" type="button">大型按钮.btn-lg</button>
    <button class="btn btn-primary btn-block" type="button">正常按钮</button>
    <button class="btn btn-primary btn-sm btn-block" type="button">小型按钮.btn-sm</button>
    <button class="btn btn-primary btn-xl btn-block" type="'button">超小型按钮.b
```

![img](https://images2015.cnblogs.com/blog/959898/201605/959898-20160520155402076-1967905327.png)

**3-22按钮状态--活动状态**

　　Bootstrap框架针对按钮的状态做了一些特殊处理。在Bootstrap框架中针对按钮的状态效果主要分为两种：**活动状态**和**禁用状态**。　Bootstrap按钮的活动状态主要包括按钮的**悬浮状态(:hover)**，**点击状态(:active)**和**焦点状态（:focus）**几种。而且不同风格下的按钮都具有这几种状态效果，只是颜色做了一定的调整

源码：

```
.btn:focus,
.btn:active:focus,
.btn.active:focus {
outline: thin dotted;
outline: 5px auto -webkit-focus-ring-color;
outline-offset: -2px;
}
.btn:hover,
.btn:focus {
color: #333;
text-decoration: none;
}
.btn:active,
.btn.active {
background-image: none;
outline: 0;
  -webkit-box-shadow: inset 0 3px 5px rgba(0, 0, 0, .125);
box-shadow: inset 0 3px 5px rgba(0, 0, 0, .125);
}
```

**3-23按钮状态--禁用状态**　　

在Bootstrap框架中，要禁用按钮有两种实现方式：

　　**方法1：**在标签中添加disabled属性

　　**方法2：**在元素标签中添加类名“disabled”

　　两者的主要区别是：

　　“**.disabled**”样式不会禁止按钮的默认行为，比如说提交和重置行为等。如果想要让这样的禁用按钮也能禁止按钮的默认行为，则需要通过JavaScript这样的语言来处理。对于<a>标签也存在类似问题，如果通过类名“.disable”来禁用按钮，其链接行为是无法禁止。而在元素标签中添加“disabled”属性的方法是可以禁止元素的默认行为的。

```
  <button class="btn btn-primary btn-lg btn-block" type="button" disabled="disabled">通过disabled属性禁用按钮</button>
    <button class="btn btn-primary btn-block disabled" type="button">通过添加类名disabled禁用按钮</button>
    <button class="btn btn-primary btn-sm btn-block" type="button">未禁用的按钮</button>
```

![img](https://images2015.cnblogs.com/blog/959898/201605/959898-20160520160831294-204363436.png)

**3-24图像**

　在Bootstrap框架中对于图像的样式风格提供以下几种风格：

　　**1、img-responsive：**响应式图片，主要针对于响应式设计
　　**2、img-rounded：**圆角图片
　　**3、img-circle：**圆形图片
　　**4、img-thumbnail：**缩略图片

使用方法非常简单，只需要在**<img>**标签上添加对应的类名

```
   <div class="container">
        <div class="row">
            <div class="col-sm-4">
                <img alt="140*140" src="http://placehold.it/140x140">
                    <div>默认图片</div>
            </div>
            <div class="col-sm-4">
                <img  class="img-rounded" alt="140x140" src="http://placehold.it/140x140"> 
                    <div>圆角图片</div>
            </div>
            <div class="col-sm-4">
                <img class="img-circle" alt="140x140"   src="http://placehold.it/140x140">
                    <div>圆形图片</div>
            </div>

            <div class="row">
                <div class="col-sm-6">
                    <img class="img-thumbnail" alt="140x140" src="http://placehold.it/140x140">
                    <div>缩略图</div>
                </div>
            </div>
            <div class="col-sm-6">
                <img class="img-responsive" alt="140x140" src="http://placehold.it/140x140">
                    <div>响应式图片</div>
            </div>
        </div>
    </div>
```

![img](https://images2015.cnblogs.com/blog/959898/201605/959898-20160520162554138-854461773.png)

**设置图片大小：**

由于样式没有对图片做大小上的样式限制，所以在实际使用的时候，需要通过其他的方式来处理图片大小。比如说控制图片容器大小。（注意不可以通过css样式直接修改img图片的大小，这样操作就不响应了）



**3-25图标(一)**

Bootstrap框架中提供了近200个不同的icon图片，而这些图标都是使用CSS3的@font-face属性配合字体来实现的icon效果。

　　自定义完字体之后，需要对**icon**设置一个默认样式，在Bootstrap框架中是通过给元素添加**“glyphicon”**类名来实现，然后通过伪元素“**:before**”的“**content**”属性调取对应的icon编码

```
    <span class="glyphicon glyphicon-search"></span>
    <span class="glyphicon glyphicon-asterisk"></span>
    <span class="glyphicon glyphicon-plus"></span>
    <span class="glyphicon glyphicon-cloud"></span>
```

　　显示效果如下图所示:

   ![img](https://images2015.cnblogs.com/blog/959898/201605/959898-20160520163320888-1521145503.png)

**3-26图标(二)**

在网页中使用图标也非常的简单，在任何内联元素上应用所对应的样式即可：

```
    <span class="glyphicon glyphicon-search"></span>
    <span class="glyphicon glyphicon-asterisk"></span>
    <span class="glyphicon glyphicon-plus"></span>
    <span class="glyphicon glyphicon-cloud"></span>
    <span class="glyphicon glyphicon-heart"></span>
    <span class="glyphicon glyphicon-star"></span>
    <span class="glyphicon glyphicon-cloud"></span>
    <span class="glyphicon glyphicon-envelope"></span>
    <span class="glyphicon glyphicon-th-list"></span>
    <span class="glyphicon glyphicon-euro"></span>
    <span class="glyphicon glyphicon-music"></span>
    <span class="glyphicon glyphicon-star-empty"></span>
    <span class="glyphicon glyphicon-user"></span>
    <span class="glyphicon glyphicon-th"></span>
    <span class="glyphicon glyphicon-zoom-in"></span>
    <span class="glyphicon glyphicon-ok"></span>
    <span class="glyphicon glyphicon-remove"></span>
    <span class="glyphicon glyphicon-zoom-out"></span>
```

　　![img](https://images2015.cnblogs.com/blog/959898/201605/959898-20160520164050857-132215274.png)

**特别说明**：

除了使用glyphicon.com提供的图标之外，还可以使用第三方为Bootstrap框架设计的图标字体，如Font Awesome(http://www.bootcss.com/p/font-awesome/)。使用方法和上面介绍的一样，不过记得将字体下载到你本地。 感兴趣的可以阅读官网相关介绍。