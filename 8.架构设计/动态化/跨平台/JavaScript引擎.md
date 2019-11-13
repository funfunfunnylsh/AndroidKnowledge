# JavaScript 引擎

### 前言

任何一个 web 开发者都要知道：为什么某段代码在一个浏览器上工作得很慢，但在另一个上却快得多？同样地，移动开发者需要了解：到底是什么在解释执行你的 JavaScript 代码？这都是因为 JS 引擎。

JS 引擎是浏览器的组成部分之一，负责把 JavaScript 代码转换成高效、优化的代码，这样就可以通过浏览器进行解释甚至嵌入到应用中。移动端 JS 引擎的落地场景不仅仅是 H5 开发，还可以动态下发执行脚本，在不更新应用的情况下升级功能降低重要功能硬编码带来的问题。

作为一个想持续发展的 web、移动或应用程序开发人员，你应该时刻关注 JavaScript 引擎的变化。

### 什么是 Javascript 引擎？

> 计算机自身是不懂我们编写的 Javascript，因此需要 Javascript 引擎去转换 Javascript 代码成计算机能识别的机器码，这样才能被处理，如下图：
>
>![](https://upload-images.jianshu.io/upload_images/2444638-a7dc02890571252a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1000/format/webp)
>
>- 堆栈底部是机器码，这是机器能识别并基于它运行，但机器码非常难编写
>- 因此我们以不同的语言远离机器码，如在机器码之上的汇编语言，但这仍然很像机器码
>- 出现了 C++ 或 C，这些语言远离难以理解的机器码，却仍保留不少它原有的能力，因此十分流行。
>- 最终出现了最上方的 Javascript，多层远离机器码，因此当我们写 Javascript 的时候我们需要一种方式去转换成机器码，让机器明白我们想要做什么。

- [【译】一篇给小白看的 JavaScript 引擎指南](http://web.jobbole.com/84351/)
> 本文「全面又不过多深入」地讲解了 JS 引擎，容易理解，适合入门。

- [如何在iOS和Android上选择一个JavaScript 引擎进行应用开发](https://www.oschina.net/translate/how-to-choose-a-javascript-engine-for-ios-and-android-apps?cmpc)

### 方案

#### 1. V8

> V8 是 Google 基于 C++ 编写并在 Google Chrome 浏览器使用的高性能开源 Javascript 引擎。

- [【译】Google V8 引擎工作原理](https://juejin.im/post/5b5014565188251ad06b6091)
> 本文详解了 V8 两个编译器的作用和工作流程。V8 引擎采用惰性优化的方式来提高性能，通过针对运行时的热点函数优化，快编译和慢优化的结合，而且通过合理的类型推断解决了 JavaScript 的类型问题。开始阅读本文来接触 V8 优化的魔法吧！

- [认识V8引擎](https://zhuanlan.zhihu.com/p/27628685)
> 深度好文！作者对 V8 的介绍娓娓道来，从解释型语言的缺点开始，引出 JavaScript 的特点，再带出 V8 是如何使得 JavaScript 性能有大幅提升的，具体有什么机制，有哪些优化。相信读完本文，你会对 V8 有个整体的认识。

- [V8 Ignition：JS 引擎与字节码的不解之缘](https://cnodejs.org/topic/59084a9cbbaf2f3f569be482)
> 有人认为 V8 引入字节码是一种退步，字节码性能是低于之前的直接转换为机器代码的。那么 V8 为什么要做这样一个退步的选择呢？引入字节码的动机又是什么呢？笔者总结了三条原因，详细阐述 V8 回到字节码怀抱的考量，图文并茂，分析非常到位！

- [【译】为什么V8引擎这么快？](https://www.xuanfengge.com/why-v8-so-fast.html)
> V8 是基于什么需求背景被研发出来的？改进了哪些地方？为什么当时的 JS 引擎这么慢，本文会给你一个答案。

- [【译】JavaScript如何工作：V8引擎深入探究 + 优化代码的5个技巧](https://segmentfault.com/a/1190000011289535)
> 深入探索了 v8 引擎的内部结构，想深入了解 v8 的小伙伴不妨一看。

#### 2. Rhino

> Rhino 是一个由 Java 实现的 JS 解析引擎，可以很容易的接入到 Java 项目中，对于现在的大前端的趋向中，可以利用 Rhino 来实现相关的跨平台渲染功能。
>  
> 个人理解相比于现在更主流的 chrome v8 引擎，Rhino 的优势在于容易应用在 Java 项目，不需要去踩交叉编译的坑。但是缺点也在于只适用于 Java 项目，v8 在功能等方面更胜一筹。
如果只是小范围使用的话，rhino 可以做为一个很好的选择。

- [Java用 Rhino/Nashorn 代替第三方 JSON 转换库](https://www.jb51.net/list/list_244_1.htm)
> 本文中，作者提出了一个新思路：自从 Java 1.6 开始就自带 JS 引擎了，为什么不用自带 js 引擎作 json 转换呢？这样我们就可以不用引入其他第三方库了呀！

