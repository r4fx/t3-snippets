---
title: PIDinRootline in Fluid
description: PIDinRootline condition in Fluid using VHS
tags: [fluid, vhs, PIDinRootline, condition, asset]
date: 2016-08-30
author: Rafał Brzeski
---


~~~ xml
<!-- Conditional styles asset for PID in rootline of 21 -->
<v:condition.iterator.contains needle="21" haystack="{v:page.rootline() -> v:iterator.extract(key: 'uid')}">
    <v:asset.style path="/{settings.path.css}/expo.css" standalone="1" external="1"/>
</v:condition.iterator.contains>
~~~
