## HTML
1. DOCTYPE的作⽤？

DOCTYPE是html5标准⽹⻚声明，且必须声明在HTML⽂档的第⼀⾏。来告知浏览器的解析器⽤什么⽂档标准解析这个 ⽂档，不同的渲染模式会影响到浏览器对于 CSS 代码甚⾄ JavaScript 脚本的解析

⽂档解析类型有： 
- BackCompat：怪异模式，浏览器使⽤⾃⼰的怪异模式解析渲染⻚⾯。（如果没有声明DOCTYPE，默认就是这个 模式） 
- CSS1Compat：标准模式，浏览器使⽤W3C的标准解析渲染⻚⾯。 
- IE8还有⼀种介乎于上述两者之间的近乎标准的模式，但是基本淘汰了

2. meta标签有哪些常见的形式？

meta标签由name和content两个属性来定义，来描述⼀个HTML⽹⻚⽂档的属性，例如作者、⽇期和时间、⽹⻚描述、 关键词、⻚⾯刷新等，除了⼀些http标准规定了⼀些name作为⼤家使⽤的共识，开发者也可以⾃定义name

常见形式：
- charset，⽤于描述HTML⽂档的编码形式
```
<meta charset="UTF-8" >
```
- http-equiv，顾名思义，相当于http的⽂件头作⽤,⽐如下⾯的代码就可以设置http的缓存过期⽇期
```
＜meta http-equiv="expires" content="Wed, 20 Jun 2019 22:33:00 GMT"＞
```
- viewport，移动前端最熟悉不过，Web开发⼈员可以控制视⼝的⼤⼩和⽐例
```
<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1">
```
- apple-mobile-web-app-status-bar-style,开发过PWA应⽤的开发者应该很熟悉，为了⾃定义评估⼯具栏的颜⾊
```
<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
```
3. src和href的区别？

src是指向外部资源的位置，指向的内容会嵌⼊到⽂档中当前标签所在的位置，在请求src资源时会将其指向的资源 下载并应⽤到⽂档内，如js脚本，img图⽚和frame等元素。当浏览器解析到该元素时，会暂停其他资源的下载和处 理，知道将该资源加载、编译、执⾏完毕，所以⼀般js脚本会放在底部⽽不是头部

href是指向⽹络资源所在位置（的超链接），⽤来建⽴和当前元素或⽂档之间的连接，当浏览器识别到它他指向的 ⽂件时，就会并⾏下载资源，不会停⽌对当前⽂档的处理

4. defer和async的区别？

defer：浏览器指示脚本在⽂档被解析后执⾏，script被异步加载后并不会⽴刻执⾏，⽽是等待⽂档被解析完毕后执⾏

async：同样是异步加载脚本，区别是脚本加载完毕后⽴即执⾏，这导致async属性下的脚本是乱序的，对于script 有先后依赖关系的情况，并不适⽤


5. 前端存储方式和区别？

前端存储方式有以下几种方式：cookies、localstorage、sessionstorage、Web SQL、IndexedDB

区别如下：

cookies： 在HTML5标准前本地储存的主要⽅式，优点是兼容性好，请求头⾃带cookie⽅便，缺点是⼤⼩只有4k， ⾃动请求头加⼊cookie浪费流量，每个domain限制20个cookie，使⽤起来麻烦需要⾃⾏封装 

localStorage：HTML5加⼊的以键值对(Key-Value)为标准的⽅式，优点是操作⽅便，永久性储存（除⾮⼿动删 除），⼤⼩为5M，兼容IE8+ 

sessionStorage：与localStorage基本类似，区别是sessionStorage当⻚⾯关闭后会被清理，⽽且与cookie、 localStorage不同，他不能在所有同源窗⼝中共享，是会话级别的储存⽅式 

Web SQL：2010年被W3C废弃的本地数据库数据存储⽅案，但是主流浏览器（⽕狐除外）都已经有了相关的实 现，web sql类似于SQLite，是真正意义上的关系型数据库，⽤sql进⾏操作，当我们⽤JavaScript时要进⾏转换， 较为繁琐

IndexedDB： 是被正式纳⼊HTML5标准的数据库储存⽅案，它是NoSQL数据库，⽤键值对进⾏储存，可以进⾏快 速读取操作，⾮常适合web场景，同时⽤JavaScript进⾏操作会⾮常⽅便。


