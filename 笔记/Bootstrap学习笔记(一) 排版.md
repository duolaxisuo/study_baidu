##  Bootstrap学习笔记(一) 排版

首先学习排版:

从[Bootstrap](http://www.bootcss.com/)网站下载Bootstrap3中文文档（V3.3.5），解压到本地。由于幕课上排版系列课程主要用的是Bootstrap的Css，所以下载解压，将其中的bootstrap.min.css复制粘贴到我保存html文件里的一个styles文件夹中，此文件夹专用来保存css文件。

编辑器使用 sublime text3。

然后再html文件的head里插入如下代码即可使用了:（先jq,再CSS，最后为JS）

```
<script src="https://how2j.cn/study/js/jquery/2.0.0/jquery.min.js"></script>
<link href="https://how2j.cn/study/css/bootstrap/3.3.6/bootstrap.min.css" rel="stylesheet">
<script src="https://how2j.cn/study/js/bootstrap/3.3.6/bootstrap.min.js"></script>
```

**2-1标题** 

　　和html一样，bootstrap使用标签<h1>到<h6>,在bootstrap中非标题元素也可以使用:

```
<h1>Bootstrap标题一</h1>
<h2>Bootstrap标题二</h2>
<h3>Bootstrap标题三</h3>
<h4>Bootstrap标题四</h4>
<h5>Bootstrap标题五</h5>
<h6>Bootstrap标题六</h6>

<!--Bootstrap中让非标题元素和标题使用相同的样式-->
<div class="h1">Bootstrap标题一</div>
<div class="h2">Bootstrap标题二</div>
<div class="h3">Bootstrap标题三</div>
<div class="h4">Bootstrap标题四</div>
<div class="h5">Bootstrap标题五</div>
<div class="h6">Bootstrap标题六</div>
```

**2-2标题（2）**

　　bootstrap中使用<small>标签制作副标题。

**2-3段落**

　　使用标签<p>

**2-4强调内容**

　　可添加类名"**.lead**"实现：

```
 <p class="lead">我是特意要突出的文本。</p>
```

**2-5粗体**

```
<p>我在学习<strong>Bootstrap</strong></p>
```

**2-6斜体**

<i> 标签显示斜体文本效果

<em> 标签告诉浏览器把其中的文本表示为强调的内容。对于所有浏览器来说，这意味着要把这段文字用斜体来显示。

```
<p>我在慕课网上跟<em>大漠</em>一起学习<i>Bootstrap</i>的使用。我一定要学会<i>Bootstr
```

**2-7强调相关的类**

- .text-muted：提示，使用**浅灰色（#999）**
- .text-primary：主要，使用**蓝色（#428bca）**
- .text-success：成功，使用**浅绿色(#3c763d)**
- .text-info：通知信息，使用**浅蓝色（#31708f）**
- .text-warning：警告，使用**黄色（#8a6d3b）**
- .text-danger：危险，使用**褐色（#a94442）**

```
<div class="text-muted">.text-muted 效果</div>
<div class="text-primary">.text-primary效果</div>
<div class="text-success">.text-success效果</div>
<div class="text-info">.text-info效果</div>
<div class="text-warning">.text-warning效果</div>
<div class="text-danger">.text-danger效果</div>
```

![img](https://images2015.cnblogs.com/blog/959898/201605/959898-20160519160302935-1839635022.png)

**2-8文本对齐**

　　bootstrap中text-left：左对齐，text-center：居中对齐，text-right：右对齐,text-justify：两端对齐。

```
<p class="text-left">我居左</p>
<p class="text-center">我居中</p>
<p class="text-right">我居右</p>
<p class="text-justify"></p>
```

**2-9列表**

　　<ul>无序

　　<ol>有序

　　定义列表:

```
<dl>
    <dt>定义列表标题</dt>
    <dd>定义列表信息1</dd>
    <dd>定义列表信息2</dd>
</dl>
```

**2-10列表--无序列表、有序列表**

　　<ul>无序

　　<ol>有序

```
<h5>普通列表</h5>
<ul>
    <li>列表项目</li>
    <li>列表项目</li>
    <li>列表项目</li>
    <li>列表项目</li>
    <li>列表项目</li>
</ul>
<h5>有序列表</h5>
<ol>
      <li>项目列表一</li>
      <li>项目列表二</li>
      <li>项目列表三</li>
</ol>
```

**2-11去点列表**

　　给列表添加**.list-unstyled**，可以去除默认列表样式风格。

```
 <ol>
            <li>有序项目列表一</li>
            <li>有序项目列表二</li>
                <ol class="list-unstyled">
                    <li>有序二级列表项目列表一</li>
                    <li>有序二级列表项目列表二</li>
                    <ul>
                        <li>无序三级项目列表一</li>
                        <li>无序三级列表项目二</li>
                        <ul class="list-unstyled">
                            <li>无序四级项目列表一</li>
                            <li>无序四级列表项目二</li>
                        </ul>
                        <li>无序三级项目列表三</li>
                    </ul>
                    <li>有序二级项目列表三</li>
                </ol>
            <li>有序项目列表三</li>
        </ol>
```

**2-12列表--内联列表**

　　通过添加类名“**.list-inline**”来实现内联列表，bs4中需要添加list-inline-item

```
<ul class="list-inline">

    <li class="list-inline-item">W3cplus</li>

    <li class="list-inline-item">Blog</li>

    <li class="list-inline-item">CSS3</li>

    <li class="list-inline-item">jQuery</li>

    <li class="list-inline-item">PHP</li>

</ul>

```