---
title: Zmiana _ na normalna spację
description: Wykorzystanie funkcji TS replace w szablonie fluid
tags: [replace, search, useRegExp, fluid, current]
date: 2016-01-21
author: Rafał Brzeski
---

### TypoScript

~~~ js
lib.replaceLineSpace = TEXT
lib.replaceLineSpace {
    current = 1
    htmlSpecialChars = 1
    required = 1
 
    replacement {
        // Use spaces in link text (Replace _ to real space)
        10 {
            search = _
            replace.char = 32
        }
 
        // strip file extension from link text, move "_20" to "20" to enable it.
        _20 {
            search = /(.*)(\..*)/
            replace = \1
            useRegExp = 1
        }
    }
}
~~~

### Fluid

~~~ xml
<f:cObject typoscriptObjectPath="lib.replaceLineSpace">{folder.name}</f:cObject>
~~~
