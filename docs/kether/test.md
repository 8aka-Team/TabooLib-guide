---
sidebar_position: 1
---

> 本文主要借助一些常见的语句来展开讲解几个语句的基本概念。

# 语句的简单使用

我们先来从几个比较基础的语句开始说起

## Print 语句
:::tips
`print {action}`

:::

<!-- <details class="lake-collapse"><summary id="u98a91143"><span class="ne-text">「展开 / 收起详情」</span><span class="ne-text">💠</span><span class="ne-text"> Print 语句</span></summary><div id="eJsUq" class="ne-yuque">此处为语雀内容卡片，点击链接查看：<a href="https://www.yuque.com/sacredcraft/kether/reference#pPdnb" target="_blank">https://www.yuque.com/sacredcraft/kether/reference#pPdnb</a></div></details> -->


这个语句可以将消息输出到控制台，语句后面写了什么它就会在控制台上输出什么信息

其中 `{action}` 为语句的参数，在这个位置的内容会被当做参数传入 Print 语句，然后在控制台中输出

例如我们在控制台中使用 `Vulpecula` 插件试着玩一下这个语句，能得到这样的效果

:::tips
>`/vul eval<font style="color:#601BDE;"> </font><font style="color:#C75C00;">print</font> "<font style="color:#4C16B1;">今天翻的是书"</font>`

<!-- - [Vulpecula] **今天翻的是书** -->

<!-- **<font style="color:#AE146E;">‹ ›</font>** Result: kotlin1510.Unit -->

:::

这里我们可以看到，紫色部分 `<font style="color:#4C16B1;">今天翻的是书</font>` 位于 Print 语句的 `{action}` 参数位置，因此它被作为参数传入了 Print 语句，并被 Print 语句输出到了控制台上。



## Tell 语句
:::tips
`tell {action}`

:::
