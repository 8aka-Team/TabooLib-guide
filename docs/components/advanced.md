---
sidebar_position: 3
---

# 高级玩法

本文介绍一些 TabooLib Components 更高端的玩法。

## 渐变文本

提供两个或多个颜色，根据所提供的颜色和颜色顺序自动生成渐变颜色。

示例：

```markdown
[||||||||||||||||||||](gradient=#f6d365,#fda085)
```

:::tip
您也可以使用 `g` 代替 `gradient` ，这是一个简写。
:::

效果如下：

![渐变文本效果图](../../static/img/components/Xnip2023-07-25_15-04-02.png)

## 自定义字体

可以选择其他字体显示，甚至是资源包里自定义的字体。

示例：
```markdown
[TabooLib](font=uniform) yyds!
```

效果如下：

![自定义字体效果图](../../static/img/components/Xnip2023-07-25_15-27-35.png)

## 插入文本

按住 Shift 键点击文本，即可向聊天框内补充内容。

示例：
```markdown
点击 [&9&l这个](insertion=没什么跟您说的我要玩原神了) 看看我想对您说的话
```

:::tip
您也可以使用 `insert` 代替 `insertion` ，这是一个简写。
:::

效果如下：

![插入文本效果图](../../static/img/components/Xnip2023-07-25_20-44-32.png)

## 键位

显示玩家设置的该功能（例如跳跃）的键位。

示例：
```
点击 [key.jump](keybind) 来跳跃
```

效果如下：

![键位效果图](../../static/img/components/Xnip2023-07-25_20-50-30.png)

:::tip
第一行是当空格为跳跃键时显示的文本，第二行是设置回车键为跳跃键后显示的文本。
:::

## 换行

换行，不用我多说吧。

示例：

```markdown
今天读的是书，[](newline)明天数的是钱。
```

:::tip
您也可以使用 `[](br)` 来换行，这是一个简写。
:::

效果如下：

![换行效果图](../../static/img/components/Xnip2023-07-25_20-54-29.png)

## 翻译键

获取玩家客户端语言文本。

示例：
```markdown
[block.minecraft.diamond_block](translate)
```

:::tip
您也可以使用 `trans` 代替 `translate` ，这是一个简写。
:::

效果如下：

![翻译键效果图](../../static/img/components/Xnip2023-07-25_21-43-40.png)

:::tip
从上至下依次为：汉语、马来语、日语、英语。
:::

## 选择器

目标选择器。

示例：

**不会**，谁有能力谁去搞。

![原神效果图](../../static/img/components/GenshinImpact.png)