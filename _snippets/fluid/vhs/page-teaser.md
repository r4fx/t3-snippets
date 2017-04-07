---
title: Page teaser on Fluid and VHS
description: Teaser based od pages, made with help of VHS.
tags: [vhs, teaser, fluid, menu, directory]
date: 2016-12-23
author: Rafał Brzeski
---

~~~ xml
{namespace v=FluidTYPO3\Vhs\ViewHelpers}

<v:menu.directory pages="{data.uid}" as="bricks" expandAll="true">
    <f:for each="{bricks}" as="brick">
        <div class="bricks-container__item col-6">
            <f:link.typolink parameter="{brick.uid}">
                <h3 class="section-header">{brick.title}</h3>
                <figure>
                    <v:page.resources.fal table="pages" field="media" uid="{brick.uid}" as="images" limit="1">
                        <f:if condition="{images}">
                            <f:then>
                                <f:for each="{images}" as="image">
                                    <f:switch expression="{brick.tx_mask_teasertype}">
                                        <f:case value="superWide">
                                            <f:image src="{image.url}" alt="{image.title}" width="1670c" height="364c" />
                                        </f:case>
                                        <f:case value="superHeight">
                                            <f:image src="{image.url}" alt="{image.title}" width="784c" height="865c" />
                                        </f:case>
                                        <f:case default="TRUE">
                                            <f:image src="{image.url}" alt="{image.title}" width="784c" height="364c" />
                                        </f:case>
                                    </f:switch>
                                </f:for>
                            </f:then>
                            
                            <f:else>
                                <f:image src="/assets/images/image-not-available.png" alt="{image.title}" width="784c" height="364c" />
                            </f:else>
                        </f:if>
                    </v:page.resources.fal>
                </figure>
                <p>{brick.abstract}</p>
            </f:link.typolink>
        </div>
    </f:for>
</v:menu.directory>
~~~
