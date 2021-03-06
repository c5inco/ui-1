---
title: Scrollbar
category: Controls
---

The scrollbar allows users to browse content that’s larger than the visible area, such as text or images, by scrolling it horizontally or vertically.
![]({{site.baseurl}}/images/scrollbar/scrollbar-small.png)

## Parts of a scrollbar

A scroll bar consists of a track, a thumb, and a status icon if there is a known status for displayed content.

![]({{site.baseurl}}/images/scrollbar/scrollbar-detailed.png)

### Track

A track represents the overall length or width of the document.

The track can contain optional markers for quicker navigation between the important parts of the document, for example:

* The occurrences of a search string.

* Breakpoints and the current execution lines.

* A place where an inspection failed.

* Files with errors laid out in a tree.

* Changed parts of a file.

A marker can fit the track width or be placed to the left of the track. Use the latter when you expect the marked region to be tall.

Hovering over the track can also show a lens with a preview of the content at the corresponding position in the document. This can be useful in large documents when it is not desirable to change the viewpoint:

![]({{site.baseurl}}/images/scrollbar/lens-temp.png)

### Thumb

A thumb represents the visible portion of the content. For example, a small thumb indicates that there’s lots of content available for scrolling.

### Status icon (optional)

A status icon shows the overall status of inspections performed on the content and allows you to avoid scrolling over the entire view. If at least one inspection has failed, the overall status should be the status of that inspection.

![]({{site.baseurl}}/images/scrollbar/commit.png)

## How to use

Respect the OS settings when showing the sсrollbar. For example, on Mac OS you can hide the scrollbar until you scroll the content.
Always show the scrollbar when it is important to understand which part of the content is currently shown. For example, the scrollbar in the Editor helps users understand the location of the current code fragment, and the overall size of the currently opened file.

Show the track on hover to make the clickable area clearer. Consider not showing the track on hover if it might have more than 5-10 stripes at a time.

Increase the thumb contrast against the background on hover and when scrolling to make it more prominent.

Clicking the track above/below the thumb scrolls one page up/down the viewpoint. This allows you to hide the up/down icons on the scrollbar to lessen the visual noise and to scroll with mouse-clicks.
Track markers serve as a mini-map of the document. If they are present, clicking them takes you to the position that this marker is pointing to without having to scroll down the page. Change cursor to "Hand" when hovering such scrollbars.

When showing a text, wrap it instead of showing the horizontal scrollbar when possible. With both scrollbars, it is harder to manipulate the content.
<p class='label incorrect'>Incorrect</p>
![]({{site.baseurl}}/images/scrollbar/soft-wrap-incorrect.png)

<p class='label correct'>Correct</p>
![]({{site.baseurl}}/images/scrollbar/soft-wrap-correct.png)

A horizontal scroll bar can be added for code snippets or for formatted input. Use the context menu to enable soft-wrapping.
<p class='label correct'>Correct</p>
![]({{site.baseurl}}/images/scrollbar/soft-wrap-context.png)

Show only 1 scrollbar per table which scrolls the entire table:
<p class='label incorrect'>Incorrect:</p>
![]({{site.baseurl}}/images/scrollbar/table-scrollbar-incorrect.png)

<p class='label correct'>Correct:
</p>![]({{site.baseurl}}/images/scrollbar/table-scrollbar-correct.png)

## Placement

Reserve the space for a vertical scrollbar if there is a column on the right side, otherwise the scrollbar always overlaps content.
<p class='label incorrect'>Incorrect</p>
![]({{site.baseurl}}/images/scrollbar/vertical-scrollbar-incorrect.png)

<p class='label correct'>Correct:
</p>![]({{site.baseurl}}/images/scrollbar/vertical-scrollbar-correct.png) 

## Style

<table>
<col width="183.75 px">
  <tr>
    <td>
        <p style="margin:20px 0px 0px 20px">Windows/Linux</p>
    </td>
    <td>
        <p style="margin:20px 0px 0px 40px">Mac</p>
    </td>
  </tr>
  <tr>
    <td>
        <p style="margin-left:20px">          <img src="{{site.baseurl}}/images/scrollbar/win-light.png" /></p>
    </td>
    <td>
        <p style="margin-left:20px">          <img src="{{site.baseurl}}/images/scrollbar/mac-light.png" /></p>
    </td>
  </tr>
</table>


