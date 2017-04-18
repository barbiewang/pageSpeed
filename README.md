# pageSpeed
## 此文件夹包含两部分内容：
* 用PageSpeed Insights测试工具测试index.html网页的得分;
* 优化pizza.html网页相关内容，使fps达到60以上。
## 第一部分：测试index.html
### 1. 测试方法：
+ 下载此文件夹到您的电脑，并将本文件夹放置在您的本地服务器上（前提是您已经搭建好本地服务器）；
+ 登录[google pageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/)页面,输入index.html的网页地址，在该网站上进行分析。
### 2. 优化途径：
- 将外部css及js文件保存为内部文件，避免远程查找，消耗时间；
- 将js设为async,避免阻塞dom渲染；
- 将原本内部的style.css文件内联至html文件中，加快该css文件的查找和渲染；
- 压缩图片大小，大大减少网页下载量；
- 将font.css文件链接设置为```<link href="css/font.css" rel="stylesheet"  media="none" onload="if(media!='all')media='all'" > ```，不阻塞渲染地加载css。
## 第二部分：测试pizza.html
### 1.测试方法：
使用Google浏览器打开pizza.html网页，并打开Google develop tools中的Timeline.
### 2. 优化途径：
+ 用getElementById或getElementsByClassName替换querySelector或QuerySelectorAll,提高查找速度；
+ 修改导致强制回流的代码，避免强制回流而导致的页面加载速度缓慢；
+ 使用 requestAnimationFrame() 进行连续的帧操作, 它能减少掉帧的概率，使得动画更加流畅
+ 修改for循环中的相关数值，避免无必要的循环。
