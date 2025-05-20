在 Kether 中，任何动作的返回值都是可以被我们临时储存起来，方便再次使用的，我们一般将其称为变量  
  
需要注意的是，储存起来的变量只能在当前正在运行的 Kether 中使用，当 Kether 语句全部执行完毕后，储存起来的变量将会被释放。你无法在下一次运行 Kether 时去使用上一次运行储存的变量，这是不大可能的。



<h1 id="seA4D">设置变量</h1>
我们先来看看如何设置变量

<details class="lake-collapse"><summary id="u6e0d6422"><span class="ne-text">「展开 / 收起详情」</span><span class="ne-text">💠</span><span class="ne-text"> Variable Set 语句</span></summary><div id="VgqIl" class="ne-yuque">此处为语雀内容卡片，点击链接查看：<a href="https://www.yuque.com/sacredcraft/kether/reference#Kx5Iu" target="_blank">https://www.yuque.com/sacredcraft/kether/reference#Kx5Iu</a></div></details>
设置变量有两种写法：

+ `set {key} {token}`
+ `set {key} to {action}`

它们的区别也很明显，一个支持将文本作为变量，另一个支持将语句返回值作为变量

如果你只想将一段普通文本设置为变量，那么我更推荐你用第一种写法



```ruby
/* 设置文本变量 */
set text "Crazy KFC vivo 50."


/* 将玩家名字作为变量存储 */
set name to player name


/* 存储玩家血量 */
set health to player health
```



需要注意的是如果你重复使用 **同一个变量名 **来储存数据，那么会将覆盖上一次存储的数据



这里稍微说一下，Kether 里的变量名并没有像 Java、Kotlin 编程语言那样有那么多那么严格的规定  
事实上，变量名写什么都是可以的，包括空格、中文以及特殊符号都是允许的。但我还是建议你尽量使用符合规则的变量名吧，例如：数字、字母和下划线或横杠等  
实在不行中文变量名也可以（你看着舒服就行）  
你硬是要用奇奇♂怪怪的变量名我也拦不住你对吧 awa  
❗ 注意，如果你的变量名含有空格的话请不要忘记加上英文引号



<h1 id="bsFps">获取变量</h1>
<details class="lake-collapse"><summary id="u8c8c564e"><span class="ne-text">「展开 / 收起详情」</span><span class="ne-text">💠</span><span class="ne-text"> Variable Get 语句</span></summary><div id="uipzj" class="ne-yuque">此处为语雀内容卡片，点击链接查看：<a href="https://www.yuque.com/sacredcraft/kether/reference#tohxA" target="_blank">https://www.yuque.com/sacredcraft/kether/reference#tohxA</a></div></details>
获取变量的方法也非常简单：`&<变量名>`

需要注意的是，如果之前没有定义变量，或系统没有提供内置变量，则获取到的变量可能为 `null`



```ruby
/* 打印变量 */
print &test


/* 在 Math 中使用变量 */
print math mul [ &health 0.6 ]


/* 检查获取到的变量是否为空 */
if check &test is null then {
    tell "变量为空"
} else {
    tell "变量不为空"
}
```



❗ 注意，如果你的变量名含有空格的话请不要忘记加上英文引号



<h1 id="pILtH">变量的拓展用法</h1>
接下来我们学点好玩的内容



`Variable Get` 和 `Variable Set` 语句除了可以用来获取，定义变量之外，还有个特殊的用法，那就是获取或修改变量对象的内部属性。



对于数组对象，我们可以直接获取其内部的值

现有一个数组 `set test to array [ 1 1 4 5 1 4 ]`，赋值给变量 `test`，内部有六个数字。

要打印第四个数字，则可以这么写 `print &test[3]`，数组下标从 0 开始，第四个数字下标为 3

```ruby
set test to array [ 1 1 4 5 1 4 ]

/* 获取第四个数字 */
print &test[3]
```

运行结果：`5`



对于字符串对象，我们可以直接获取它对应的大小写字符串

现有一个字符串 `set test to "Hello World!"`，赋值给变量 `test`

要打印其大写形式的字符串，则可以这样写 `print &test[uppercase]`

```ruby
set test to "Hello World!"

/* 打印全大写形式字符串 */
print &test[uppercase]
```

运行结果：`HELLO WORLD!`



通过在中括号内指明该对象的属性，即可获取其对应属性的值。

当然，除了获取属性以外，还能通过使用 `Variable Set` 语句来设置属性



例如我们修改上述数组第三个数字

```ruby
set test to array [ 1 1 4 5 1 4 ]

/* 修改第三个数字 */
set &test[2] to 6

/* 输出结果 */
print &test
```

运行结果：`[1, 1, 6, 5, 1, 4]`



原生 Kether 内置的属性比较少。如果你希望获得更多支持的属性，不妨考虑使用 Vulpecula

