---
title: Manually rendering language menu using VHS LanguageMenuViewHelper
description: v:page.languageMenu with f:for
tags: [vhs, menu, page, languageMenu]
date: 2018-03-26
author: Rafał Brzeski
---

[v:page.languageMenu ViewHelper documentation](https://fluidtypo3.org/viewhelpers/vhs/master/Page/LanguageMenuViewHelper.html)

~~~ xml
<v:page.languageMenu
  class="list-inline"
  defaultLanguageLabel="EN"
  defaultIsoFlag="en"
  as="menu">

  <f:comment>
    * ========================================
    * Check all properties by debugging object
    * ========================================

    <f:debug title="menu">{menu}</f:debug>
  </f:comment>

  <ul class="list-inline">
    <f:for each="{menu}" as="langMenu">
      <li class="list-inline-item
          {f:if(condition: '{langMenu.inactive}', then: 'lang-inactive')}
          {f:if(condition: '{langMenu.current}', then: 'lang-current')}"
      >
        <f:link.page
          pageUid="{langMenu.url}"
          class="flag-nav--{langMenu.flag}">
          <span title="{langMenu.label}"></span>
        </f:link.page>
      </li>
    </f:for>
  </ul>
</v:page.languageMenu>
~~~
