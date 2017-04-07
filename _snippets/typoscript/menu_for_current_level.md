---
title: Menu only for current level
description: Simple solution with field:pid
tags: [menu, directory, pid]
date: 2016-08-31
author: Rafał Brzeski
---

~~~ js
lib.tabs-nav = HMENU
lib.tabs-nav {
    special = directory
    special.value.dataWrap = {field:pid}
 
    1 = TMENU
    1 {
        wrap = <ul class="mate-tabs__nav">|</ul>
 
        NO = 1
        NO.wrapItemAndSub = <li>|</li>
 
        CUR = 1
        CUR {
            wrapItemAndSub = <li class="active">|</li>
        }
 
        ACT < .CUR
}
~~~
