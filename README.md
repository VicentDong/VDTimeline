# VDTimeline

时间线组件,基于 js、 Lodash 的时间线控件，支持：

- （1）滑动加载
- （2）播放，快进，快退，回到第一项，回到最后项，前一项，后一项
- （3）自动播放

## 使用环境

VDTimeline 支持浏览器和 Nodejs 中引入<br >
浏览器支持：IE8+，Chrome，Firefox，Safari 等<br >

## 安装

VDTimeline 支持多种形式的引入，包括 script，ES6，AMD，commonJS 方式的引入。<br >

使用 SCRIPT 标签引入 VDTimeline 时，会创建全局的变量 VDTimeline 进行调用。<script src="VDTimeline.js"></script><br >

使用 require(‘VDTimeline’)方式引入<br >

ES2015 模块 如 import VDTimeline from ‘VDTimeline’<br >

## 使用

根据具体应用场景，参考上章节的 script 引入方式进行 VDTimeline 的安装。<br >
为了减少包的体积，VDTimeline 抽离了部分公用 JS，如 Lodash。基于此，需要在使用时手动引入支持 lodash,可以自行采用 CDN 加速<br >

## 发布目录结构

VDTimeline<br >
-- fonts<br >
-- index.html<br >
-- main.css<br >
-- VDTimeline.js<br >
-- VDTimeline.js.map<br >

（1）fonts 文件夹<br >
内含 VDTimeline 使用的字体资源，使用时需要添加到项目<br >
（2）Index.html<br >
这个 Html 是作为 VDTimeline 的演示/实例的 html 入口，项目引入可以删<br >
（3）main.css<br >
Css 文件是 VDTimeline 加载时需要调用的样式文件，项目需要引入<br >
（4）VDTimeline.js<br >
Js 文件，是 VDTimeline 的主要 Js 文件，项目需要引入<br >

## 示例

这里以 script 方式引入进行举例，具体使用示例如下:<br >

### 首先创建 html 文件

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>   
</head>
<body>
 <div class="container">
  </div>
</body>
</html>

### 引入相关 JS 和 VDTimeline，可以放在头部，或者 body 元素内部

- <script src='https://cdn.bootcss.com/lodash.js/4.17.15/lodash.min.js'></script>

- <script type='text/javascript' src='VDTimeline.js'></script>

### 初始化

var myVDTimeLine = VDTimeline.init(
//  容器<br >
container:document.querySelector('.container'),<br >
//  数据<br >
data:[]<br >
)<br >

### 调用方法

myVDTimeLine.stop();<br >

## 配置

//  容器

- container: null,
  //  数据
- data: [],
  //  播放间隔
- interval: 2000,
  //  类目个数
- size: 10,
  //  快进/快退速度
- speed: 5,
  //  是否显示播放按钮
- showPlayBtn: true,
  //  是否显示回到第一项按钮
- showStartBtn: true,
  //  是否显示回到最后一项按钮
- showEndBtn: true,
  //  是否显示快退按钮
- showBackBtn: true,
  //  是否显示快进按钮
- showForwardBtn: true,
  //  是否显示前一项按钮
- showNextBtn: true,
  //  是否显示后一项按钮
- showPrevBtn: true,
  //  播放
- play: null,
  //  暂停
- stop: null,
  //  第一项
- toStart: null,
  //  最后一项
- toEnd: null,
  //  快退
- toBack: null,
  //  快进
- toForward: null,
  //  下一项
- toNext: null,
  //  前一项
- toPrev: null,
  // 自动播放
- autoPlay: false

## 方法

### init-初始化

- 参数：option<br >
- 描述：进行 VDTimeline 的实例的创建和初始化<br >

### Play-播放

- 参数：function 回调<br >
- 描述：组件播放，支持传入回调方法<br >
- 回调参数：<br >
  data:当前项的数据<br >
  index：当前项的索引（当前时间项的索引）<br >
  start：当前时间轴的开始项索引（data 数组内索引）<br >
  end：当前时间轴的结束项索引（data 数组内索引）<br >

### Stop-停止

如上

### toStart-回到第一项

如上

### toEnd-回到最后一项

如上

### toBack-快退

如上

### toForward-快进

如上

### prev-前一项

如上

### next-下一项

如上
