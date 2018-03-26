---
title: Rendering menu with one level deep using VHS MenuViewHelper
description: Mixed v:menu rendering with first and next level, ideal for sidebar navigation.
tags: [vhs, menu, sidebar, entryLevel]
date: 2018-03-26
author: Rafał Brzeski
---

[v:menu.list ViewHelper documentation](https://fluidtypo3.org/viewhelpers/vhs/master/MenuViewHelper.html)

~~~ xml
<ul class="list-unstyled">
    <v:menu
      as="menu"
      entryLevel="1"
      expandAll="1"
    >
        <f:for each="{menu}" as="item">
            <li class="{item.class}">
                <f:link.page
                  pageUid="{item.uid}"
                  title="{item.linktext}"
                  class="nav-link {item.class}">
                    {item.title}
                </f:link.page>

                <v:menu
                  pageUid="{item.uid}"
                  entryLevel="2"
                  class="lvl-1 list-unstyled"
                />
            </li>
        </f:for>
    </v:menu>
</ul>
~~~
