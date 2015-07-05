---
layout: post
title: "Drag &amp; drop with AIR"
date: 2011-10-18 10:52
comments: true
categories: [as3, drag and drop, tutorial]
---

This is a small blogpost on how to implement drag and drop functionality in an AIR-application. It can be used to make an application much more easier to work with.

At first, you have to add two event listeners to the component, `NATIVE_DRAG_ENTER` and `NATIVE_DRAG_DROP`. Both of them are `NativeDragEvents`.

{% codeblock lang:as3 %}
addEventListener(NativeDragEvents. NATIVE_DRAG_ENTER, nativedragenterHandler);
addEventListener(NativeDragEvents. NATIVE_DRAG_DROP, nativedragdropHandler);
{% endcodeblock %}

The `nativedragenterHandler` will be triggered whenever a user hovers the component with one or more files selected. The `nativedragdropHandler` will be triggered when the user ‘drops’ his files on this component.

Put this code in the `nativedragenterHandler`, to let the component accept a user to drop his files here.

{% codeblock lang:as3 %}
DragManager.acceptDragDrop(this);
{% endcodeblock %}

Everything else happens in the `nativedragdropHandler`. The code below shows you how to fetch the dropped files, so you can work with them in the application.

{% codeblock lang:as3 %}
var droppedFiles:Array = event.clipboard.getData(ClipboardFormats.FILE_LIST_FORMAT) as Array;
{% endcodeblock %}
