<details class="lake-collapse"><summary id="ued52182e"><span class="ne-text">「展开 / 收起详情」</span><span class="ne-text">💠</span><span class="ne-text"> Inline 语句</span></summary><div id="JNv2r" class="ne-yuque">此处为语雀内容卡片，点击链接查看：<a href="https://www.yuque.com/sacredcraft/kether/reference#jdvIW" target="_blank">https://www.yuque.com/sacredcraft/kether/reference#jdvIW</a></div></details>


先来介绍一下，这个语句可以让我们在文本中插入语句，插入语句的返回值会直接插入该位置变成文本的一部分。

为了能让系统从文本中识别我们插入的语句，我们需要将语句写到 `{{...}}` 里。



```ruby
/* 插入玩家名 */
tell inline "恭喜你 {{ player name }} 中奖啦！！奖池为VIVO50"


/* 插入变量 */
/* 制作血量显示 Action Bar */
set health to player health
set max-health to player max health
actionbar color inline "HP：&a&l{{ &health }} &f/ &c&l{{ &max-health }}"
```



<details class="lake-collapse"><summary id="u1546a66a"><span class="ne-text">「展开 / 收起详情」</span><span class="ne-text">🥝</span><span class="ne-text"> 演示效果</span></summary><p id="u24df891f" class="ne-p"><br></p><p id="u3675328f" class="ne-p"><img src="https://cdn.nlark.com/yuque/0/2023/png/26025412/1675054665665-dd18daf4-abce-41ba-9fe1-ab0da373314f.png" width="854" id="u7e4dc34b" class="ne-image"></p><p id="u360d1808" class="ne-p"><br></p><p id="u8164d79c" class="ne-p"><img src="https://cdn.nlark.com/yuque/0/2023/png/26025412/1675052716766-cf6f95ee-b5e8-44ce-ad13-d5acf9132ef2.png" width="854" id="ud55d205f" class="ne-image"></p><p id="u639fb853" class="ne-p"><br></p></details>


每一个内联脚本 `{{...}}` 在运行时都相当于去执行了一份新的 Kether 脚本，并在内联脚本执行后立刻获取结果替换文本中的内联脚本。

这意味着如果你在内联里使用 `Delay` 语句，那么将导致获取的结果为 `null`，我想应该没有人会这样写吧，不过还是想提醒一下各位。





此外，如果你只是想在一段文本里插入玩家的名字，很多时候都是可以不用 `inline` 的。

例如 `Tell`、`Broadcast`、`Action Bar`、`Command` 等语句都是支持将文本中的 `@sender` 字段替换成玩家的名字。（ 注意大小写 ）

```ruby
tell "欢迎光临 @sender"
command "kill @sender"
```





当然，除了 `inline`，你也可以用 `join` 来达到同样的效果，只不过看上去没有 `inline` 那么直观而已。

<details class="lake-collapse"><summary id="u57e7667d"><span class="ne-text">「展开 / 收起详情」</span><span class="ne-text">💠</span><span class="ne-text"> Join 语句</span></summary><div id="VhDpp" class="ne-yuque">此处为语雀内容卡片，点击链接查看：<a href="https://www.yuque.com/sacredcraft/kether/reference#Th01h" target="_blank">https://www.yuque.com/sacredcraft/kether/reference#Th01h</a></div></details>
`Join` 的作用是将多个语句的返回值拼凑成一段文本。

如果你的内联脚本正好处于文本的开头或末尾，那么用 `Join` 语句来代替 `Inline` 将会是个不错的主意。

```ruby
/* 对比：单个内联脚本 */
tell color inline "&7当前血量: {{ player health }}"
tell color join [ "&7当前血量" player health ]


/* 对比：多个内联脚本 */
set health to player health
set max-health to player max health
actionbar color inline "HP：&a&l{{ &health }} &f/ &c&l{{ &max-health }}"
actionbar color join [ "HP：&a&l" &health " &f/ &c&l" &max-health ]
```







