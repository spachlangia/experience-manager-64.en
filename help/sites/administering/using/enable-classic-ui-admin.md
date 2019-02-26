---
title: Admin Consoles
seo-title: Admin Consoles
description: Lear how to use the Admin Consoles available in AEM.
seo-description: Lear how to use the Admin Consoles available in AEM.
uuid: 0be56a0a-0756-4d5d-99ba-fb867ce9a4c4
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: operations
content-type: reference
discoiquuid: 42bed7a3-c482-4995-be57-7b35b95c66d4
---

# Admin Consoles{#admin-consoles}

By default, the ability to switch to the classic UI via the admin consoles has been disabled. Therefore the pop-up icons that was seen when mousing over certain console icons, allowing access to classic UI, are no longer displayed.

![](assets/screen_shot_2018-03-23at111956.png)

Every console that has a Classic UI version in `/libs/cq/core/content/nav` can be re-enabled individually so that the **Classic UI** option once again pops up over the console icon when it is moused over.

In this example, we are re-enabling the Classic UI for the Sites console.

1. Using CRXDE Lite, find the node corresponding the the admin console for which you want to re-enable Classic UI. They are found under:

   For example

1. Select the node corresponding to the console for which you want to re-enable Classic UI. For our example, we will re-enable classic UI for the Sites console.
1. Using the **Overlay Node** option, create an overlay for the selected node under `/apps` as follows:
1. Add the following boolean property to the overlaid node:
1. The **Classic UI** option is again available as a popover option in the admin console.

   ![](assets/screen_shot_2018-03-23at111924.png)

Repeat these steps for every console for which you wish to re-enable access to the Classic UI version.