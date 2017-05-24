---
title: Fluid typoscript object, inline
description: notacja inline typoscriptObjectPath
tags: [fluid, typoscriptObjectPath]
date: 2016-01-22
author: Rafał Brzeski
---

~~~ xml
<img class="logotype replace-svg" src="{f:cObject(typoscriptObjectPath: 'lib.logo.10')}" width="160" height="18" />
 
// Wersja z przekazaniem danych poprzez parametr "data"
 
<a href="#" data-map-zoom="{f:cObject(typoscriptObjectPath: 'lib.iframeSrcRowerowy', data: '{newsItem.author -> f:format.stripTags()}' )}">{newsItem.title}</a>
~~~
