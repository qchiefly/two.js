<h1 id="masthead" style="display: block; width: 285px; height: 80px; background: url(http://jonobr1.github.io/two.js/images/logo.gif) center center no-repeat; overflow: hidden; text-indent: -9999px;">two.js</h1>

> A two-dimensional drawing api meant for modern browsers. It is renderer agnostic enabling the same api to render in multiple contexts: webgl, canvas2d, and svg.

一个二维的绘图 API，用于现代 Web 浏览器，可基于不同上下文绘制，包括 webgl、canvas 和 svg。

[主页](http://jonobr1.github.com/two.js) • [例子](http://jonobr1.github.com/two.js/#examples) • [文档](http://jonobr1.github.com/two.js/#documentation) • [帮助](http://stackoverflow.com/questions/tagged/two.js)

## 用法
下载 [minified library](https://raw.github.com/jonobr1/two.js/master/build/two.min.js) 并引入到你的HTML. 或者查看 [how to build the library yourself](https://github.com/jonobr1/two.js#custom-build).

```html
<script src="js/two.min.js"></script>
```

下面是用two.js实现旋转矩形的一个HTML样例:

```html
<!doctype html>
<html>
  <head>
    <script src="js/two.min.js"></script>
  </head>
  <body>
    <script>
      var two = new Two({
        fullscreen: true,
        autostart: true
      }).appendTo(document.body);
      var rect = two.makeRectangle(two.width / 2, two.height / 2, 50 ,50);
      two.bind('update', function() {
        rect.rotation += 0.001;
      });
    </script>
  </body>
</html>
```

## 自定义安装
Two.js 应用于 [nodejs](http://nodejs.org/) 所需源文件. 第一步你将安装nodejs. 接着安装 [node-minify](https://npmjs.org/package/node-minify):

```
cd two.js/utils
npm install node-minify
```

接着用文本方式打开 `./utils/build.js` . 在头部有个叫 `files`的数组. 这是需要编译到安装源的源文件序列. 根据你自己的需求进行增删改.

若你开发应用并只使用一种渲染方式（如：svg）,则强烈建议从你的安装中去除canvas和webgl渲染器以大大的减少文件数量.

最后，创建它:

```
cd two.js/utils
node build
```

## Change Log

2013 05 01 [v0.2.0](https://github.com/jonobr1/two.js/tree/v0.2.0)
+ 第一个 alpha 版

Jan 29, 2013 [v0.1.0-alpha](https://github.com/jonobr1/two.js/tree/v0.1.0-alpha)
+ 理念来自 Three.js
