---
title: Zmiana _ na normalna spację
description: Wykorzystanie funkcji TS replace w szablonie fluid
tags: [replace, search, useRegExp, fluid, current]
date: 2016-01-21
author: Rafał Brzeski
---

### TypoScript

~~~ js
// Replace _ to real space

lib.replaceLineSpace = TEXT
lib.replaceLineSpace {
    current = 1
    htmlSpecialChars = 1
    required = 1
 
    replacement {
        // equivalent to former useSpacesInLinkText = 0; remove using > to disable it
        10 {
            search = _
            replace.char = 32
        }
 
        // equivalent to former stripFileExtensionFromLinkText = 0; move "_20" to "20" to enable it. Disabled by default.
        20 {
            search = /(.*)(\..*)/
            replace = \1
            useRegExp = 1
        }
    }
 
    #wrap = <span class="real-name">|</span>
}
~~~

### Fluid

~~~ xml
<f:cObject typoscriptObjectPath="lib.replaceLineSpace">{folder.name}</f:cObject>
~~~
