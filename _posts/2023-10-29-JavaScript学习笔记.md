---
layout: post
author: Zierc
---

# JavaScript 学习笔记

## 导航

- [简介](#简介)
- [引入 HTML](#引入-html)
- [输出方式](#输出方式)
- [变量](#变量)
  - [ES5 中的六种数据类型](#es5-中的六种数据类型)
  - [ES6 中新加的一个数据类型](#es6-中新加的一个数据类型)
  - [常用对象](#常用对象)
    - [Math](#math)
    - [Date](#date)
    - [DOM](#dom)
- [运算符](#运算符)
- [函数](#函数)

---

## 简介

- 轻量级脚本语言
- 可以插入 **html** 页面并被所有浏 览器运行
- 学习容易 ?

### 组成

---

## 引入 HTML

两种方式

1. 直接在 html 脚本中的 script 中写 js 代码

```html
<script>
  function ChangeText() {
    x = document.getElementById("demo");
    x.innerHTML = "Hello JavaScript";
  }
</script>
```

> 注：html 代码中 script 标签可以写在任意位置

2. 先创建一个本地 js 文件/获取网络 js 文件 再通过"script src"把他引入

```html
<script src="文件地址"></script>
```

---

## 输出方式

1. 弹出框
   ```javascript
   alert("输出内容");
   ```
2. 直接输出到页面上

   ```javascript
   document.write("输出内容(可以包含html的代码)");
   ```

3. 控制台
   ```javascript
   console.log("要输出的内容");
   ```

---

## 变量

### ES5 中的六种数据类型

1.  原始数据类型/ 基本数据类型

    - 数值
    - 布尔值
    - 字符串

    ```javascript
    var age = 20; //数值
    var name = "你好"; //字符串
    var t = true; //布尔
    ```

2.  合成数据类型/ 引用数据类型

    - null
      > 数据为空值 引用类型中的空
    - undefined
      > 数据不为空 但是没有初始化 基本类型里的空
    - 对象

```javascript
//赋值使用:
var user = {
  name: "wang",
  age: 19,
  t: true,
  get: function () {
    //对象方法
  },
  array: [""],
};
```

> 可以说**没有数据类型声明**可言 泛型
> 赋值类似写作表达 可以说很亲民
> **对象类型**组成数据甚至不需要说明是数据

> null undefined 日常使用时意思几乎一样 为什么有两个呢? 有一部分[历史原因 :)](https://juejin.cn/post/6952747073124958245)

### ES6 中新加的一个数据类型

### 常用对象

#### Math

1. 方法
   1. 静态
      Math.abs() 绝对值
      Math.max/min() 最大小值
      Math.floor/ceil() 取整
      Math.random() 随机数(>=0 <1)

#### Date

> 单位是毫秒 默认从 1970 1 月 1 日 00.00.00 作为时间的零点

> 实例对象可以直接输出

1. 方法

   1. 静态
      Date.now()
   2. 非静态
      getTime :返回实例距离零点的毫秒数
      getDate : 返回实例对象对应每个月的几号
      getDay : 返回星期( 周日为 0 周一为 1 ...)
      getYear : 返回距离 1900 的年数
      getFullYear :返回年份
      getMonth : 返回月份 0 表示 1 月 ...
      getHours :返回小时
      getMilliseconds :返回毫秒
      getMinutes :返回分钟
      getSeconds :返回秒

#### DOM

> 它将网页转为 javascript 的一个对象 从而让 js 能够通过节点控制网页操作

如果将 document 打印 会得到整个 html 的代码

##### Node.nodeType 属性

- 文档节点(document) :9 Node.DOCUMENT_NODE
- 元素节点(element) :1 Node.ELEMENT_NODE
- 属性节点(attr) :2 Node.ATTRIBUTE_NODE
- 文本(text) :3 Node.TEXT_NODE
- 文档片段节点(DocumentFragment):11 Node.DOCUMENT_FRAGMENT_NODE

##### 获取元素

> 通过 innerHTML 可以修改整个元素

- document.getElementsByTagName("x")
  返回文档中所有 x html 元素
- document.getElementsByClassName("x")
  返回文档中所有 x 类的元素(一般表示 CSS 的元素)

---

## 运算符

- 算数
- 赋值
- 比较
- 布尔
  > ^这四种与其他编程语言类似
- typeof
  > 检测数据类型 number boolean object

```javascript
var name = "wang";
var user = {
  name: "",
  age: 10,
  t: true,
};
console.log(typeof name); //string
console.log(typeof user); //object
```

---

## 函数

```javascript
function funcName(参数1, 参数2) {
  //函数实现
}
```

无返回类型声明 无参数类型声明 无作用域声明 主打的就是简单

要返回就直接 return
