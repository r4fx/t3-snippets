---
title: Split dataProcessor
description: wykorzystanie metody dataProcessing do rozdzielenia danych podanych po przecinku w polu i wykorzystanie tych danych w szablonie fluid
tags: [dataProcessing, split, fluid]
date: 2016-05-19
author: Rafał Brzeski
---

### TypoScript

~~~ js
lib.fluidContent{
  dataProcessing.99 = TYPO3\CMS\Frontend\DataProcessing\SplitProcessor
  dataProcessing.99{
     if.isTrue.field = layout
     delimiter =,
     fieldName = layout     
     as = splitlayout  
  }
}
~~~
 
### Fluid

~~~ xml
 <f:for each="{splitlayout}" as="layout">{layout} </f:for>
~~~
