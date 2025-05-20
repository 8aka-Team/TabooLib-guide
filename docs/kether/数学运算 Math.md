<details class="lake-collapse"><summary id="uedbfa992"><span class="ne-text">「展开 / 收起详情」</span><span class="ne-text">💠</span><span class="ne-text"> Math 语句</span></summary><div id="j9ie0" class="ne-yuque">此处为语雀内容卡片，点击链接查看：<a href="https://www.yuque.com/sacredcraft/kether/reference#nLa23" target="_blank">https://www.yuque.com/sacredcraft/kether/reference#nLa23</a></div></details>
> 该语句自`2022-09-03` `TabooLib v6.0.9-77` 版本起将会过时
>
> 推荐使用 `Calculate` 语句
>



<h1 id="Ew7Ep">Math 的简单使用</h1>
---

如你所见，`Math` 语句是用来计算加减乘除的，更高级的科学计算请使用 `Calculate` 语句

语句的格式为：`math {symbol} {action list}`

其中，`{symbol}` 指的是运算符

而 `{action list}` 则是用来运算的数据集合，这个参数类型在上一篇文章 `If & Else` 介绍过了，这里不再多说。

直接上示例



```ruby
/* 加法运算：等价于 1+2+3 = 6 */
math add [ 1 2 3 ]
math + [ 1 2 3 ]


/* 减法运算：等价于 9-5-1 = 3 */
math sub [ 9 5 1 ]
math - [ 9 5 1 ]


/* 乘法运算：等价于 3x2x5 = 30 */
math mul [ 3 2 5 ]
math * [ 3 2 5 ]


/* 除法运算：等价于 6÷2 = 3 */
math div [ 6 2 ]
math / [ 6 2 ]
```



不过这里需要额外注意一下

当两个整数不能被整除时，得到的结果可能会被强制转型

例如：`math div [ 9 2 ]` 等同于 `9 ÷ 2` 得到的结果应该是小数 `4.5`

但事实上得到的是 `4`，为什么会这样呢？

学过编程的同学应该已经知道原因了，这里给没接触过编程的同学简单解释一下

简单来说就是 `9` 跟 `4` 会被系统当成整数来运算

两个整数进行运算，无论结果是啥，系统最后都会把结果转化为整数

但是，只要算式中有一个实数（非整数或小数），那么最后算出来的就会是实数，不会给你转成整数

例如：

`math div [ 6 2.0 ]` 等同于 `6 ÷ 2.0` 结果是 `3.0`

`math div [ 9.0 2 ]` 等同于 `9.0 ÷ 2` 结果是 `4.5`



<h1 id="TngOq">Math 的拓展用法</h1>
---

除了上面几种用法，`Math` 还有一种比较舒服的写法



```ruby
/* 计算 1 + 3 x 6 ÷ 3 - 2 */
math 1 + 3 * 5 / 6 - 2
```



这个写法可能更容易理解一些，只要注意别把运算符紧挨到 `math` 后面就行了。

这个写法可能更容易理解一些，不过需要注意几个地方：

1. 请勿将运算符紧挨到 `math` 后面：`math + 3 - 5`，这样会被识别成第一种情况而出现报错
2. 这种写法形式不支持括号
3. 这种写法的运算顺序为从左到右，无视运算符的优先级







