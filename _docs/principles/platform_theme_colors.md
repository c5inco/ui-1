---
title: Platform theme colors
category: Principles
---

There are two default color themes: IntelliJ Light and Darcula.

![]({{site.baseurl}}/images/platform_theme_colors/01_default_themes.png)

<p class="noanchor">Use the colors consistently within the default themes. To do so, follow these guidelines:</p>
* [Icons]({{site.baseurl}}/principles/icons)&nbsp;&nbsp;&nbsp;<span style="color: #999999;">In the article about icons</span>
* [UI components](#UI-components)
* Editor scheme&nbsp;&nbsp;<span style="color: #999999;">TBD</span>
* Charts&nbsp;&nbsp;<span style="color: #999999;">TBD</span>

## UI components
Colors for UI components are specified with **color keys**. A color key is a name of a color property in a particular component, e.g. `ComboBox.background`, or a generic color property for several components, e.g. `Component.borderColor`.
![]({{site.baseurl}}/images/platform_theme_colors/02_keys_naming.png)
*Color keys of a combo box*

Each key has two default color values: one for IntelliJ Light and another for Darcula. Example: `ComboBox.background` is #FFFFFF in IntelliJ Light and #3C3F41 in Darcula.

Keys allow creating [custom color themes](http://www.jetbrains.org/intellij/sdk/docs/reference_guide/ui_themes/themes_intro.html). A custom theme is one of the default themes plus a set of color keys with new values in a JSON file. Example: the High contrast theme is a custom theme based on Darcula. New color values are stored in the [JSON file](https://github.com/JetBrains/intellij-community/blob/master/platform/platform-resources/src/themes/HighContrast.theme.json).

<aside class="note sideblock _visible">See custom themes in the <a href="https://plugins.jetbrains.com/search?tags=Theme">plugins repository</a>.</aside>

See the meanings of the parts in a color key in the [key naming scheme](http://www.jetbrains.org/intellij/sdk/docs/reference_guide/ui_themes/themes_metadata.html#key-naming-scheme). 

See a complete list of keys with their descriptions in the JSON files: [IntelliJ custom keys](https://github.com/JetBrains/intellij-community/blob/master/platform/platform-resources/src/themes/metadata/IntelliJPlatform.themeMetadata.json), [JDK keys](https://github.com/JetBrains/intellij-community/blob/master/platform/platform-resources/src/themes/metadata/JDK.themeMetadata.json).

See the color values for the currently selected theme in the LaF Defaults dialog:

<aside class="note sideblock _visible">To store color values between theme switching, use a scratch <code>*.theme.json</code> file. This might be useful if you want to test colors before implementing them. See guidelines for the <a href="http://www.jetbrains.org/intellij/sdk/docs/reference_guide/ui_themes/themes_customize.html#defining-named-colors">theme JSON structure</a>.</aside>

* The dialog is available in the [internal mode](http://www.jetbrains.org/intellij/sdk/docs/reference_guide/internal_actions/enabling_internal.html). See Tools > Internal Actions > UI in the main menu or find it with Go to Action.
* Some color keys are not shown in the dialog by default because they are loaded at runtime with a corresponding UI component. Open the UI with this component to see such keys in the dialog.
* Edit a color in the dialog to preview it in the IDE. The edited color is stored until the theme is switched.
  
![]({{site.baseurl}}/images/platform_theme_colors/03_LaF_Defaults.png)

<aside class="note sideblock _visible">For IntelliJ designers: 
<ol>
<li>Provide color keys in design specifications to be sure that correct keys are used.</li>
<li>When a new key is implemented, check that <a href="https://github.com/JetBrains/intellij-community/blob/master/platform/platform-resources/src/themes/metadata/IntelliJPlatform.themeMetadata.json">IntelliJPlatform.themeMetadata.json</a> has the new key with the “since” parameter and description, and the old keys are deprecated.</li>
</ol>
</aside>

If a color is needed:
1. Choose a color value for all default themes:
* Try reusing any of the existing colors first. Use the LaF Defaults dialog to see the existing colors.
* If none of them fit, choose two new color values that are consistent with IntelliJ Light and Darcula palettes in hue and contrast.
2. Choose a color key if a component does not have it:
* Use an existing color key if it fits semantically. Otherwise, a UI component might get an unexpected color in a custom color theme.
* Create a new key if none of the existing ones fit semantically. Follow the naming scheme.

<p class="noanchor" style="margin-left: 42px;">
<span>Example:</span><br/>
<span class="incorrect">Incorrect:</span> A new component with a light-blue background reuses <code>Focus.borderColor</code> which has a light-blue color in the default themes. A theme author decides they need a bright focus border and changes the color value for <code>Focus.borderColor</code>. As a result, the new component has a bright background with the text unreadable over it.<br/><br/>

<span class="correct">Correct:</span> A new component with a light-blue background has its own color key <code>ComponentName.background</code>.<br/><br/>
</p>


**Implementation**  
Use `JBColor.namedColor` to set a color key and fallback color values:
<div class="code-block__wrapper">{% highlight java %}
private static final Color SELECTED_BACKGROUND_COLOR = JBColor.namedColor("CompletionPopup.selectionBackground", new JBColor(0xc5dffc, 0x113a5c));
{% endhighlight %}</div>