---
title: Conditions in TypoScript
description: List of examples for conditionals in TypoScript
tags: [conditions, loginUser, globalString, PIDinRootline, globalVar, TSFE, treeLevel, AND, OR, ELSE, slide]
date: 2016-10-28
author: Rafał Brzeski
---

~~~ js
// Available operators "||", "&&", "OR", "AND"
 
[page|uid = 123]
  //...
[end]
 
[globalVar = TSFE:id = 6|7] || [PIDinRootline = 14,20,43,274]
  //...
[end]
 
// Hide object after login (any FE user)
[loginUser = *]
  lib.signIn >
[ELSE]
  lib.signIn = TEXT
  lib.signIn {
    value = Sign in
    typolink.parameter = 14
    typolink.ATagParams = class="btn"
  }
[global]
 
// HTTPS
[globalString = _SERVER|HTTPS = 1]
  //...
[end]
 
[PIDinRootline = 8,21]
  //...
[end]
 
[PIDupinRootline=1]
  //...
[end]
 
// If value from Constants for $constant_to_turnSomethingOn is equal 1
[globalVar = LIT:1 = {$constant_to_turnSomethingOn}]
  //...
[end]

// If value from Constants for $firstMenu is equal 9 and Page is equal 1
[globalVar = LIT:9 = {$firstMenu}] AND [globalVar = TSFE:id = 1]
  //...
[end]
 
[globalVar = LIT:0<{$show_element}]
  //...
[global]
 
// not empty string
[globalString = LIT:{$settings.googleAnaliticsUA} = /.+/]
  //...
[end]
 
[treeLevel = 2,3,4,5] 
  //...
[end]
 
[userFunc = isCurrentUser(merchant)]
  //...
[end]
 
[globalVar = GP:print = 1]
  //...
[END]
 
// if FE user from selected group log in
[usergroup = 2] || [usergroup = 3]
  //...
[END]
 
// if IP addres is 
[globalString = IENV:REMOTE_ADDR = 82.177.87.*]
  //... 
[global]
~~~
