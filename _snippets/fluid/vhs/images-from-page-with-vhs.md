---
title: Obrazki z pola Media w szablonie fluid, viewhelper
description: Pobieranie obrazków z pola Media podstrony bezpośrednio poprzez Fluid i VHS
tags: [media, vhs, fluid, image]
date: 2016-04-11
author: Rafał Brzeski
---

~~~ xml
// Przykłady użycia https://github.com/FluidTYPO3/vhs/pull/395
 
<v:resource.record.fal table="pages" field="media" uid="{data.uid}" as="resources">
    <f:for each="{resources}" as="resource">
        <v:resource.image identifier="{resource.id}" class="object-fit" width="1280c" height="370c"/>
    </f:for>
</v:resource.record.fal>
~~~
