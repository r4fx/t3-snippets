---
title: Inline conditions in Fluid
description: Set of examples
tags: [fluid, inline conditions, condition]
date: 2015-12-21
author: Rafał Brzeski
---

~~~ xml
<div class="slider" data-slider-maxSlides="{f:if(condition: '{field.items}', then: '{field.items}', else: '3')}">
 foo
</div>
~~~
 
#### String compare
~~~ xml
<div class="row {f:if(condition:'{field.marker} == \'simple-tooltip\'', then: 'form-tooltip')}">
  foo
</div>
~~~
