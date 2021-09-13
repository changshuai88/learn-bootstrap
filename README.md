# learn-bootstrap
学习bootstrap--from 2021-09-07 to

# 目标

- 能够说出响应式原理
- 能够使用媒体查询完成响应式导航
- 能够使用Bootstrap的栅格系统
- 能够使用bootstrap的相应式工具
- 能够独立完成案例

# 知识点

* 响应式开发
* bootstrap前端开发框架
* bootstrap栅格系统
* 案例

# 1.响应式开发

## 1.1 响应式开发原理

就是使用媒体查询针对不同宽度的设备进行布局和样式的设置，从而适配不同设备的目的

|设备划分|尺寸区间|
|---|---|
|超小屏幕--手机|<768px|
|小屏设备--平板|>=768~<992px|
|中等屏幕--桌面显示器|>=992px ~ <1200px|
|宽屏设备--大桌面显示器|>=1200px|

## 1.2响应式布局容器

- 响应式需要一个父级作为布局容器，来配合子级元素来实现变化效果
- 原理就是在不同屏幕下，通过媒体查询来改变这个布局容器的大小，再改变里面子元素的排列方式和大小，从而实现不同屏幕下，看到不同的页面布局和样式变化。

### 平时我们的相应式尺寸划分

- 超小屏幕（手机，小于768px）：设置宽度为100%
- 小屏幕(平板，大于等于768px)：设置宽度为750px
- 中等屏幕(桌面显示器，大于992px)：宽度设置为970px
- 大屏幕(大桌面显示器，大于等于1200px)：宽度设置为1170px
  
  但是我们可以根据实际情况自己定义划分


### 案例：响应式导航

1.当我们屏幕大于等于768像素，我们给布局容器container宽度为750px
2.container里面包含8个小li盒子，每个盒子的宽度定为93.75培训(750/8),高度为30px，浮动一行显示。
3.当我们屏幕缩放，宽度小于768像素的时候，container盒子宽度改为100%宽度。
4.此时里面的8个小li，宽度修改为33.33%，这样一行就只能显示3个小li，剩余下行显示。

# 2 Bootstrap前段开发框架

## 2.1 Bootstrap简介

Bootstrap来自Twitter，是目前最受欢迎的前端框架，Bootstrap是基于HTML、CSS和JavaScript的，它简介灵活，使得web开发更加快捷。
- 中文官网：http://www.bootcss.com
- 官网：http://getbootstrap.com
- 推荐使用：http://bootstrap.css88.com

  ** 框架：顾名思义就是套架构，它有一套比较完整的网页功能解决方案，而且控制权在框架本身，有预制样式库、组件和插件。使用者要按照框架所规定的某种规范进行开发 **

1.优点
- 标准化的html+css编码规范
- 提供了一套简洁、直观、强悍的组件
- 有自己的生态圈，不断地更新迭代
- 让开发更简单，提高了开发的效率
  
2.版本
* 2.xx：停止维护，兼容性好，代码不够简洁，功能不够完善
* 3.xx：目前使用最多，稳定，但是放弃了IE6-IE7，对IE8支持但是界面效果不好，偏向用于响应式布局。 移动设备优先的web项目。
* 4.xx：最新版，目前还不是很流行。
  
## 2.2 bootstrap使用
** 控制权在框架本省，使用者要按照框架所规定的某周规范进行开发 **
bootstrap使用四部曲：
1.创建文件夹结构
2.创建html骨架结构
<!doctype html>
<html lang="zh-CN">
  <head>
    <meta charset="utf-8">
    <!-- 要求当前网页使用IE浏览器最高版本的内核来渲染 -->
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <!-- 视口的设置：视口的宽度和设备一致，默认的缩放比例和PC端一致，用户不能自行缩放 -->
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <!-- 上述3个meta标签*必须*放在最前面，任何其他内容都*必须*跟随其后！ -->
    <title>Bootstrap 101 Template</title>

    <!-- Bootstrap -->
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/3.4.1/css/bootstrap.min.css" integrity="sha384-HSMxcRTRxnN+Bdg0JdbxYKrThecOKuH5zCYotlSAcp1+c8xmyTe9GYg1l9a69psu" crossorigin="anonymous">

    <!-- HTML5 shim 和 Respond.js 是为了让 IE8 支持 HTML5 元素和媒体查询（media queries）功能 -->
    <!-- 警告：通过 file:// 协议（就是直接将 html 页面拖拽到浏览器中）访问页面时 Respond.js 不起作用 -->
    <!--[if lt IE 9]>
    <!-- 解决IE9以下浏览器对HTML5新增标签的不识别,并导致CSS不起作用的问题 -->
      <script src="https://cdn.jsdelivr.net/npm/html5shiv@3.7.3/dist/html5shiv.min.js"></script>
      <!-- 解决IE9以下浏览器对CSS media query的不识别 -->
      <script src="https://cdn.jsdelivr.net/npm/respond.js@1.4.2/dest/respond.min.js"></script>
    <![endif]-->
  </head>
  <body>
    <h1>你好，世界！</h1>

    <!-- jQuery (Bootstrap 的所有 JavaScript 插件都依赖 jQuery，所以必须放在前边) -->
    <script src="https://cdn.jsdelivr.net/npm/jquery@1.12.4/dist/jquery.min.js" integrity="sha384-nvAa0+6Qg9clwYCGGPpDQLVpLNn0fRaROjHqs13t4Ggj3Ez50XnGQqc/r8MhnRDZ" crossorigin="anonymous"></script>
    <!-- 加载 Bootstrap 的所有 JavaScript 插件。你也可以根据需要只加载单个插件。 -->
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/3.4.1/js/bootstrap.min.js" integrity="sha384-aJ21OjlMXNL5UyIl/XNwTMqvzeRMZH2w8c5cRVpzpU8Y5bApTppSuUkhZXN0VxHd" crossorigin="anonymous"></script>
  </body>
</html>
3.引入相关样式文件

4.书写内容
- 直接拿bootstrap预定义好的样式来使用
- 修改bootstrap原来的样式，注意权重问题
- 学好bootstrap的关键在于知道它定义了那些样式，以及这些样式能实现什么样的效果。

## 2.3 布局容器
bootstrap需要为页面内容和栅格系统包裹一个.container容器，bootstrap预先定义好了这个类，叫container它提供了两个做此用处的类。
1.container类
- 响应式布局的容器 固定宽度
- 大屏(>=1200px) 宽度定为1170px
- 中屏(>=992px) 宽度定为970px
- 小屏(>=768px) 宽度定为750px
- 超小屏(100%)
2.container-fluid类
- 流式布局容器 百分百宽度
- 占据全部视口(viewport)的容器
- 适合于单独做移动端开发


