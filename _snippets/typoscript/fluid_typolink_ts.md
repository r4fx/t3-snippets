---
title: Fluid typolink by TypoScript
description: dla wersji TYPO3 (<7.6) nie obsługujacej VH typolink
tags: [typolink, fluid, split, char, token, typoscript]
date: 2016-05-27
author: Rafał Brzeski
---

### Typoscript

~~~ js
lib.fluid-typolink = TEXT
lib.fluid-typolink {
    current = 1
    split {
        token.char = 32
        cObjNum = 1 || 2
 
        // href
        1 {
            typolink {
                parameter.current = 1
                returnLast = url
            }
            wrap = href="|"
        }
 
        // Target
        2 {
            current = 1
            wrap = target="|"
        }
    }
}
~~~

### Fluid

~~~ xml
<a {f:cObject(typoscriptObjectPath: 'lib.fluid-typolink', data: '{banner.link}' )}>
   Link
</a>
~~~
