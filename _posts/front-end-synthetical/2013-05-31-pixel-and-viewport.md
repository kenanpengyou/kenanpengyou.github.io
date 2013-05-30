---
layout: post
title: "像素与浏览器视口的细节"
category: "前端综合"
description: "最近在做移动版网页的开发，因此研究了网页在不同屏幕尺寸和分辨率的手机中的表现差异。相应地，在一般桌面电脑网页中很少考虑过的一些概念，到了移动版网页则变得重要起来，所以有必要重新理清其中的内容和关系。本文会通过像素及浏览器视口这两个概念，对相关的细节做整理和详细说明。如果你以前有了解过这方面的一些知识，但又存在一些疑惑的地方，也许本文会对你很有帮助。"
---
{% include JB/setup %}

初学网页制作，很常见的做法就是找各种线上的网页，然后查看源代码，参考学习这些网页是如何实现自己的设计的。而对我来说，我印象最深的一个知识点，是这样的：

{% highlight html %}
<div class="wrapper"></div>
{% endhighlight %}

{% highlight css %}
.wrapper{width:980px;margin:0 auto;}
{% endhighlight %}

这个在现在来看，其实就是经典的固定宽度的网页布局。不过，以前的时候，我并不知道为什么这样做就可以。当时的理解是：一个定宽，水平居中的容器，来容纳网页的主体内容，就可以使网页能在不同分辨率的显示屏都有相对较好的表现。而对于浏览器窗口这样一个摆放网页的“物件”，还有相当一些未理解的地方。

网页布局并不只有这一种做法。不像这样简单地使用一个固定宽度的外层容器，同样可以做出在各种状况下都有较好表现的网页。不过，这种时候，就需要对页面布局原理有更深的了解，从而准确地控制好网页元素，保证按照预定的方式显示。

本文将介绍像素及浏览器视口的概念，并解释说明与它们相关的，前端开发应理解的要点细节。本文主要参考了quirksmode.org上的[A tale of two viewports][]，在这里非常推荐你也阅读一下（注意，这篇文章分为两部分）。

##从像素开始##

*像素*（*Pixel*）是数字图像的最小组成单元，它不是一个物理尺寸，但和物理尺寸存在一个可变的换算关系（物理尺寸之间的换算是固定的）。

*PPI*（*Pixel Per Inch*）是指每英寸包含的像素数，同时也是针对这个换算关系的一个描述性指标。其中的英寸（Inch）和厘米（cm）、毫米（mm）等尺寸一样，都属于物理尺寸。不同的显示设备会有不同的PPI，因此，每一个像素点的物理尺寸（可以理解为你如果能拿刻度尺来量的话，得到的数值），也会因为设备的不同而存在差异。一般来说，越高的PPI，相当于在单位物理尺寸内用了更多、更小的像素点来显示图像，因此会更清晰。

在Photoshop中，对图像大小的表示，有“像素大小”以及“文档大小”两个区域，如下图：

![Photoshop中的图像大小][img_photoshop_image_size]

你也许注意过，这里无论改写哪个区域的数值，另一个区域的数字也会相应变化。因此，像素大小和文档大小只是在用不同的方式，表达同一图像的尺寸信息。任何时候，它们之间都可以用“分辨率”数值（比如这里是PPI）进行换算。

与PPI类似的，还有一个*DPI*（*Dot Per Inch*），是指每英寸打印的点数，表示了打印机的打印精度，是属于印刷行业的概念。但如今随着数字化的输入输出设备的发展，很多人也把数字图像的解析度用DPI来表示。严格来说，印刷时计算的网点和电脑显示器的显示像素并不相同，但现在已普遍认同，数字图像显示屏的信息，用DPI或PPI表示均可行，是相同的含义。

##设备像素与css像素##

*设备像素*（*device pixels*）是指与硬件设备直接相关的像素，是真实的屏幕设备中的像素点。比如说，一个电脑显示器的参数中，最佳分辨率是1920x1080，那么指的就是这个显示器在屏幕上用于显示的实际像素点，也就是设备像素。

另一个概念是*css像素*（*css pixels*）。css像素是指网页布局和样式定义所使用的像素，也就是说，css代码中的px，对应的就是css像素。那么，css像素和设备像素有什么区别呢？简单地说，css像素比设备像素要更“虚拟”一些。下面来解释这一点。

在桌面电脑上，浏览器有一个很少使用的功能：*缩放*。比如下边这个矩形元素，宽度是128px，高度是40px。显然，这里的尺寸是css像素。

<div class="post_display">
    <div style="width:128px;height:40px;background:#38a1ff;"></div>
</div>

然后，缩放本页（`ctrl` + `+` 或 `ctrl` + `-`），注意一下，你看到了什么？

矩形元素的css像素尺寸没有变化，同样，你的显示器的设备像素尺寸也不会变化。但是，放大后，元素看起来变大了，在你的屏幕上占据了更大的空间。对应地，如果是缩小，则元素看起来变小了，在屏幕上占据的空间也变小了。

css像素和设备像素之间是一种可变的转化关系。*在100%缩放比例下，1个css像素等于1个设备像素*。在表示某一数目的css像素时，在放大状态下使用了更多的设备像素，而在缩小状态下使用了更少的设备像素。这就是css像素和设备像素的概念。

对前端开发来说，设备像素没有意义，我只会关心css像素。只有css像素才描述了网页的布局与外观，我只需要让我的网页在100%缩放比例下看起来不错就可以了。

在css中，大部分人都习惯于使用`px`作为元素宽度或高度定义的单位。css中可也可以使用其他单位，比如`in`英寸这样的物理尺寸单位。联系前文的内容，你一定会困惑这些单位的关系。css是这样做的：如果你使用`in`这类物理尺寸，它会直接转化为css像素。这个转化关系是固定的：

    1in == 96px 

关于css单位的详细内容，你可以阅读CSS-Tricks上的[The Lengths of CSS][]。

##视口##

*视口*（*viewport*），指的是浏览器窗口中用来显示网页的区域。以桌面电脑的浏览器来说，就是浏览器窗口除去标题栏，菜单栏，地址栏，状态栏等等浏览器的“周边”的东西后剩余的区域。

###桌面电脑中的视口###

桌面电脑中的视口，一般来说是这样的印象：

![桌面电脑中的视口][img_viewport_on_desktop]

视口是存在着一些特性的，要讨论它，就要分析`<html>`和`<body>`这两个元素。`<html>`和`<body>`是任何网页都必然存在的元素，但它们的表现及特性却很少被提及。现在，通过一个例子来说明。

假设`<body>`有一个做自适应布局的直接子元素，比如说侧边栏，定义了`width:20%`，然后调整浏览器窗口大小，你会看到元素会相应做尺寸调整（如果你用前端工具查看，可以看到元素的宽度的计算值，也即css像素，是变化的），始终在视口中占据20%的宽度（这里也假定所有元素都没有内外边距和边框）。这是如何做到的？

可以想到，侧边栏的20%是取了父级元素，也就是`<body>`的宽度值。那`<body>`有多宽呢（没有给它定义宽度）？显然，`<body>`作为块元素，会取父元素，也就是`<html>`的100%宽度值。最后一个问题，`<html>`有多宽？是的，同样，`<html>`作为块元素，会再依照一个宽度值取100%，这个宽度值就是视口的宽度。

因此，可以理解为，视口表现得像是`<html>`之上的一个块元素，它限制并确定`<html>`的宽度，但却不属于html结构，不能被设置样式。而且，任何时候，视口的尺寸都会随着浏览器窗口的大小变化而变化。桌面电脑中的视口，就是这样的一个概念。

也许，你见过这样的问题：在全屏状态下看起来不错的网页，如果调整为一个比较小的浏览器窗口，然后再在这个时候拖动一下横向的滚动条，就会有不协调的地方。比如下图这样：

![较小的视口时有可能存在的问题][img_viewport_trouble]

现在，联系一下视口与网页中的元素之间的显示关系，就可以知道原因了。在这样浏览器窗口较小的时候，视口较小，`<html>`和`<body>`也受视口影响，宽高变得比较小，而带背景图或背景色的元素是取父元素的100%宽度，因此，会只有这样的宽度。

这里会出现问题，也是因为有其他网页元素定义的宽度超过了此时的`<html>`和`<body>`的宽度，从而使一部分元素在水平方向上出现在了视口之外。如果要解决这个问题，为带背景图或背景色的元素，定义一个最小宽度即可。

###手机中的视口###

相比桌面电脑，在手机上浏览网页，最大的差异在于屏幕尺寸。如果你拿手机来看一个平时用桌面电脑浏览的网页，那么一定会经历下面两种状态：页面被缩小，以至于文字无法阅读，或者处于适中的缩放比例，但只显示了整个网页的一小部分。

手机浏览器的供应商致力于让用户在手机上也获得最佳的网页浏览体验，这也是说，要让手机浏览网页的体验能够“尽可能地和桌面电脑相同”。

然后，手机浏览器的供应商是这么考虑的：由于手机屏幕的宽度对于css网页布局来说太小，为了让更多的网页能正常显示（一些流体布局的网页会在过窄的视口中变得一团乱），应该让视口更宽，超越屏幕的宽度。所以，在手机浏览器中，视口被划分为了两个：*可见视口*（*visual viewport*）和*布局视口*（*layout viewport*）。

可见视口是指当前在手机屏幕上显示的部分。当你做缩放的时候，可见视口的尺寸（css像素值）也会变化。如下：

![asdasd][img_visual_viewport_on_mobile]

和可见视口不同，布局视口用于元素布局和尺寸计算（比如百分比的宽度值），而且比可见视口明显要更宽。无论你缩放，或者滑动页面，甚至翻转手机屏幕，布局视口始终不变。前文介绍过`<html>`元素会取视口的宽度值，在手机上，这个限定和确定`<html>`的是布局视口。这就是手机浏览器在处理时和桌面电脑浏览器不一样的地方，而这个布局视口的引入，保证了网页在手机里中的显示与在桌面电脑上的一致。

布局视口的宽度是由手机浏览器定义的，随浏览器不同而不同。比如Safari是980px，Android   Webkit是800px。这都远比屏幕宽度值要大。

你可以做一个测试：写一个整体只有300px宽的网页，但不针对手机做任何处理（也就是代码写法和桌面电脑网页一样），然后用手机打开。你会看到，即使页面内容没有超过手机屏幕宽度，页面仍然会被大比例缩小，就好像这个页面“是一个很宽的桌面电脑网页”。这个测试可以说明布局视口的存在。

###更改手机中的布局视口###

手机中的布局视口是可以更改的。你一定在很多移动版网页中见到过下边这个`<meta>`标签元素。

{% highlight html %}
<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no">
{% endhighlight %}

这是最早由Safari引入，但如今已普遍被各类手机浏览器认可了的一项设置。这其中有一句`width=device-width`，它的意思是，把手机浏览器的布局视口的宽度，更改为当前设备的宽度。你还可以使用`width=500`这样的具体数值（也是css像素值）。总的来说，使用这个`<meta>`标签元素，就可以告诉手机浏览器当前页面应该使用的布局视口的尺寸。

关于这个viewport meta tag的更多信息，你可以阅读Mozilla开发团队写过的[关于viewport meta tag的文章][]。

##与媒体查询的关系##

css中的`@media`媒体查询可以根据尺寸信息分别定义不同的css。其中，可用的值有2个，`width/height`和`device-width/device-height`。这两种尺寸信息有什么区别呢？

*   `width/height`使用的是视口的尺寸值，如果是手机，则是布局视口的尺寸值。
*   `device-width/device-height`使用的是设备屏幕的尺寸值。

在桌面电脑上，如果你写：

{% highlight css %}
@media all and (max-width:600px){
    /*特定样式，只在宽度不大于600时有效*/
}
{% endhighlight %}

那么，只需要调整浏览器尺寸到一定程度，你就可以看到这部分特定样式生效后的效果。但是，如果把这里的`max-width`换成`max-device-width`，那么，无论做什么，都无法看到这部分特定样式生效，因为整个显示器的宽度是不会变化的。因此，在桌面电脑上，你只需要使用`width`。

而在手机上，如果网页有前面说的`width=device-width`的定义（目前几乎所有移动版网页都做了这样的定义），那么使用`width`和`device-width`是相同的。

##结语##

由像素及浏览器视口引入的相关知识还有不少，本文受限于篇幅（如果太长了我实在觉得不能拿来看...（ ﾟ口ﾟ）），只以尽可能明确的方式，介绍了主要的部分。如果有任何疑惑的地方，欢迎讨论。

[img_photoshop_image_size]: {{POSTS_IMG_PATH}}/201305/photoshop_image_size.png "Photoshop中的图像大小"
[img_viewport_on_desktop]: {{POSTS_IMG_PATH}}/201305/viewport_on_desktop.jpg "桌面电脑中的视口"
[img_viewport_trouble]: {{POSTS_IMG_PATH}}/201305/viewport_trouble.jpg "较小的视口时有可能存在的问题"
[img_visual_viewport_on_mobile]: {{POSTS_IMG_PATH}}/201305/visual_viewport_on_mobile.jpg "手机上的可见视口"

[A tale of two viewports]: http://www.quirksmode.org/mobile/viewports.html "A tale of two viewports"
[The Lengths of CSS]: http://css-tricks.com/the-lengths-of-css/ "The Lengths of CSS"
[关于viewport meta tag的文章]: https://developer.mozilla.org/en/mobile/viewport_meta_tag "Using the viewport meta tag to control layout on mobile browsers"