---
title: Web前端与可视化
icon: post
order: 2
author: 宋玉
date: 2023-07-28
category:
  - 数据可视化
tag:
  - 概念
  - 指南
sticky: false
star: false
---

::: warning 声明
本文内容源自极客时间专栏：[《跟月影学习可视化》](https://time.geekbang.org/column/intro/100053801)

搬运不是初心，目的是为了更好的学习，随着时间的推移，本系列会不断融入我自己的产出。
:::

![](https://files.sunguoqi.com/brain-images/202307281145278.png)

## 可视化是什么

抗击新冠疫情的三年间，我们几乎每天都会关注疫情信息。

不知道你有没有注意过这些疫情信息的展现方式。除了一些基础的疫情数据外，我们还可以看到各种丰富的图表。

这种图表信息与普通的网页看上去差别非常大，我们没办法用传统的 Web 开发技术实现这样的“网页”。没错，这是一个与传统 Web 开发完全不一样的领域，叫做**数据可视化**（Data Visualization）。

![](https://files.sunguoqi.com/brain-images/202307281157862.jpg)

如果要给可视化下一个定义，我觉得应该是这样的：

**可视化是将数据组织成易于为人所理解和认知的结构，然后用图形的方式形象地呈现出来的理论、方法和技术。**

实现可视化有两个关键要素，一个是**数据**，另一个是**图形**。如果要考虑在计算机上呈现，那还要加上**交互**。

## Web 前端与可视化有什么区别？

前端工程师主要负责处理内容呈现和用户交互。可视化的数据呈现，尤其是在 Web 端的呈现，也属于前端工程师的范畴。但是，与传统的前端开发相比，可视化开发的工具、思路和方法，又和 Web 有着比较大的区别。

### 技术栈不同

Web 开发主要以 HTML 来描述结构，以 CSS 来描述表现，以 JavaScript 来描述行为。而可视化则较少涉及 HTML 和 CSS，它更多地要同浏览器的 Canvas、SVG、WebGL 等其他图形 API 打交道。这是因为，Web 开发以呈现块状内容为主，所以 HTML 是更合适的技术。而可视化开发因为需要呈现各种各样的形状、结构，所以，形状更丰富的 SVG 以及更底层的 Canvas2D 和 WebGL 就是更合适的技术了。

![](https://files.sunguoqi.com/brain-images/202307281150404.png)

### 业务重点不同

Web 开发着重于处理普通的文本和多媒体信息，渲染普通的、易于阅读的文本和多媒体内容，而可视化开发则着重于处理结构化数据，渲染各种相对复杂的图表和图形元素。两者针对的信息特征和对图形渲染的要求有所不同，所以，在细节处理上也有比较大的差异。

![](https://files.sunguoqi.com/brain-images/202307281213070.png)

## Web 开发—>数据可视化

尽管 Web 前端与可视化在工具、思路和方法上有一些区别，但前端开发的同学想要学习可视化，门槛并不高，主要原因有三点。

- 可视化与 Web 前端一样，最终都是以图像呈现在浏览器上，因此有许多通用的方法论。比如，两者都要涉及 DOM、都要处理浏览器事件、都采用同样的颜色表达方式和同样的资源请求方法等等。

- 二者都使用 JavaScript，而且都是浏览器端的 JavaScript。所以，就 JavaScript 的应用而言，这一块差别并不大。不过，可视化应用面对的数据和渲染的图形元素都比传统的 Web 应用更复杂一些，所以也就更加依赖 JavaScript 一些。

- Web 前端领域有许多成熟的工具，包括响应式框架（比如，三大框架 Vue、React、Angular）、设计系统（比如 Ant Design、ElementUI）、函数库（比如，Underscore、Lodash）等等。与 Web 前端一样，可视化领域也有丰富的 JavaScript 工具和活跃的生态，通常这些“开箱即用”的工具，就能够帮助我们完成可视化开发。

因此，只要善于使用这些成熟的可视化工具，我们就能高效率地完成手头的工作。

## 可视化领域的工具

可视化领域经过多年的发展，有非常多丰富的工具。这些工具大体上可分为四类：

- 呈现各种类型图表的图表库；
- 处理地图、地理位置的可视化地理库；
- 处理视觉呈现的渲染库；
- 处理数据的数据驱动框架。

### 图表库

可视化应用通常需要绘制大量的图表，比如，柱状图、折线图、饼图，还有一些简单的平面地图等等。图表库能够帮助我们快速把它们绘制出来。

社区中有许多优秀的开源图表库，比如[ECharts](https://echarts.apache.org/zh/index.html)，类似的还有 [Chartlist](https://gionkunz.github.io/chartist-js/)、[Chart](https://www.chartjs.org/) 等等，它们都属于图表库。

![](https://files.sunguoqi.com/brain-images/202307281406593.png)

### 地理库

如果要绘制更加复杂的地图，比如，一座城市的交通线路和建筑物三维模型，或者一个园区的立体建筑模型等等，我们可能要依赖专业的 GIS 地图库。社区中比较成熟的 GIS 库也不少，比较常见的像 [Mapbox](https://www.mapbox.com/)、[Leaflet](https://leafletjs.com/)、[Deck.gl](https://deck.gl/)、[Cesium](https://cesium.com/) 等等。

![](https://files.sunguoqi.com/brain-images/202307281409593.png)

### 渲染库

如果要绘制其他更灵活的图形、图像或者物理模型，我们常用的一些图表库就不一定能完成了。这个时候，我们可以用 [Three](https://threejs.org/)、[Sprite](https://spritejs.com/#/) 这样比较通用的渲染库（实际上图表库或 GIS 地图库本身底层渲染也基于这些渲染库）。

![](https://files.sunguoqi.com/brain-images/202307281411038.png)

### 数据驱动框架

除了这些库之外，还有一类比较特殊的库，比如 [D3.js](https://d3js.org/)，它属于数据驱动框架。那什么是数据驱动框架呢？

这是一种特殊的库，它们更专注于处理数据的组织形式，而将数据呈现交给更底层的图形系统（DOM、SVG、Canvas）或通用图形库（SpriteJS、ThreeJS）去完成。

D3.js 与图表库一样，都能完成可视化项目中的各种图表展现，但是它们之间也有区别。

ECharts 等大部分图表库会提供封装好的图表类型，我们只需要简单配置一下参数就可以使用。但正因为如此，图表能够表现的形式也会被预设的图表类型和封装好的参数所固定了。如果我们想做一些非常个性化的视觉呈现形式，用图表库来做，相对就比较困难。

而 D3.js 因为只关注数据的组织形式，将具体的渲染交给底层去做，所以更加灵活，扩展起来也很方便。但相对地，就不像其他的图表库一样，拥有完整的封装了，使用的门槛也就相对高一
些。

![](https://files.sunguoqi.com/brain-images/202307281412450.png)