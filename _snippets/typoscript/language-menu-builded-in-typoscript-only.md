---
title: Language menu builded in TypoScript only
description: You don't need additional extension for it
tags: [menu, language, addQueryString, exclude, doNotLinkIt, USERDEF, override]
date: 2016-01-22
author: Rafał Brzeski
---

lib.langMenu = HMENU
lib.langMenu {
    special = language
    special.value = 0,1,2
    special.normalWhenNoLanguage = 0
    wrap = <ul class="list-inline">|</ul>
    
    1 = TMENU
    1 {
        NO = 1
        NO {
            linkWrap = <li>|</li>
 
            // By default links are mounted from from Site title, override them with this below
            stdWrap.override = PL || EN || DE
 
            // Disable standard links, because they don't accept GET parameters
            doNotLinkIt = 1
 
            // Build link with all needed parameters
            stdWrap.typolink {
                parameter.data = page:uid
                additionalParams = &L=0 || &L=1 || &L=2
                addQueryString = 1
                addQueryString.exclude = L,id,cHash,no_cache
                addQueryString.method = GET
                useCacheHash = 1
                no_cache = 0
            }
        }
 
        ACT < .NO
        ACT {
            linkWrap = <li class="active">|</li>
            stdWrap.typolink >
        }
 
        // No translation, Normal
        USERDEF1 < .NO
        USERDEF1 {
            linkWrap = <li class="no-trans">|</li>
            stdWrap.typolink {
                parameter >
                // Link to home page, or dedicated page for other language
                parameter = 1
            }
        }
 
        // No translation, Active
        USERDEF2 < .ACT
        USERDEF2 {
            linkWrap = <li class="active no-trans">|</li>
            stdWrap.typolink >
        }
    }
}
