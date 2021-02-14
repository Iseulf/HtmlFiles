## 一、`clear`属性
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;用于去除浮动元素对当前元素所产生的影响，可选值有：
* left：去除左侧元素对当前元素的影响
* right：去除右侧元素对当前元素的影响
* both：去除两侧中最大影响的

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;注意设置不是对浮动元素设置，而是对想要不受影响的元素设置。原理是对元素加一个相应的外边距。

## 二、`clear`解决高度塌陷
利用`::after`伪元素选择器和`clear`属性可以解决高度塌陷的问题，如
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .box1{
            border: 2px red solid;
        }
        .box2{
            width: 100px;
            height: 100px;
            background-color: orange;
            float: left;
        }
        .box1::after{
            content: "";
            display: block;
            clear: both;
        }
    </style>
</head>
<body>
    <div class="box1">
        <div class="box2"></div>
    </div>
</body>
</html>
```
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;在`box1`中加一个没有内容的模块，并将之设置为块元素，加以`clear`属性即可去除高度塌陷影响。