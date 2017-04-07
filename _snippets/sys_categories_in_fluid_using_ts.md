---
title: Pobieranie kategorii systemowych przez TS i Fluid
description: z użyciem ts object i parametrami do zapytania przekazanym w polu data
tags: [fluid, data, select, where, register, sys_category]
date: 2016-11-16
author: Rafał Brzeski
---

~~~ js
//===================================================
// LIST CATEGORIES
//
// FLUID: <f:cObject typoscriptObjectPath="lib.category" data="{cat:'28', pid:'110'}"/>
//===================================================
 
lib.category = COA
lib.category {
    // Debug
    #1 = TEXT
    #1 {
        #dataWrap = [{register:cat}, {register:pid}]<br>
    #}
 
    5 = LOAD_REGISTER
    5 {
        cat = TEXT
        cat.field = cat
 
        pid = TEXT
        pid.field = pid
    }
 
    10 = CONTENT
    10 {
        table = sys_category
        select {
            selectFields = title, uid
            where.data = register:cat
            where.intval = 1
            where.wrap = sys_category.parent=|
            pidInList.data = register:pid
        }
 
        renderObj = TEXT
        renderObj {
            dataWrap = <option value="contactCategory-{field:uid}">{field:title}</option>
        }
    }
}
~~~
