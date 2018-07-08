---
title: Set title tag in meta section directly in Fluid file
description: This very simple method allows you to set a 'title' tag in fluid without hassle
tags: [HeaderAssets, fluid, meta, title, vhs]
date: 2018-07-08
author: Rafał Brzeski
---

## Example 1

~~~ xml
<f:section name="HeaderAssets">
  <title>Super title from fluid</title>
</f:section>
~~~

## Example 2

Global HeaderAssets.html
~~~ xml
<html xmlns:f="http://typo3.org/ns/TYPO3/CMS/Fluid/ViewHelpers" data-namespace-typo3-fluid="true">
<v:variable.set name="pageUid" value="{v:page.info(field: 'uid')}" />

<f:if condition="{pageUid} != 30">
    <title>
        {v:page.info(field: 'title')}
        <f:if condition="{settings.titleEndSegment}">
            — {settings.titleEndSegment}
        </f:if>
    </title>
</f:if>
~~~

Page id 30 with detail view of some plugin
~~~ xml
<f:section name="HeaderAssets">
  <title>{arguments.job.value.jobTitle}</title>
</f:section>
~~~
