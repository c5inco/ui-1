---
title: Button
type: GroupHeader
category: Controls
---

![]({{site.baseurl}}/images/button/example.png)

## When to use

Use a button to invoke an immediate action. In some cases use a link, toolbar buttons and a split button instead:

1. Use a [link]({{site.baseurl}}/controls/link) if:
  * The action takes the user to another page of the same dialog or an external source like documentation:
    ![]({{site.baseurl}}/images/button/link_after.png)
    *The Manage scope link takes to another page of the Settings dialog.*
    **Exception**: Next and Previous buttons in wizard navigation.    
  * The command is a secondary action that is not related to the primary purpose of the window and the space is constrained. For example, the _Reset_ action in the Settings dialog.
    <p class="label incorrect">Incorrect</p>
    ![]({{site.baseurl}}/images/button/link_incorrect.png)
    
    <p class="label correct">Correct</p>
    ![]({{site.baseurl}}/images/button/link_correct.png)  
    
2. Use toolbar buttons if there are several buttons related to a table or list:
   <p class="label incorrect">Incorrect</p>
   ![]({{site.baseurl}}/images/button/many_buttons.png)
   
   <p class="label correct">Correct</p>
   ![]({{site.baseurl}}/images/button/toolbar.png)
   
3. Use a [split button]({{site.baseurl}}/controls/split_button) instead if: 
   * There are several related actions (more than 2) but the space is limited and/or packed.
   * The action is not common and is dangerous, for example, can destroy user data and cannot be easily undone.



## How to use

### Label
The label displays the action the button performs.
* Write the label as an imperative verb, e.g. Save, Print, Cancel.

  **Exceptions**: standard buttons like OK, Back/Forward, Previous/Next, Yes/No, Agree, Options, Settings, Details.
* Use title capitalization.
* The button should answer the question in the title, so the user can skip the description. Prefer specific labels over generic ones:
    <table>
    <col width="250px">
        <tr>
            <td> <p class="label incorrect">Incorrect</p> </td>
            <td> <p class="label correct">Correct</p> </td>
        </tr>
        <tr>
            <td> <img src="{{site.baseurl}}/images/button/default_OK.png" style="margin-top: -5px"> <em style="margin-bottom: 5px;">Unclear what happens on the click.</em> </td>
            <td> <img src="{{site.baseurl}}/images/button/default_save.png" style="margin-top: -5px"> <em style="margin-bottom: 5px;">The label indicates what happens on the click.</em> </td>
        </tr>
    </table>
    **Exception**: the Cancel button if it is clear what action is being canceled. For example:
	![]({{site.baseurl}}/images/button/mac_new_file.png)
	*Use the Cancel button, not the Don’t Create button.*
	
* The label should be short, not more than 5 words. If it’s not obvious what element the button is related to, add more words to make it clear. Prefer clear labels to short:
    <table>
    <col width="200px">
        <tr>
            <td> <p class="label incorrect">Acceptable</p> </td>
            <td> <p class="label correct">Better</p> </td>
        </tr>
        <tr>
            <td> <img src="{{site.baseurl}}/images/button/active_edit.png" style="margin-top: -5px; margin-bottom: 5px;">  </td>
            <td> <img src="{{site.baseurl}}/images/button/active_edit_action_icon.png" style="margin-top: -5px; margin-bottom: 5px;">  </td>
        </tr>
    </table>


* Add an ellipsis if additional actions such as adding more info or confirming the action are required:
![]({{site.baseurl}}/images/button/buttons_with_ellipsis.png)

  Do **not** add ellipsis if another window is opened, but no more input from the user is required. For example, About, Details. 

* Do **not** use the word _Now_ in the label because button always trigger an immediate action:
 
  <p class="label incorrect">Incorrect</p>
  ![]({{site.baseurl}}/images/button/check_now.png)
     
  <p class="label correct">Correct</p>
  ![]({{site.baseurl}}/images/button/check_for_updates.png)

* Use the _Close_ label only if nothing can be changed in the dialog and there is no confirmation button, for example in the Productivity Guide dialog. In all other cases, use the _Cancel_ button.

* Do **not** add an icon to the button. The main purpose of an icon is to quickly find a familiar action in a packed toolbar or menu. Usually, no more than 3 buttons are placed nearby, their labels can be scanned quickly and icons are not required.


### Hover
On hovering over a button, show a tooltip with the shortcut and the action name if it can be clarified. 
    
<table>
<col width="180px">
<col width="230px">
    <tr>
        <td> <img src="{{site.baseurl}}/images/button/hover_shortcut.png" style="margin-top: -5px"> <em style="margin-bottom: 5px;">If the action is clear, show the shortcut only.</em> </td>
        <td> <img src="{{site.baseurl}}/images/button/hover_name_shortcut.png" style="margin-top: -5px"> <em style="margin-bottom: 5px;">If the action can be clarified, show the action name and the shortcut.</em> </td>
    </tr>
</table>		
	
For more details see [Context help]({{site.baseurl}}/principles/context_help).

### Size

The button width accommodates the length of the label plus standard indents, but not less than the minimum size (see the [Style section](#style)).
![]({{site.baseurl}}/images/button/sizes.png)     
    
The button height is fixed, so the label is always a single line.


### Placement

* If a button is related to a control, place it to the right of the control if there is enough space for it:
  ![]({{site.baseurl}}/images/button/check_for_updates.png)
  Align the button with the text baseline or the control bottom border:
  ![]({{site.baseurl}}/images/button/placement_align.png)
  
* If a button is related to a group of controls, or if the space on the right is limited, place the button under these controls and left-align it:
  ![]({{site.baseurl}}/images/button/placement_bottom.png)
  
* If buttons are related to the whole dialog, place them at the bottom and right-align them:
  ![]({{site.baseurl}}/images/button/mac_new_file.png)
  For more details on buttons placement in Dialogs, see the [Dialog Window section]({{site.baseurl}}/components/dialog_window).

  
## Button states

### Default
<table>
    <tr>
        <td> <img src="{{site.baseurl}}/images/button/default_save.png" style="margin-top: -5px"> <em style="margin-bottom: 5px;">Mac OS</em> </td>
        <td> <img src="{{site.baseurl}}/images/button/default_save_win.png" style="margin-top: -5px"> <em style="margin-bottom: 5px;">Windows</em> </td>
    </tr>
</table>
The default button confirms the main purpose of a dialog and is triggered by pressing <kbd>Enter</kbd> or <kbd>Ctrl+Enter</kbd>.

**Exception**: If the focus is on an element that uses the <kbd>Enter</kbd> key (e.g. a text area or a table row), the default button is triggered only by <kbd>Ctrl+Enter</kbd>.

The default button should be always present in a dialog. Only one button in a dialog can be the default one. 

Do **not** use the default button, or make a secondary button the default one if the users’ most probable action is dangerous, e.g. can lead to data loss:
![]({{site.baseurl}}/images/button/merge_dialog.png)


### Focused

![]({{site.baseurl}}/images/button/focused.png)
All buttons can get focus, even on Mac OS if the **Full Keyboard Access** option is disabled in Preferences > Keyboard > Shortcuts. 
A focused button behavior varies on Mac OS/Linux and Windows.

* **Mac OS/Linux**

  A focused button is invoked by pressing <kbd>Space</kbd>. Focused and default buttons are **independent**, so when the focus moves from one button to another, the default button does not change.
  
  Make the second most popular button in the dialog focused. For example, the _New Window_ button in the Open Project dialog:
  ![]({{site.baseurl}}/images/button/open_project_dialog.png)
  
  It’s recommended to have one default and one focused button, so that most of the actions can be triggered using the keyboard.
  <p class="label incorrect">Incorrect</p>
  ![]({{site.baseurl}}/images/button/open_project_dialog_incorrect_focus.png)
  *The This Window button is the default and the focused one, while it’s better to place the focus on the New Window button, so that the user can access both options using the keyboard.*
  

* **Windows**

  The focused button is triggered by pressing <kbd>Enter</kbd> or <kbd>Space</kbd>. If non-default button gets focus, the default button is invoked using <kbd>Ctrl+Enter</kbd>.
  ![]({{site.baseurl}}/images/button/open_project_dialog_win.png)
  *On pressing the Tab key, the New Window button gets the focus and is triggered with Enter or Space. The original This Window button is triggered with Ctrl+Enter.*
  If the focus moves to a control that’s not a button, the original default button is triggered by <kbd>Enter</kbd>.


### Disabled
![]({{site.baseurl}}/images/button/disabled.png)

Disable a button if:
* It’s an Apply button and no changes have been made in this dialog.
* The control to which the button is related is disabled.
* Not all required fields in the dialog are filled. For more details, see the [Required field section]({{site.baseurl}}/principles/required_fields).



Other common buttons are described below. They can be regular or default buttons.

### Cancel
The _Cancel_ button reverts the app to the state before the dialog was invoked, and works equivalent to the <kbd>Esc</kbd> key on Win and Linux, and <kbd>Esc</kbd> or <kbd>Cmd+Period</kbd> on Mac. 
If a confirmation button is present in a dialog, e.g. OK or Save, it’s recommended to have a button that cancels the dialog, e.g. Cancel, Continue Editing, etc.


### Apply
Use the Apply button in dialogs with many settings that affect how data is displayed. The Apply button allows you to save and preview the effect of the selected options, and continue changing the settings, for example, change a scheme in Settings.


### Help
![]({{site.baseurl}}/images/button/helpButton_mac.png)
The help button appears in the bottom-left corner of a dialog and shows help in a tooltip on hover, or opens a help dialog on clicking it. For more details see [Context help]({{site.baseurl}}/principles/context_help).


## Control button
A Сontrol button is a small square button placed on the right of  a control:
![]({{site.baseurl}}/images/button/control_button.png)

The shortcut for a Control Button is <kbd>Shift+Enter</kbd>.
 
It’s **not** recommended to use control buttons, because they clutter the UI. Use input fields with built-in icons instead.

### Browse
![]({{site.baseurl}}/images/button/browse_buttons.png)
A browse button opens a dialog with the disk, a tree view or a table of values. 
Use an input field with the browse icon for a file/folder path selected from the disk:
![]({{site.baseurl}}/images/button/input_browse.png)
Use an input field with the table icon for classes, methods or environment variables:
![]({{site.baseurl}}/images/button/input_table.png)  


### Add value
![]({{site.baseurl}}/images/button/plus.png)
The Plus button works the same way as the Browse button, the only difference is that the selected value is added, instead of overwriting the existing one. Use an input field with the plus icon instead.


### Expand field
Use the [Expandable input field]({{site.baseurl}}/controls/input_field/#input-field-types) instead of the Show Viewer button to open a popup with a multiline input field. 
![]({{site.baseurl}}/images/button/input_expand.png)


### Variables
Use a combo box instead of the Variables button:
![]({{site.baseurl}}/images/button/variables_combobox.png)
This icon works as a combo box.


### Copy, Info

<table>
<col width="130px">
    <tr>
        <td> <img src="{{site.baseurl}}/images/button/copy_button.png" style="margin-top: -5px"></td>
        <td> Do not use the Copy button, the content can be selected and copied using the Cmd/Ctrl+C shortcut or the context menu. </td>
    </tr>
    <tr>
        <td> <img src="{{site.baseurl}}/images/button/info_button.png" style="margin-top: -5px"></td>
        <td> Do not use the info button to open an external link. Use context help instead.</td>
    </tr>
</table>


## Style
### Size and colors
The font size and colors are the default ones. 
<table>
<col width="25%">
<col width="25%">
<col width="25%">
<col width="25%">
    <tr>
        <td style="margin-left: 20px"> Mac OS </td>
        <td> Windows </td>
        <td> Darcula </td>
        <td> IntelliJ </td>
    </tr>
    <tr>
        <td> <img src="{{site.baseurl}}/images/button/size_margins_mac.png" style="margin: -5px 0 0 0"><em style="margin: 10px 0 0 0">On retina, the button height is 40px.</em></td>
        <td> <img src="{{site.baseurl}}/images/button/size_margins_win.png" style="margin: -5px 0 0 0"></td>
        <td> <img src="{{site.baseurl}}/images/button/size_margins_darcula.png" style="margin: -5px 0 0 0"></td>
        <td> <img src="{{site.baseurl}}/images/button/size_margins_intellij.png" style="margin: -5px 0 0 0"></td>
    </tr>
</table>
<table>
<col width="21%">
<col width="22%">
<col width="22%">
<col width="22%">
<col width="22%">
    <tr>
        <td>  </td>
        <td style="margin-left: 20px"> Mac OS </td>
        <td> Windows </td>
        <td> Darcula </td>
        <td> IntelliJ </td>
    </tr>
    <tr>
        <td> <p style="color: #999999; margin-top: -5px;"> Regular </p></td>
        <td> <img src="{{site.baseurl}}/images/button/regular_mac.png" style="margin: -5px 0 0 0"></td>
        <td> <img src="{{site.baseurl}}/images/button/regular_win.png" style="margin: -5px 0 0 0"></td>
        <td> <img src="{{site.baseurl}}/images/button/regular_dark.png" style="margin: -5px 0 0 0"></td>
        <td> <img src="{{site.baseurl}}/images/button/regular_intellij.png" style="margin: -5px 0 0 0"></td>
    </tr>
    <tr>
        <td> <p style="color: #999999; margin-top: -5px;"> Default </p></td>
        <td> <img src="{{site.baseurl}}/images/button/default_mac.png" style="margin: -5px 0 0 0"></td>
        <td> <img src="{{site.baseurl}}/images/button/default_win.png" style="margin: -5px 0 0 0"></td>
        <td> <img src="{{site.baseurl}}/images/button/default_dark.png" style="margin: -5px 0 0 0"></td>
        <td> <img src="{{site.baseurl}}/images/button/default_intellij.png" style="margin: -5px 0 0 0"></td>
    </tr>
    <tr>
        <td> <p style="color: #999999; margin-top: -5px;"> Focused </p></td>
        <td> <img src="{{site.baseurl}}/images/button/focused_mac.png" style="margin: -5px 0 0 0"></td>
        <td> <img src="{{site.baseurl}}/images/button/focused_win.png" style="margin: -5px 0 0 0"><em style="margin: 0">and hovered</em></td>
        <td> <img src="{{site.baseurl}}/images/button/focused_dark.png" style="margin: -5px 0 0 0"></td>
        <td> <img src="{{site.baseurl}}/images/button/focused_intellij.png" style="margin: -5px 0 0 0"></td>
    </tr>
    <tr>
        <td> <p style="color: #999999; margin-top: -5px;"> Disabled </p></td>
        <td> <img src="{{site.baseurl}}/images/button/disabled_mac.png" style="margin: -5px 0 0 0"></td>
        <td> <img src="{{site.baseurl}}/images/button/disabled_win.png" style="margin: -5px 0 0 0"></td>
        <td> <img src="{{site.baseurl}}/images/button/disabled_dark.png" style="margin: -5px 0 0 0"></td>
        <td> <img src="{{site.baseurl}}/images/button/disabled_intellij.png" style="margin: -5px 0 0 0"></td>
    </tr>
    <tr>
        <td> <p style="color: #999999; margin-top: -5px;"> Pressed </p></td>
        <td></td>
        <td> <img src="{{site.baseurl}}/images/button/pressed_win.png" style="margin: -5px 0 0 0"></td>
        <td> </td>
    </tr>
    <tr>
        <td> <p style="color: #999999; margin-top: -5px;"> Help </p></td>
        <td> <img src="{{site.baseurl}}/images/button/helpButton_mac.png" style="margin: -5px 0 0 0"></td>
        <td> <img src="{{site.baseurl}}/images/button/helpButton_win.png" style="margin: -2px 0 0 0"></td>
        <td> <img src="{{site.baseurl}}/images/button/helpButton_dark.png" style="margin: -6px 0 0 0"></td>
    </tr>
</table>

### Spacing
<table>
<col width="140px">
<col width="200px">
<col width="300px">
    <tr>
        <td>  </td>
        <td> Mac OS, Darcula </td>
        <td> Windows </td>
    </tr>
    <tr>
        <td> <p style="color: #999999; margin-top: 10px;"> Several buttons </p></td>
        <td> <img src="{{site.baseurl}}/images/button/size_1.png" style="margin: -5px 0 0 0"></td>
        <td> <img src="{{site.baseurl}}/images/button/size_2.png" style="margin: -5px 0 0 0"></td>
    </tr>
</table>
<table>
<col width="140px">
    <tr>
        <td> <p style="color: #999999; margin-top: 10px;"> Button on the right </p></td>
        <td> <img src="{{site.baseurl}}/images/button/size_3.png" style="margin: -5px 0 0 0"></td>
    </tr>
    <tr>
        <td>  </td>
        <td> <img src="{{site.baseurl}}/images/button/size_4.png" style="margin: -5px 0 0 0"></td>
    </tr>
    <tr>
        <td>  </td>
    </tr>
    <tr>
        <td> <p style="color: #999999; margin-top: -5px;"> Button under </p></td>
        <td> <img src="{{site.baseurl}}/images/button/size_5.png" style="margin: -5px 0 0 0"></td>
    </tr>
</table>
   
   

















































