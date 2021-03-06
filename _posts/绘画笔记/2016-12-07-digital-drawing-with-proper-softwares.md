---
layout: post
title: "初级板绘教程：那些绘画软件的使用方法"
category: "绘画笔记"
description: "有意向尝试板绘吗？这可能是一篇不错的新手指南。"
---
{% include JB/setup %}

在现代，画画除了真实的纸面作画，还有一个很主要的类别就是板绘（数码绘画）。感觉上说，就是一种一定要搭配一点数码设备的绘画方式。

## 设备 ##

说起数码绘画的设备，最为人所知的大概就是数位板了：

![数位板][img_graphics_tablet_normal_version]

这样，一个板子，一支笔，就可以像真实绘画的纸 + 笔的搭配那样去作画。

另一种叫做数位屏：

![数位屏][img_graphics_tablet_screen_version]

它是直接在显示屏幕上作画，相对比较昂贵，但更贴近真实的纸面绘画。

此外，平板电脑，比如Surface（+ Surface Pen），iPad Pro（+ Apple Pencil）也是很不错的选择。再简单一点的话，手机等触控设备也可以（有那么多画画的APP呢，对吧？）

### 数位板的选购 ###

从新人入门的角度来说，考虑想认真练习绘画，又花费比较少的话，推荐的设备是数位板。

数位板的品牌只推荐wacom（和冠），目前它的入门级产品Bamboo系列只要500元左右（在本文的时间点，是CTL-671中尺寸板）。即使是这样一个入门级的板子，也足够用上几年。

如果有更多的预算，可以考虑wacom其他系列产品。

数位板有一个参数叫压感级别（Pressure Levels），指的是笔尖压力的识别精度，一般来说达到1024就很足够（上面的入门级产品也是这个值）。比这个更高的压感级别，对于不是非常专业的作画来说，意义不大。

数位板的尺寸是另一个需要注意的地方，对大部分人来说，中等尺寸是最好用的，方便携带，又不会觉得作画范围太小，施展不开。

### 数位板的使用要点 ###

数位板在使用前，一般都要安装驱动程序。驱动程序也提供了数位板的属性配置功能，比如我的是这样的：

![wacom的数位板驱动程序之一][img_wacom_config]

在这个程序中可以调整数位板的快捷键、笔压等，而且可以针对不同的应用程序使用不同的配置（上图的“应用程序”一栏）。

可以稍注意一下上图的“映射”，它的意思是，你拿笔点到（不是真要碰到，靠近到一定距离就算）数位板的有效范围（红框）内的任一点，屏幕指针就会直接跳到屏幕上的对应点。这是“笔”模式，和鼠标是不一样的。我用的是图中这样的默认值。

在笔没有接触到数位板，但位于数位板上方一定的距离内时，笔的移动就会带着电脑里的屏幕指针一起移动。

以惯用右手为例的话，作画的过程大概是：一边眼睛看着屏幕（不看数位板...），一边右手拿笔在数位板上涂，同时左手操作键盘做辅助（各类快捷键，如切换笔刷，保存文件）。

## 特色 ##

我们熟知的水彩、彩铅、油画等真实绘画的风格，在数码绘画中都能以非常接近的形式实现。而借助于绘图软件多样化的功能，更可以创作出一些以真实绘画方式无法做到的全新风格。就像摄影的照片常用的“后期”那样，数码绘画的作品同样可以“后期”。

在数码绘画中，作品是电脑文件（最常见的就是`.psd`）。利用云盘等存储方法，我们可以比较可靠地保存自己的全部作品（可以拿来制作“画师进化录”）。需要作品实物的话，就拿源文件去印刷吧，来多少份都可以。

现在常见的画师约稿，也主要是以数码绘画成品的形式交稿。

## 软件 ##

接下来进入正篇。数码绘画有很多的软件可以用，说起具体哪一个比较好这种问题的话，就像画师的画风那样，是因人而异的。以及，并没有说一定要选一个，有精力的话，你完全可以全部学习下，然后根据对这些不同绘画软件的理解，穿插搭配使用。

下面是几位有名的画师贴出的自己所用的软件，供参考：

![几位画师的软件][img_illustrator_softwares]<br>
<small>信息来源：pixiv个人资料 / 《プロの絵師に学ぶキャラ塗り上達テクニック》 / 《Let's Make ★ Character CGイラストテクニックvol.9》</small>

软件只是工具，所以不必太过拘泥，关键还是在绘画功底。只要你画得好，没人在意你是拿什么画的（<del>Windows画图，Excel等也可以</del>）。

我自己的话，前后有学习和使用过的软件分别是SAI、Photoshop、CLIP STUDIO PAINT（简称CSP），它们都可以在上图中找到。

Photoshop是大家都知道的，功能强大，绘画只算它的其中一种用途。相比之下，SAI和CSP比较像更专项的“绘画软件”。

![三个常用绘画软件][img_logos_combined]

在这三个软件中，SAI是最简单也最小巧的，所以从SAI开始吧。

## SAI ##

[SAI](https://zh.wikipedia.org/wiki/Paint_Tool_SAI)，也叫Easy PaintTool SAI，它是一个很轻巧的软件，安装包小，资源占用也小，很一般的电脑也可以流畅运行它。

SAI的界面大概这个样子：

![SAI主界面][img_sai_overview]

一下子看到这么多东西可能有点慌。不用担心，我只打算介绍我认为比较重要的部分。

接下来以一个简单的绘画过程来说下SAI是怎样用的。

### 文件大小与格式 ###

首先，是新建一个文件（`文件 → 新建文件`或`Ctrl + N`）：

![新建文件][img_sai_new_file_size]

图中的“预设尺寸”很有用。如果是正式的个人作品，包括同人或商业稿，一般可以选A4或B5，它们最为常用，分辨率300，放大后也很清晰。

如果只是随便画画，可以取默认分辨率72，大小自定。

点击“确定”后就可以看到画布了。先别急着画，这里有一个非常重要的事情：保存文件（重要x3）。在菜单选择`文件 → 另存为`或直接`Ctrl + S`，把作品源文件保存下来：

![另存文件格式][img_sai_file_format]

如上图，在“文件类型”一栏里，建议不使用默认的`.sai`，而选择`.psd`。一方面`.psd`更稳定可靠，另一方面`.psd`还可以被Photoshop、CSP等许多其他软件读取和使用（`.sai`就只有SAI了）。

保存文件是数码绘画很重要的一件事，绘画过程中，记得随时`Ctrl + S`保存。已经画得差不多了却因为死机、软件异常关闭等事件而吐血重画的经历，还是少一点比较好。

### 笔和颜色 ###

已保存的文件就绪后，接下来就开始画了。像真实绘画那样，先考虑用什么笔和颜色。

找到这个写着“铅笔”，“喷枪”，“笔”等字样的区域，就是选笔的地方了：

![笔工具区域][img_sai_pen_select]

紧贴着这个区域下边的面板，则是用于设置笔刷属性和笔刷大小。有关笔刷选择及设置的详细介绍，推荐阅读豆瓣上的这篇[SAI 超详细入门级教程](https://site.douban.com/214224/widget/notes/14185333/note/289187358/)。

我自己用得最多的是铅笔（默认快捷键N）、笔（V）和喷枪（B）。另外，橡皮擦（E）也是在这个区域。

SAI里最靓丽的这个色轮（也叫色环），用于选取颜色：

![色轮][img_sai_color_cycle]

这里需要一点色相、饱和度、明度的[色彩知识](https://zh.wikipedia.org/wiki/HSL%E5%92%8CHSV%E8%89%B2%E5%BD%A9%E7%A9%BA%E9%97%B4)。外面的圆环选取色相，里面的方形选择饱和度，明度，这样得到一个颜色。

### 画布 ###

选取好笔和颜色后，就开始在中间的画布上动笔了。下面是一些可能有用的tips：

* `Ctrl + +`和`Ctrl + -`来放大缩小，`Ctrl + 0`还原到默认缩放。
* 某些地方以默认角度画起来比较困难，可以用下图这个旋转工具来旋转画布。双击可以设置快捷键，我用的是R，这和Photoshop的旋转工具是一致的。

    ![旋转工具][img_sai_rotate_tool]
    
* 任何时候，按住空格，当前工具会变为抓手工具，此时可以移动画布。松开空格，则还原为之前的工具。
* 按H来水平翻转视图，这可以用于确认画面的平衡。
* 当前的一笔觉得涂得不好（比如线条扭曲了），`Ctrl + Z`撤销掉，然后重新涂。可以反复撤销直到画出满意的一笔。

### 图层 ###

绘画过程中，我们会希望某些元素和另一些元素是分离的，比如画面的背景和位于前方的人物。涂背景的时候，无论怎样画，也不会影响人物，反之亦然，这样会很方便随时做调整。

这里要用到的就是图层。初始状态下只有一个图层1，如果希望接下来要画的东西不影响画布上已有的内容，就在图层面板新建一个图层：

![图层面板][img_sai_layer_panel]

如上图，从起好名字的图层和图层组中，可以很方便看出独立的背景、人物线稿及人物上色。

SAI的图层上限是256，尽情使用吧。

### 透明色 ###

在前景色/背景色的位置的左下有一个小方格，点击后可以切换当前颜色为透明色。像这样：

![透明色][img_sai_transparent]

透明色就好像在把你当前正在用的笔工具变成了同样属性的橡皮擦，非常好用。我自己是设置成了快捷键Q（默认是`-`）。

### 抖动修正 ###

在快捷工具栏里有一个“抖动修正”，作用就是在你下笔的时候处理掉一些小的抖动，使笔触更平滑。这对于画流畅的线条来说尤其有用。

![抖动修正][img_sai_revise]

抖动修正的数值越高，辅助效果越强，但也会让人产生依赖（比如习惯了再到Photoshop这类没有这个的软件里就很难画）。对新手来说，建议取10以下的值，并且随着水平提升渐渐减小这个值。

### 其他参考 ###

SAI是很受欢迎的绘画软件，相关介绍及教程很多，可以自行搜索。

## Photoshop ##

Photoshop是我们很熟悉的大型图像软件了：

![Photoshop界面][img_ps_overview]

图中的色轮是一个Photoshop插件，叫做Coolorus，它可以帮助你更好地在Photoshop中选取颜色，很推荐在使用Photoshop绘画时搭配上它。

同样，下面只介绍对绘画比较重要的部分。

### 笔刷 ###

Photoshop有许多工具，不过绘画最主要使用的还是画笔工具和橡皮擦工具。画笔和橡皮擦在Photoshop中都属于画笔类工具，可以打开下面这个画笔面板来进行非常详尽的配置：

![Photoshop的画笔面板][img_ps_brush_panel]

每一套画笔面板的配置，都可以保存为一个“画笔预设”，这就是常说的Photoshop笔刷了。

在网上可以找到非常多的笔刷资源下载。比如下面这个笔刷系列叫johnsilva smudge pack 2.0：

![一套笔刷资源的预览][img_ps_dl_brush]

笔刷资源可以直接使用，也可以在它们的基础上再做调整，得到新的笔刷。每个人都有自己的作画风格，可以一点点摸索并制作出自己喜欢的笔刷。

### 工具预设和画笔预设 ###

下载的笔刷资源可能有`.tpl`和`.abr`两种不同的格式，它们是有区别的：

![TPL和ABR格式][img_ps_tpl_abr]

`.tpl`是工具预设，`.abr`是画笔预设。如上图，工具预设位于更靠左的小箭头位置，它不仅可以保存画笔工具的预设，还可以保存其他工具的预设，而画笔预设只用于画笔类工具。简单来说，`.tpl`比`.abr`的作用范围更广一些。

不过，在绘画中使用时，并不会觉得多大区别。选择`窗口 → 工具预设 / 画笔预设`，都可以得到一个随时可切换的画笔列表：

![预设列表][img_ps_brush_list]

### 画布和图层 ###

可以像前面介绍的SAI的画布操作那样去移动、缩放和旋转画布。

Photoshop的图层面板和SAI近似，只是更为强大。

### 滤镜与调整 ###

菜单里的“滤镜”（比如高斯模糊），以及调整图层（比如曲线）：

![调整图层][img_ps_adjust_layer]

可以用于作品的后期处理。

### 其他参考 ###

不用说，Photoshop的介绍及教程非常多，自行搜索即可。不是关于绘画的也可以，Photoshop的综合熟练度总能或多或少地有助于绘画。

## CLIP STUDIO PAINT ##

[CSP](http://www.clipstudio.net/tc/functions/)也是一个相对大型的软件，它在中国内陆对应的是由CELSYS（CSP的所属公司）的合资公司UNICORN出品的[优动漫](http://www.udongman.cn/index.php)。

CSP的界面看上去比较复杂，作为绘画软件非常专业：

![CSP界面][img_csp_overview]

对比前面的SAI，界面其实有许多地方是近似的。因此，在CSP中，最基本的作画方法是一致的。

CSP也有不少地方类似Photoshop，它同样支持`.psd`文件格式，而且也提供了一定程度的滤镜和调整图层用于后期处理。

此外，CSP还有许多它的特色。

### 素材库 ###

点开前面图中“素材集”的任意图标，可以打开CSP内置的这个强大的素材库：

![CSP素材库][img_csp_material]

找到喜欢的素材后，拖拽到画布上就可以使用。除官方初始提供的素材外，可以从网上下载到更多的素材资源。此外，也可以自己制作素材，然后保存到这个库内。

### 3D参考 ###

CSP还在素材库里提供了3D人物：

![CSP的3D素材][img_csp_3d_ref]

找到角色后，和其他素材一样拖拽到画布上，就会增加3D人物的图层。预设的姿势（POSE），则需要拖拽到人物身上。

### 透视尺 ###

选择`图层 → 尺子/格子框 → 新建透视尺`可以创建带透视尺的图层：

![创建透视尺][img_csp_ruler]

透视尺图层可以任意添加透视参考线，这对于带透视效果的作品绘制来说非常有用（图来自[wiki-透视](https://zh.wikipedia.org/wiki/%E9%80%8F%E8%A7%86)）：

![透视参考][img_csp_perspective]

### 漫画 ###

CSP特别为漫画制作准备了一系列工具，如分镜格子框、对白框：

![CSP的漫画支持][img_csp_comic]

你肯定在很多漫画里都见过这些元素，它们在CSP中会很容易创建。

此外，素材库中也可以找到漫画分格模板、网点、效果线等丰富的漫画素材。

### 其他参考 ###

CSP的教程相对较少，在此推荐下面两个：

* [clip studio paint 大概演示和漫画教程](http://www.bilibili.com/video/av1885080/)
* [官方教程手册](http://www.clip-studio.com/site/gd_tc/csp/startupguide/csp_startup_tc/CSPaint_00/Chapter00_1.htm)

## 一点个人使用感受 ##

以上三个软件，无论哪一个都可以独立完成绘画作品。

如果考虑组合使用，我自己是这样的倾向：

* 草稿、线稿及人物的基础上色由SAI完成。
* 涂鸦练习用SAI。
* 人物的后期上色、背景绘制、作品整体的后期处理在Photoshop中做。
* 漫画用CSP。
* 用CSP来准备透视参考线。
* 多利用CSP的素材库。

以上观点十分主观，仅供参考。

## 参考资料的来源 ##

画画总是要各种参考资料，素材，或者别人的作品都很有意义。在此推荐一些收集资料的网站：

* [pixiv](http://www.pixiv.net/)，有名的插画交流网站。
* [花瓣网](http://huaban.com/)，图片资源采集分享站点。
* [DeviantArt](http://www.deviantart.com/)，国际性艺术创作社群网站。
* [Posemaniacs](http://www.posemaniacs.com/)，主要是不同动作，视角的3D人物模型。
* [Sketchfab](https://sketchfab.com)，更多种类的3D视图模型。

## 结语 ##

本文只介绍了几个绘画软件的最基本用法，具体如何去完整作品，可能是每个画画的人需要自行摸索的历程。我自己的水平还差得很远，所以只在此建议多向优秀的画师学习，以及多做有效的绘画练习。

虽然本文介绍了好几个绘画软件，但不用想着一定要全都学会，我觉得，好的作品是靠实力说话的，绘画功底远比会一个绘画软件重要。

[img_graphics_tablet_normal_version]: {{POSTS_IMG_PATH}}/201612/graphics_tablet_normal_version.jpg  "数位板"
[img_graphics_tablet_screen_version]: {{POSTS_IMG_PATH}}/201612/graphics_tablet_screen_version.jpg  "数位屏"
[img_wacom_config]: {{POSTS_IMG_PATH}}/201612/wacom_config.jpg  "wacom的数位板驱动程序之一"
[img_illustrator_softwares]: {{POSTS_IMG_PATH}}/201612/illustrator_softwares.jpg "几位画师的软件"
[img_logos_combined]: {{POSTS_IMG_PATH}}/201612/logos_combined.png  "三个常用绘画软件"
[img_sai_overview]: {{POSTS_IMG_PATH}}/201612/sai_overview.jpg  "SAI主界面"
[img_sai_new_file_size]: {{POSTS_IMG_PATH}}/201612/sai_new_file_size.png  "新建文件"
[img_sai_file_format]: {{POSTS_IMG_PATH}}/201612/sai_file_format.png  "另存文件格式"
[img_sai_pen_select]: {{POSTS_IMG_PATH}}/201612/sai_pen_select.png  "笔工具区"
[img_sai_color_cycle]: {{POSTS_IMG_PATH}}/201612/sai_color_cycle.jpg  "色轮"
[img_sai_rotate_tool]: {{POSTS_IMG_PATH}}/201612/sai_rotate_tool.png  "旋转工具"
[img_sai_layer_panel]: {{POSTS_IMG_PATH}}/201612/sai_layer_panel.png  "图层面板"
[img_sai_transparent]: {{POSTS_IMG_PATH}}/201612/sai_transparent.png  "透明色"
[img_sai_revise]: {{POSTS_IMG_PATH}}/201612/sai_revise.png  "抖动修正"
[img_ps_overview]: {{POSTS_IMG_PATH}}/201612/ps_overview.jpg  "Photoshop界面"
[img_ps_brush_panel]: {{POSTS_IMG_PATH}}/201612/ps_brush_panel.png  "Photoshop的画笔面板"
[img_ps_dl_brush]: {{POSTS_IMG_PATH}}/201612/ps_dl_brush.jpg  "一套笔刷资源的预览"
[img_ps_tpl_abr]: {{POSTS_IMG_PATH}}/201612/ps_tpl_abr.png  "TPL和ABR格式"
[img_ps_brush_list]: {{POSTS_IMG_PATH}}/201612/ps_brush_list.png  "预设列表"
[img_ps_adjust_layer]: {{POSTS_IMG_PATH}}/201612/ps_adjust_layer.png  "调整图层"
[img_csp_overview]: {{POSTS_IMG_PATH}}/201612/csp_overview.jpg  "CSP界面"
[img_csp_material]: {{POSTS_IMG_PATH}}/201612/csp_material.jpg  "CSP素材库"
[img_csp_3d_ref]: {{POSTS_IMG_PATH}}/201612/csp_3d_ref.png  "CSP的3D素材"
[img_csp_ruler]: {{POSTS_IMG_PATH}}/201612/csp_ruler.png  "创建透视尺"
[img_csp_perspective]: {{POSTS_IMG_PATH}}/201612/csp_perspective.jpg  "透视参考"
[img_csp_comic]: {{POSTS_IMG_PATH}}/201612/csp_comic.png  "CSP的漫画支持"
