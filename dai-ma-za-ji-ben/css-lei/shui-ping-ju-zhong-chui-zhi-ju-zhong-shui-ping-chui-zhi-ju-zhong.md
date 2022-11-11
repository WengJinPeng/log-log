# 水平居中、垂直居中、水平垂直居中



### 1、水平居中 <a href="#lnhci" id="lnhci"></a>

**水平居中可分为行内元素水平居中和块级元素水平居中**

**1.1 行内元素水平居中**

这里行内元素是指文本text、图像img、按钮超链接等，只需给父元素设置text-align:center即可实现。

`.center{`

`text-align:center; }`

`<div class="center">水平居中</div>`

**1.2 块级元素水平居中**

* **定宽块级元素水平居中**\
  只需给需要居中的块级元素加margin:0 auto即可，**但这里需要注意的是，这里块状元素的宽度width值一定要有**

`.center{`

`display:table;`

`margin:0 auto;`

`border:1px solid red;`

`}`

`<div class="center">水平居中</div>`

**方法2：设置inline-block**（多个块状元素）\
子元素设置inline-block，同时父元素设置text-align:center

`.center{`

`text-align:center;`

`}`

`.inlineblock-div{`

`display:inline-block;`

`}`

`<div class="center">`

`<div class="inlineblock-div">1</div>`

`<div class="inlineblock-div">2</div>`

`</div>`

**方法3：设置flex布局**\
只需把要处理的块状元素的父元素设置display:flex,justify-content:center;

`.center{`

`display:flex;`

`justify-content:center;`

`}`

`<div class="center">`

`<div class="flex-div">1</div>`

`<div class="flex-div">2</div>`

`</div>`

**方法4：position + 负margin；**\
**方法5：position + margin：auto；**\
**方法6：position + transform；**

**注：**这里方法4、5、6同下面垂直居中一样的道理，只不过需要把top/bottom改为left/right，在垂直居中部分会详细讲述。

***

### 2、垂直居中 <a href="#mf9bn" id="mf9bn"></a>

**2.1 单行文本垂直居中**

* 设置paddingtop=paddingbottom；或
* 设置line-height=height；

**2.2 多行文本垂直居中**

通过设置父元素table，子元素table-cell和vertical-align\
vertical-align:middle的意思是把元素放在父元素的中部

![](https://cdn.nlark.com/yuque/0/2022/png/29713818/1661961508372-38282ce8-4dae-4b23-9605-17d1492f0c22.png)

![](https://cdn.nlark.com/yuque/0/2022/png/29713818/1661961512653-f56775f9-1d93-4859-b872-d68fc3c54e6e.png)

**2.3 块级元素垂直居中**

**方法1：flex布局**\
在需要垂直居中的父元素上，设置display:flex和align-items：center\
要求：父元素必须显示设置height值

![](https://cdn.nlark.com/yuque/0/2022/png/29713818/1661961528766-e3e2c7fd-aa76-4423-8e44-9520208f2fba.png)

显示效果：

![](https://cdn.nlark.com/yuque/0/2022/png/29713818/1661961542430-096600cf-407a-4cb8-a7cb-5ce9272b75cc.png)

**方法2：利用position和top和负margin**（需知宽高）\
1、设置元素为absolute/relative/fixed\
2、margin=负一半

![](https://cdn.nlark.com/yuque/0/2022/png/29713818/1661961592123-298cb5c9-9b37-4de1-8174-fbdf76ef8681.png)

效果如下：

![](https://cdn.nlark.com/yuque/0/2022/png/29713818/1661961626958-cbc47bd1-7db5-4131-bdae-778c4a4d1d01.png)

**方法3：利用position和top/bottom和margin:auto**（注意不是margin:0 auto）\
1、position：absolute/relative/fixed\
2、top/bottom：0\
3、margin：auto

![](https://cdn.nlark.com/yuque/0/2022/png/29713818/1661962310233-4ad60ab3-05bb-4ee9-9b59-414e2c89ccf8.png)

效果如下：

![](https://cdn.nlark.com/yuque/0/2022/png/29713818/1661962322600-9d49a838-8999-4cf5-8e5f-a92f7da70e76.png)

方法4：利用position和top和transform\
transform中translate偏移的百分比就是相对于元素自身的尺寸而言的。

![](https://cdn.nlark.com/yuque/0/2022/png/29713818/1661962349952-db878f57-ae29-4bd8-83c5-d2005f859a7e.png)

效果如下：

![](https://cdn.nlark.com/yuque/0/2022/png/29713818/1661962380805-61da2a7f-95fd-48df-ade1-f766eac962ef.png)

**注：**

* 上述的块级垂直居中方法，稍加改动，即可成为块级水平居中方法，如top/bottom换成left/right
* transform方法，可用于未知元素大小的居中

***

### 3、水平垂直居中 <a href="#gdmgf" id="gdmgf"></a>

**方法1：绝对定位+margin:auto**

`div{`

`width: 200px;`

`height: 200px;`

`background: green;`

`position:absolute;`

`left:0;`

`top: 0;`

`bottom: 0;`

`right: 0;`

`margin: auto;`

`}`

**方法2：绝对定位+负margin**

`div{`

`width:200px;`

`height: 200px;`

`background:green;`

`position: absolute;`

`left:50%;`

`top:50%;`

`margin-left:-100px;`

`margin-top:-100px;`

`}`

**方法3：绝对定位+transform**

`div{`

`width: 200px;`

`height: 200px;`

`background: green;`

`position:absolute;`

`left:50%; /* 定位父级的50% */`

`top:50%;`

`transform: translate(-50%,-50%); /*自己的50% */`

`}`

**方法4：flex布局**

`.box{`

`height:600px;`

`display:flex;`

`justify-content:center; //子元素水平居中`

`align-items:center; //子元素垂直居中`

`/* aa只要三句话就可以实现不定宽高水平垂直居中。 */`

`}`

`.box>div{`

`background: green;`

`width: 200px;`

`height: 200px;`

`}`

**方法5：table-cell实现居中**

* 设置\
  `display:table-cell;`\
  `text-align:center;`\
  `vertical-align: middle;`
