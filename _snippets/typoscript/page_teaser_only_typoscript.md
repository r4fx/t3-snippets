---
title: Page teaser w TypoScript
description: Sposób na zrobienie page teaser tylko przez TypoScript, bez uzycia wtyczek. Poniższy kod wywolaj we Fluidzie.
tags: [teaser, fal, file]
date: 2016-10-28
author: Rafał Brzeski
---

~~~ js
lib.pageTeaser = HMENU
lib.pageTeaser{
    wrap = <div class="bricks-container">|</div>
    special = directory
 
    1 = TMENU
    1 {
        wrap = <div class="row box--flex">|</div>
        NO {
            allWrap = <div class="bricks-container__item col-6 col-12--phone">|</div>
 
            stdWrap.cObject = COA
            stdWrap.cObject {
                5 = TEXT
                5 {
                    field = subtitle // title
                    wrap = <h3 class="section-header"><span>|</span></h3>
                }
 
                10 = FILES
                10 {
                    stdWrap.wrap = <figure>|</figure>
 
                    // Default image if empty
                    stdWrap.ifEmpty.cObject = IMAGE
                    stdWrap.ifEmpty.cObject {
                        file = /files/assets/images/image-not-access.png
                        file {
                            width = 780c
                            height = 456c
                        }
                        altText.field = subtitle // title
                    }
 
                    // Get reference to Pages
                    references {
                        table = pages
                        uid.data = id
                        fieldName = media
                    }
 
                    maxItems = 1
 
                    renderObj = IMAGE
                    renderObj {
                        file {
                            #import.data = file:current:publicUrl
                            import.data = file:current:uid
                            crop.data = file:current:crop
                            treatIdAsReference = 1
                            width = 780c
                            height = 456c
                        }
                        altText.data = file:current:title // field:subtitle // field:title
                    }
                }
 
                20 = TEXT
                20 {
                    field = abstract
                    wrap = <p>|</p>
                }
            }
        }
    }
}
~~~
