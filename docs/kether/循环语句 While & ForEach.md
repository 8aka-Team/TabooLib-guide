> 使用循环语句的时候请务必小心，千万别陷入死循环了~
>



<h1 id="Qt0Ix">While 循环</h1>
<details class="lake-collapse"><summary id="u64808cab"><span class="ne-text">「展开 / 收起详情」</span><span class="ne-text">💠</span><span class="ne-text"> While 语句</span></summary><div id="gOVCT" class="ne-yuque">此处为语雀内容卡片，点击链接查看：<a href="https://www.yuque.com/sacredcraft/kether/reference#oBP3u" target="_blank">https://www.yuque.com/sacredcraft/kether/reference#oBP3u</a></div></details>


`while` 循环主要用在不确定循环次数的情景之下。

它在每一次循环前都会判断你给定的条件语句是否满足，若满足条件，则执行条件体，若不满足，则退出循环。

它的实际应用场景感觉有点少啊，各位可以自行去摸索一下。



<h1 id="idpZE">ForEach 循环</h1>
<details class="lake-collapse"><summary id="u67e2881a"><span class="ne-text">「展开 / 收起详情」</span><span class="ne-text">💠</span><span class="ne-text"> ForEach 语句</span></summary><div id="yhYxJ" class="ne-yuque">此处为语雀内容卡片，点击链接查看：<a href="https://www.yuque.com/sacredcraft/kether/reference#AP7ct" target="_blank">https://www.yuque.com/sacredcraft/kether/reference#AP7ct</a></div></details>


`foreach` 循环主要用于遍历集合，例如遍历数组，或者遍历所有在线玩家，又或者根据给定范围遍历

我们来仔细看看这个语句的参数 `for <font style="color:#07787E;">{token}</font> in <font style="color:#C75C00;">{action}</font> then <font style="color:#4C16B1;">{action}</font>`

第二个参数 `<font style="color:#C75C00;">{action}</font>` 需要传入被遍历集合

第一个参数 `<font style="color:#07787E;">{token}</font>` 是指代每一次循环中，遍历到的当前内容的变量名。

这意味着你可以在循环体中通过 `&{token}` 获取当前遍历到的内容

第三个参数 `<font style="color:#4C16B1;">{action}</font>` 自然就是循环体了，集合有多少个元素，循环体就会执行多少次。



```ruby
/* 遍历数组 */
set array to array [ 1 1 4 5 1 4 ]
for it in &array then {
    tell &it
}

/* 遍历在线玩家的名字 */
for playerName in players then {
  tell &playerName
}

/* 给定范围遍历 */
for it in range 1 to 10 then {
    tell &it
}
```



<h1 id="bSBPf">Break 跳出循环</h1>
如果你在循环的过程中，想要跳出（中断）循环，那么可以使用 `break` 语句。`While` 和 `ForEach` 都适用。

```ruby
/* 当遍历到 5 时跳出循环 */
for it in array [ 1 1 4 5 1 4 ] then {
    if check &it == 5 then break
    tell &it
}
```

运行结果：`1 1 4`



当然了，`break` 除了可以用在循环里，还可以用在 `join` 和 `map` 语句里。

