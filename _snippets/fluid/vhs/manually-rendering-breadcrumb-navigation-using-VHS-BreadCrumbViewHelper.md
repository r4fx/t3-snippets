---
title: Manually rendering breadcrumb navigation using VHS BreadCrumbViewHelper
description: v:page.breadCrumb with f:for for nav elements
tags: [vhs, menu, page, breadCrumb]
date: 2018-03-26
author: Rafał Brzeski
---

[v:page.breadCrumb ViewHelper documentation](https://fluidtypo3.org/viewhelpers/vhs/master/Page/BreadCrumbViewHelper.html)

~~~ xml
<v:page.breadCrumb
  as="menu"
  classActive=""
  classCurrent="active"
>
    <f:comment>
        * ========================================
        * Check all properties by debugging object
        * ========================================

        <f:debug title="menu">{menu}</f:debug>
    </f:comment>

    <ul class="breadcrumb">
        <f:for each="{menu}" as="menuItem">
            <li class="list-inline-item {menuItem.class}">
                <f:link.page
                  pageUid="{menuItem.uid}">
                    {menuItem.title}
                </f:link.page>
            </li>
        </f:for>
    </ul>
</v:page.breadCrumb>
~~~
