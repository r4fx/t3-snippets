---
title: How to use 'picture' tag in Fluid
description: HTML5 Picture tag in Fluid templates, example based on extension News
tags: [fluid, picture, image]
date: 2017-06-05
author: Rafał Brzeski
---

~~~ xml
<picture>
    <source media="(max-width: 479px)" srcset="{f:uri.image(src:'{mediaElement.originalResource.publicUrl}', width:'345', height:'204c')}, {f:uri.image(src:'{mediaElement.originalResource.publicUrl}', width:'690', height:'404c')} 2x">
    <source media="(min-width: 480px)" srcset="{f:uri.image(src:'{mediaElement.originalResource.publicUrl}', width:'{settings.list.media.image.width}', height:'{settings.list.media.image.height}')}">

    <f:image image="{mediaElement}"
        title="{mediaElement.title}"
        alt="{mediaElement.title}"
        width="{settings.list.media.image.width}"
        height="{settings.list.media.image.height}"/>
    </picture>
~~~
