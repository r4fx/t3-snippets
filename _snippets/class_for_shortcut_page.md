---
title: CSS class for active page with type of Shortcut
description: Override class if the shortcut is pointing to the current page
tags: [shortcut, menu, override, if]
date: 2016-09-21
author: Piotr Łojewski
---

~~~ js
1 = TMENU
1 {
    NO {
        allWrap = <li>|</li>
        // Override class if the shortcut is pointing to the current page
        allWrap.override.cObject = COA
        allWrap.override.cObject {
            if {
                value = 4
                equals.field = doktype
                isTrue = 1
                isTrue.if {
                    value.data = TSFE:page|uid
                    equals.field = shortcut
                }
            }
            10 = TEXT
            10.value = <li class="active">|</li>
        }
    }
}
~~~
