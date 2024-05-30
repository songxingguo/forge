---
title: Countdown
icon: post
order: 1
author: 宋玉
date: 2024-04-15
category:
  - 分类
tags:
  - 编程/Demo
---
```js
const { useState, useEffect } = React;
const App = (props) => {
const [count, setCount] = useState(100);
useEffect(() => {
  setInterval(() => {
	setCount(count - 1);
  }, 1000);
}, [count]);
return (
  <div>
	<h1>{props.title}</h1>
	<div>{count}</div>
	<div>
	  <button>开始</button>
	  <button>结束</button>
	  <button>暂停</button>
	</div>
  </div>
);
```

### [Countdown DEMO](https://brain.songxingguo.com/demo/Countdown/Countdown.html)
  
<HtmlEditor  src="/demo/Countdown/Countdown.html"/>

