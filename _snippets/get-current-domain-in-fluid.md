---
title: Get current domain in Fluid
description: Return current domain in Fluid template (with optional page uid) with help of TypoScript
tags: [getIndpEnv, typolink, typoscriptObjectPath, domain, url]
date: 2017-05-24
author: Rafał Brzeski
---

### TypoScript

~~~ js
lib.currentDomain = TEXT
lib.currentDomain {
    dataWrap = {getIndpEnv:TYPO3_REQUEST_HOST}|
    typolink.parameter.current = 1
    typolink.returnLast = url
}
~~~
 
### Fluid

~~~ xml
 {f:cObject(typoscriptObjectPath: 'lib.currentDomain', data: '167')}
~~~
