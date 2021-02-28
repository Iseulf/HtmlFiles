<!--
 * @Descripttion : 
 * @Author       : Seulf
 * @Date         : 2021-02-09 12:47:11
 * @LastEditors  : Seulf
 * @LastEditTime : 2021-02-28 13:53:54
-->

## 一、高度塌陷

父元素是块元素, 且其中的子元素是 `float` 的话, 会出现父元素的高度不随子元素而撑开, 从而导致父元素下的块元素会挤上去, 如下所示
<center><img src="https://seul-1302377718.cos.ap-nanjing.myqcloud.com/markdown/20210209125958.png" width=80%></center>

这种情况就称为高度塌陷.

高度塌陷问题的解决方法:

* 把父元素的高度写明, 但这就不能让父元素高度随子元素变化了
* 采用BFC

## 二、BFC(Block Formatting Context)

BFC: 块级格式化环境. BFC是css的一个隐藏属性, 作用是将一个元素变为独立的布局区域. 开启BFC之后的元素特点:

* 开启BFC的元素不会被浮动元素所覆盖
* 开启BFC的元素子元素和父元素外边距不会重叠
* <span style="color:red">开启BFC的元素可以包含浮动的子元素</span>, 也即高度会随浮动子元素变化

### 1、开启BFC的方法

1. 设置元素为浮动（不推荐）
2. 将元素设置为行内块元素（不推荐）
3. <span style="color :red">将元素`overflow`设置为非visible值, 也即非默认值, 常用设置为hidden</span>(推荐)
