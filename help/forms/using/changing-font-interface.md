---
title: Changing the font on the interface
seo-title: Changing the font on the interface
description: How to change the fonts on the user interface selectively.
seo-description: How to change the fonts on the user interface selectively.
uuid: 9bcb2a64-c40d-4f87-a23a-759a7435cd39
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: c0fb565a-5999-4107-83e7-0d06af3c6c4a
---

# Changing the font on the interface{#changing-the-font-on-the-interface}

You can change the font displayed in AEM Forms workspace. Fonts used in a specific section of the user interface are defined in the corresponding section of the style sheet. You can change the fonts on the user interface selectively.

Follow the [Generic steps for AEM Forms workspace customization](../../forms/using/generic-steps-html-workspace-customization.md) and depending on your requirements, follow the steps for customizing CSS, HTML, or both.

1. Change or add the font-family in an existing style.  
1. Change or add the font-family inline for the HTML element.
1. Add a style and use it for the HTML element.

As an example, to change the font of the top navigation bar anchor text to Courier New, follow these steps:

1. Log in to CRXDE Lite by accessing `http://[server]:[port]/lc/crx/de/index.jsp`.
1. Do one of the following:

    1. To change the font-family in an existing style, add the following in the newStyle.css file at /apps/ws/css.

       ```css    
       #topnav a {
          font-family: "Courier New";
       }
       ```

    1. To add the font-family inline for the HTML element, copy the `/libs/ws/js/runtime/templates/appnavigation.html` file to `/apps/ws/js/runtime/templates/appnavigation.html`.

       Update the /apps/ws/js/runtime/templates/appnavigation.html file as follows:

       ```    
       <li class="process"><a href="#" title="<%= $.t('index.header.topnav.startprocess.detail')%>" style="font-family:Courier New;" ><%= $.t('index.header.topnav.startprocess.name')%></a></li>
       <li class="todo"><a href="#/todo" title="<%= $.t('index.header.topnav.todo.detail')%>" style="font-family:Courier New;" ><%= $.t('index.header.topnav.todo.name')%></a></li>
       <li class="track"><a href="#/tracking" title="<%= $.t('index.header.topnav.tracking.detail')%>" style="font-family:Courier New;" ><%= $.t('index.header.topnav.tracking.name')%></a></li>
       <li class="preference"><a href="#/preferences" title="<%= $.t('index.header.topnav.preferences.detail')%>" style="font-family:Courier New;" ><%= $.t('index.header.topnav.preferences.name')%></a></li>
       ```    
    
       Open the /apps/ws/js/registry.js file for editing and replace `text!/lc/libs/ws/js/runtime/templates/appnavigation.html` with `text!/lc/apps/ws/js/runtime/templates/appnavigation.html`.
    
    1. To add a style defining the font-family, add the following in the newStyle.css file at /apps/ws/css.

       ```css    
       .myNewFontStyle a {
          font-family: "Courier New";
       }
       ```    
    
       To add the font-family inline for the HTML element, add the following in the appnavigation.html file at /apps/ws/js/runtime/templates.

       ```css    
       <div id="topnav" class="myNewFontStyle">
           <ul>
               <li class="process"><a href="#" title="<%= $.t('index.header.topnav.startprocess.detail')%>" ><%= $.t('index.header.topnav.startprocess.name')%></a></li>
               <li class="todo"><a href="#/todo" title="<%= $.t('index.header.topnav.todo.detail')%>"><%= $.t('index.header.topnav.todo.name')%></a></li>
               <li class="track"><a href="#/tracking" title="<%= $.t('index.header.topnav.tracking.detail')%>" ><%= $.t('index.header.topnav.tracking.name')%></a></li>
               <li class="preference"><a href="#/preferences" title="<%= $.t('index.header.topnav.preferences.detail')%>" ><%= $.t('index.header.topnav.preferences.name')%></a></li>
           </ul>
       </div>
       ```

1. Relaunch the workspace and clear the browser cache for the changes to be visible.

![](assets/change_font_before.png)

Top navigation bar before font customization

![](assets/change_font_after.png)

Top navigation bar after font customization of first tab

[**Contact Support**](https://www.adobe.com/account/sign-in.supportportal.html)