---
title: Wyjęcie obrazka z zakładki resources
description: Z zachowaniem obrazka z poziomu wyżej i obrazkiem domyślnym jeśli nie dodano żadnego.
tags: [media, image, resources, files, crop]
date: 2016-04-11
author: Rafał Brzeski
---

~~~ js
//===================================================
// Get image from Page resources tab
//===================================================

lib.resourceImage = FILES
lib.resourceImage {
 
    // Default image if empty
    stdWrap.ifEmpty.cObject = IMAGE
    stdWrap.ifEmpty.cObject {
        file = /files/assets/images/bkg-1.jpg
        file {
            width = 1280c
            height = 370c
        }
        altText.data = page:title
        params = class="object-fit"
    }
 
    // Set image with slide from parent page
    references {
        data = levelmedia:-1, slide
    }
    maxItems = 1
 
    renderObj = IMAGE
    renderObj {
        file {
            import.data = file:current:publicUrl
	    crop.data = file:current:crop
            width = 1280c
            height = 370c
        }
        altText.data = file:current:title // page:title
        params = class="object-fit"
    }
}
~~~
