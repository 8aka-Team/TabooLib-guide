---
title: 菜单传参
sidebar_position: 2
---

import { PageRef } from '@site/src/components/GitBook';

# 菜单传参

TrMenu 的菜单支持将触发命令后缀的参数作为变量使用

## 功能启用

若不进行任何配置，菜单传参功能默认是**开启**的，

若遇到命令不兼容情况，可以通过选项关闭

<PageRef to="../menu/configuration/option.md" />

## 传递方式

* 绑定的自定义开启命令传递
* 插件开启菜单命令传递
* 调用动作二次修改

## 如何使用

例如玩家当前的参数为 apple, juice, orange，即大小为 3 的一个数组

在菜单几乎所有地方都可以当作变量使用，`{0}` 将返回 apple, `{1}` 返回 juice, 依此类推

## 注意

* 默认情况下，关闭菜单不会删除现有参数

