---
title: PAPI 变量
sidebar_position: 1
---

import { Admonition } from '@site/src/components/GitBook';

# PAPI 变量

## 菜单总量

> %trmenu\_menus%

## 传递参数

> %trmenu\_args\_````<Index>````%

## Metadata 数据

> %trmenu\_meta\_``<key>``%
>
> %trmenu\_data\_``<key>``%

## Menu 菜单数据

> %trmenu\_menu\_page%  \# 当前正在查看的页码
>
> %trmenu\_menu\_pages%  \# 菜单总页码量
>
> %trmenu\_menu\_next% \# 下一页的页码
>
> %trmenu\_menu\_prev% \# 上一页的页码
>
> %trmenu\_menu\_title% \# 当前访问的菜单标题

## JavaScript 运算

> %trmenu\_js\_``<Context>``%

<Admonition type="danger">
**警告**: 该变量可能会被恶意利用, 请在确保玩家无法主动访问 PlaceholderAPI 变量的情况使用.

若要启用该功能, 请前往 **settings.yml** 将节点 **Options.Placeholders.JavaScript-Parse** 启用
</Admonition>

## Jexl 运算

> %trmenu\_jexl\_``<Context>``%

<Admonition type="danger">
**警告**: 该变量可能会被恶意利用, 请在确保玩家无法主动访问 PlaceholderAPI 变量的情况使用.

若要启用该功能, 请前往 **settings.yml** 将节点 **Options.Placeholders.Jexl-Parse** 启用
</Admonition>

