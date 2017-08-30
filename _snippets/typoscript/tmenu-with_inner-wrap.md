---
title: TMENU with inner wrap
description: Example of how to insert tag with icon inside A tag
tags: [inner, menu, allwrap, stdWrap, hmenu]
date: 2012-11-30
author: Rafał Brzeski
---

~~~ js
temp.menu = HMENU
temp.menu {
    special = list
    special.value = 12,13,14
 
    1 = TMENU
    1 {
      wrap = <ul>|</ul>
      NO {
        allWrap = <li>|</li>
        stdWrap.wrap = |<span class="icon-facebook"></span>
      }
    }
  }
~~~
