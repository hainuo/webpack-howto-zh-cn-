## 前言
这篇教程是来自petehunt大神的，reactjs会议上的很多演讲都是他讲的。这篇文章也是他在将如何构建instagram中讲到。如下翻译给大家。

## 教程的目的

这是一个小教程告诉大家如何能够良好的使用webpack.这里包括了我们在构建Instagram中使用的大部分东西。

我的建议是：以这篇教程为指引开始你的webpack之旅，之后在看官方教程。

## 预备知识

1 你应该知道browserify、RequireJS或者类似的。

2 你应该懂得以下词汇的定义：

Bundle splitting

Async loading

Packaging static assets like images and CSS.

## 1 为什么我们使用webpack?

1.1 因为他和browserify一样可以将你的应用分离成很多个文件。如果你在单页面应用里有很多个页面，用户只需要下载当前页面的代码。如果他们转向了另一个页面，他们不需要重复的下载公用的代码。

1.2 这个工具可以代替grunt或者gulp。 因为他可以生成和打包CSS、预编译的CSS、可编译成JS的语言、还有图片什么的。

Webpack支持AMD,CommonJS,和其他一些模块系统（Angular,ES6）.如果你不知道用哪个，就用CommonJS吧。

## 2 写给使用browerify的同学

以下这些是等价的：

`browserify main.js >bundle.js`

`webpack main.js bundle.js`

但是webpack要更强大，因为你可以使用webpack.config.js去管理你要做的事情：

`module.exports={`

  `entry:'./main.js',`

  `output:{`

    `filename:'bundle.js'`

    `}`

  `};`

  这就仅仅是js而已，所以可以写js哈。

## 怎样去调用webpack

在包含webpack.config.js的目录里，运行：

    webpack： 仅仅build一次在dev的模式下
    webpack -p : 在produc的环境下build一次
    webpack --watch:在文件有改变的时候 会build
    webpack -d: to include source maps
