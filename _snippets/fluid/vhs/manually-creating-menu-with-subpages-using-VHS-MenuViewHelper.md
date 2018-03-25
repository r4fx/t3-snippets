---
title: Page teaser on Fluid and VHS
description: Manually creating menu with subpages using VHS MenuViewHelper.
tags: [vhs, menu, hasSubpages]
date: 2018-03-26
author: Rafał Brzeski
---

~~~ xml
<v:menu.list
  pages="{settings.nav.mainNav}"
  class="navbar-nav ml-auto"
  classActive=""
  classCurrent="active"
  classHasSubpages="has-sub-menu"
  as="menu"
>
  <f:comment>
    Check all properties by debugging object
    ========================================
    <f:debug title="menu">{menu}</f:debug>
  </f:comment>

  <ul class="navbar-nav ml-auto">
    <f:for each="{menu}" as="menuPage">
      <li class="nav-item {menuPage.class}">
          <f:link.page
            pageUid="{menuPage.uid}"
            title="{menuPage.linktext}"
            class="nav-link"
          >
            {menuPage.linktext}
          </f:link.page>

          <f:if condition="{menuPage.hasSubPages}">
            <ul class="list-unstyled">
              <v:menu
                pageUid="{menuPage.uid}"
                classActive=""
                classCurrent="active"
                as="submenu">
                <f:for each="{submenu}" as="subMenuPage">
                  <li class="{subMenuPage.class}">
                    <f:link.page
                      pageUid="{subMenuPage.uid}"
                      title="{subMenuPage.linktext}"
                      class="nav-link">
                      {subMenuPage.title}
                    </f:link.page>
                  </li>
                </f:for>
              </v:menu>
            </ul>
          </f:if>
        </li>
    </f:for>
  </ul>
</v:menu.list>
~~~
