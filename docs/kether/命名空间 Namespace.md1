> 这一章的内容可能会有一点点难，但如果你理解了，会非常有意思
>



<h1 id="Ywif2">语句所属的命名空间</h1>
语句所属的命名空间本质上是一段 **字符串文本**，它是用来确定这个语句是所属于哪个命名空间之下的。



插件开发者在注册每一个语句的时候，都需要指定这个语句所属的命名空间。

当然如果开发者不指定的话就默认为 `kether` 命名空间，也就是说该语句所属于 `kether` 命名空间之下。

因此不管怎样，每一个语句都是所属于一个特定的命名空间之下的。



你在官方文档中看到的“<font style="color:rgb(216, 72, 72);">由 TabooLib 提供的公有动作</font>”，这一系列语句的命名空间就是 `kether`，也就是说由 TabooLib 提供的语句都是所属于 `kether` 命名空间之下的。

而由第三方插件提供的语句的命名空间是什么，这个只有插件开发者知道。不过一般可能会是插件名的小写。



<h1 id="pKDB0">解析时的命名空间</h1>
解析时的命名空间本质上是一个 **字符串数组**<font style="color:#8A8F8D;">（It's actually java.util.List）</font>



kether 在真正运行之前，需要先把你写的 kether 文本解析成一条条语句。在解析过程中，系统需要不断去查询对应的语句。刚才我们提到，每一个语句都是所属于某一个命名空间之下的。那么查询语句的时候也是需要根据命名空间去查询的。

那这个用来查询的命名空间由谁提供啊？当然是插件开发者了。



开发者会提前指定一个字符串数组，里面包含了本次解析过程中可能会用到的所有命名空间。系统在查询语句的时候会根据这个命名空间数组挨个去查询语句。



如果开发者偷懒没有指定命名空间数组的话，那默认就是 `[ kether ]`，仅包含 `kether` 命名空间的数组。这种情况下，你就只能使用 `kether` 命名空间下的语句了。



如果开发者指定了很多命名空间，比如 `[ kether, adyeshach, chemdah ]`，那么你不仅可以使用 `kether` 命名空间里的语句，还可以使用其他命名空间 `adyeshach` 和 `chemdah` 中的语句。



<h1 id="W4T7A">私有语句 & 公有语句</h1>
> 对于一个语句的公有或私有，我们一般只考虑第三方插件提供的语句，讨论原生语句和由 TabooLib 提供的公有语句并无意义。
>



私有语句，也就是私有动作，它只能在该第三方插件提供的特定运行环境内使用。在其他插件提供的运行环境内则没有任何可能使用的余地。

例如你想在 Chemdah 插件中使用 TrMenu 插件提供的**私有**语句，这是不可能滴~



而对于公有语句，只要“**解析时的命名空间**”中包含该语句所属的命名空间，那么你就可以正常使用。否则语句解析过程中可能会出现报错。 



<h1 id="iYuCp">同名语句冲突</h1>
随着 kether 的不断发展，越来越多的第三方插件陆陆续续地推出自己的公有语句。不同插件之间难免也会出现语句同名的情况。



例如 Chemdah 与 TrMenu 都各自有一个同名的动作 [Variable](https://kether.tabooproject.org/list.html#Variable)，不过好在这两个语句都是私有语句，都只能在自己的插件中使用，互相之间不会产生影响。



如果我们假设，这两个语句是公有语句呢？并且它们所属的命名空间分别为 `chemdah` 和 `trmenu`

那么问题来了，系统遇到这个语句的时候应该解析成哪一个呢？

这就要分情况讨论了：



如果“解析时的命名空间”为 `[ kether, chemdah ]`，即不包含 `trmenu` 命名空间。那么系统会把这个语句解析为 Chemdah 中的语句。反过来也是同理。



如果“解析时的命名空间”为 `[ kether, chemdah, trmenu ]`，既包含 `chemdah` 也好包含 `trmenu` 命名空间，那么大概率会按这个数组给的命名空间顺序。先去 `kether` 命名空间里找找看，噢，找不到。很好，那就接着下一个，到 `chemdah` 命名空间里看看有没有该语句，诶找到了，那就是你啦！



显然这种并不是我们想要的结果，不过幸运的是，我们知道这两个语句所属的命名空间。那么我们在使用的时候可以这样去写：

```ruby
/* 指明使用 Chemdah 中的 Variable */
tell chemdah:var key
print chemdah:var keys

/* 指明使用 TrMenu 中的 Variable */
tell trmenu:var "{}"
print trmenu:var "{meta: example}"
```

是的没错，所有语句你都可以用这种格式去写 `命名空间:语句`

例如由 TabooLib 提供的语句：`kether:tell`、`kether:actionbar`

当然同名这种情况目前来说比较罕见，没什么必要的话尽量简写吧，大伙知道有这种写法就好。



<h1 id="zVbkg">动态修改解析时的命名空间</h1>
有时候我们可能会对开发者指定的“解析时的命名空间”不满意，能不能动态修改呢？当然可以！



<details class="lake-collapse"><summary id="u2de2cedc"><span class="ne-text">「展开 / 收起详情」</span><span class="ne-text">💠</span><span class="ne-text"> Import 语句</span></summary><h1 id="gRwu7"><span class="ne-text" style="color: rgb(216, 72, 72)">Import</span></h1><p id="u670d2eab" class="ne-p"><span class="ne-text" style="color: rgb(133, 135, 150); font-size: 14px">导入命名空间</span></p><hr id="K5GJ0" class="ne-hr"><p id="u8fff60ad" class="ne-p"><code class="ne-code"><span class="ne-text" style="color: var(--bs-gray-400); font-size: 14px">import {token}</span></code></p><hr id="KNyrb" class="ne-hr"><p id="u86b10133" class="ne-p"><span class="ne-text" style="color: rgb(216, 72, 72); font-size: 14px">由 TabooLib 提供的公有动作</span></p></details>
增加新的命名空间可以使用 `import` 语句



<details class="lake-collapse"><summary id="uadd9d2a6"><span class="ne-text">「展开 / 收起详情」</span><span class="ne-text">💠</span><span class="ne-text"> Release 语句</span></summary><h1 id="AUywR"><span class="ne-text" style="color: rgb(216, 72, 72)">Release</span></h1><p id="u22820cfd" class="ne-p"><span class="ne-text" style="color: rgb(133, 135, 150); font-size: 14px">释放命名空间</span></p><hr id="sRRQ0" class="ne-hr"><p id="ue4fcfe16" class="ne-p"><code class="ne-code"><span class="ne-text" style="color: var(--bs-gray-400); font-size: 14px">release {token}</span></code></p><hr id="aozQf" class="ne-hr"><p id="u361a9f68" class="ne-p"><span class="ne-text" style="color: rgb(216, 72, 72); font-size: 14px">由 TabooLib 提供的公有动作</span></p></details>
删除命名空间可以使用 `release` 语句



这两个动作目前只能通过查看源码得知，并不能在官方文档里找到相关信息  
最后还是在这里提个醒，如果没什么必要还请不要随便改动“解析时的命名空间”







