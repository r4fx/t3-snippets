---
title: Modifications operator ":="
description: A way to manage the values entered in TypoScript
tags: [addToList, removeFromList, prependString, appendString, removeString, replaceString, uniqueList, reverseList, sortList]
date: 2013-09-17
author: Rafał Brzeski
---

~~~ js
// doc. https://docs.typo3.org/typo3cms/TyposcriptSyntaxReference/Syntax/TypoScriptSyntax/Index.html#value-modifications-the-operator
 
// Available options:
 
// prependString: Adds a string to the beginning of the existing value.
// appendString: Adds a string to the end of the existing value.
// removeString: Removes a string from the existing value.
// replaceString: Replaces old with new value. Separate these using "|".
// addToList: Adds a comma-separated list of values to the end of a string value. There is no check for duplicate values, and the list is not sorted in any way.
// removeFromList: Removes a comma-separated list of values from an existing comma-separated list of values.
// uniqueList: Removes duplicate entries from a comma-separated list of values.
// reverseList: Reverses the order of entries in a comma-separated list of values.
// sortList: Sorts the entries in a comma-separated list of values.
 
myObject = TEXT
myObject.value = 1,2,3
myObject.value := addToList(4,5)
myObject.value := removeFromList(2,1)
 
// Result:
myObject = TEXT
myObject.value = 3,4,5
~~~
