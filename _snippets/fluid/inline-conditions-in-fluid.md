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

#### Time compare (for variables use VHS extension)
~~~ xml
{namespace v=FluidTYPO3\Vhs\ViewHelpers}

<v:variable.set name="currentDate" value="{f:format.date(date: 'now' format: 'Y-m-d H:i:s')}" />
<v:variable.set name="finishDate" value="{f:format.date(date: '{data.tx_mask_year}-{data.tx_mask_month}-{data.tx_mask_day} {data.tx_mask_hour}' format: 'Y-m-d H:i')}" />

<f:comment>
    <!-- use for debug date -->
    current date: {currentDate}<br>
    finish date: {finishDate}<br>
</f:comment>

<f:if condition="{currentDate} > {finishDate}">
    <f:then>
        foo
    </f:then>
    <f:else>
        bar ({f:format.date(date: '{finishDate}' format: 'Y-m-d')}, {f:format.date(date: '{finishDate}' format: 'H:i')})
    </f:else>
</f:if>
~~~
