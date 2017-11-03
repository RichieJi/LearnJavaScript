# 从零开始学习JavaScript
从以下几个方面，进行JavaScript的学些。

## 基本概念

### JavaScript引擎
|应用|引擎|
|---|----|
|Mozilla|Spidermonkey|
|Chrome|V8|
|Safari|JavaScriptCore|
|IE and Edge|Chakra|
|NodeJS|V8|
|Java6|Rhino|
|Java8|Nashorn|

作用：JavaScript引擎的代码解析和执行过程的目标就是在最短时间内编译出最优化的代码。

### 运行环境
可以是浏览器，比如谷歌、火狐浏览器，也可以是服务器，比如NodeJS平台、JVM平台。
注意点：平台相关的API接口。
比如在谷歌平台上，输出一段信息可以用如下的代码：

```javascript
var scriptText = "var power = function(n) {return Math.pow(2,n);};console.log(power(5));";
eval(scriptText);
```
上面的代码，在谷歌浏览器的控制台中运行的时候，可以看到会输出32。
同样的，在JVM平台，需要这么写：

```java
import javax.script.ScriptEngine;
public class MyDemo {
    public static void main(String... args) throws Exception {
        ScriptEngine engine = ScriptFactory.newSingletonScriptEngine();
        String scriptText = "var power = function(n) {return Math.pow(2,n);};print(power(5));";
        engine.eval(scriptText);
    }
}
```
上面的代码在JVM平台上运行的时候，同样也会输出32。

区别就在于谷歌浏览器中输出信息用的console.log函数，而JVM平台用的print函数。

## 应用领域
### 浏览器端
这个不用多说，现代浏览器就没有不支持JavaScript的，只要早html文件中引入相应的JavaScript代码即可，参见例子的html文件：[first.html](demo/first.html)。
### 服务器端
基于NodeJS平台，可以使用JavaScript创建一个Web服务器，使用以下代码即可创建一个简单的HTTP服务器：

```javascript
var http = require('http');
function myNode(request, response){
  response.writeHead(200, {'Content-type':'text/plain'});
  response.write('hello world'); //hello world
  response.end();
}
http.createServer(myNode).listen(2222); //监听2222端口
console.log('Server has started'); //在控制台提示服务启动
```
在机器上安装好NodeJS平台之后，执行

```
node start.js
```
就可以启动web服务器，访问[http://localhost:2222](http://localhost:2222)就可以看到hello world页面了。
### 桌面应用
典型的如[electron框架](https://electron.atom.io/)，就是可以使用JavaScript开发mac和windows上的跨平台桌面应用框架。

帆软的大屏应用（可以装载CVTouch上的应用程序），就是基于该框架开发的。

其他的比如桌面钉钉、桌面微信基本都是基于类似的框架。

## 基本语法
### 变量定义
包括局部变量和全局变量，以及变量的作用域。
### 基本运算
待补充。
### 控制语句
待补充。
### 函数对象
待补充。

## 编码和调试
### 浏览器端编码和调试（Chrome）
待补充。
### 服务器端编码和调试（NodeJS）
待补充。

## 高级语法
### 原型
待补充。
### this的使用
待补充。
### apply/call
待补充。

## 函数式编程
待补充。

## 常用库介绍
待补充。
