---
title: Obrazki z pola Media w szablonie fluid, viewhelper
description: Pobieranie obrazków z pola Media podstrony z opcją dziedziczenia, bezpośrednio poprzez Fluid i VHS
tags: [media, vhs, fluid, image]
date: 2016-04-11
author: Rafał Brzeski
---

~~~ xml 
<v:page.resources.fal uid="{data.uid}" as="resources" slide="-1">
 <f:for each="{resources}" as="resource">
  <v:resource.image identifier="{resource.id}" width="880c" height="175c" alt="{data.title}"/>
 </f:for>
</v:page.resources.fal>

lub

<v:resource.image identifier="{v:page.resources.fal(uid: '9') -> v:iterator.extract(key: 'id')}" />
~~~
