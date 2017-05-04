---
title: Zmiana szablonu fluid poprzez zmienna GP
description: Przydaje sie dla modala
tags: [fluid, GP, layout, file]
date: 2016-04-15
author: Rafał Brzeski
---
 
~~~ js
// Przykładowy url http://exampleurl.com/subpage/?modal=1

[globalVar = GP:modal = 1]
    page.10.file >
    page.10.file = {$path.html}/templates/blank-page.html
    page.bodyTagAdd = class="modal-mode"
[global]
~~~
