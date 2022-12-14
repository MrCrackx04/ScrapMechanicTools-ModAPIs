---
sidebar_position: 6
title: dlm.gui
hide_title: true
sidebar-label: 'dlm.gui'
---

<br></br>

## dlm.gui

The DLM GUI library provides functions related to [GUIs](https://scrapmechanictools.com/lua/Game-Script-Environment/Static-Functions/sm.gui) and [GuiInterfaces](https://scrapmechanictools.com/lua/Game-Script-Environment/Userdata/GuiInterface).

### createGuiFromXmlString

```lua
local gui = dlm.gui.createGuiFromXmlString( xml, destroyOnClose, settings )
```
<code>Client-Only</code> <br></br>

Loads an XML data string and tries to create a [GuiInterface](https://scrapmechanictools.com/lua/Game-Script-Environment/Userdata/GuiInterface) from it.

:::info note
This function creates a temporary layout file on the hard drive. <br></br>
You can manually clear this file using [clearTemporaryLayouts](#cleartemporarylayouts). <br></br>
Temporary layout files are also automatically cleared when the save file is closed. <br></br>
The <code>settings</code> table structure is the same as the one for [sm.gui.createGuiFromLayout](https://scrapmechanictools.com/lua/Game-Script-Environment/Static-Functions/sm.gui#createguifromlayout).
:::

<strong>Arguments:</strong> <br></br>

- <code>xml</code> [<strong> string </strong>]: The XML layout string.
- <code>destroyOnClose</code> [<strong> bool </strong>]: Whether the guiInterface is destroyed when closed or not. Defaults to false.
- <code>settings</code> [<strong> table </strong>]: Table with GUI settings. See sm.gui.createGuiFromLayout.

<strong>Returns:</strong> <br></br>

- [<strong> guiInterface </strong>]: The created guiInterface.

---

### clearTemporaryLayouts

```lua
dlm.gui.clearTemporaryLayouts()
```
<code>Client-Only</code> <br></br>

Clears temporary GUI layout files generated by [createGuiFromXmlString](#createguifromxmlstring).

Note that this also happens automatically when the game world/save is closed.

:::info note
You can call this function every tick, it is internally limited to every 5 ticks. <br></br>
A temporary layout file will only be deleted a minimum of one tick after its creation.
:::

---

### getHypertext

```lua
local hypertext = dlm.gui.getHypertext( text, textShadow, background, color, spacing )
```

This is a utility function.
It generates a [hypertext](https://scrapmechanictools.com/lua/Game-Script-Environment/Static-Functions/sm.gui#setinteractiontext) string using the given input.

<strong>Arguments:</strong> <br></br>

- <code>text</code> [<strong> string </strong>]: The text to format.
- <code>textShadow</code> [<strong> boolean </strong>]: Whether the text should have a shadow or not. Defaults to false.
- <code>background</code> [<strong> string </strong>]: The name of the text background. Defaults to "gui_keybinds_bg_orange".
- <code>color</code> [<strong> Color </strong>]: The color of the text.
- <code>spacing</code> [<strong> number </strong>]: The spacing between the text and the highlight box borders. Defaults to 9.

<strong>Returns:</strong> <br></br>

- [<strong> string </strong>]: The hypertext formatted string.

---

### getHypertextImage

```lua
local hypertext = dlm.gui.getHypertextImage( name, background, spacing )
```

This is a utility function.
It generates a [hypertext image](https://scrapmechanictools.com/lua/Game-Script-Environment/Static-Functions/sm.gui#setinteractiontext) string using the given input.

<strong>Arguments:</strong> <br></br>

- <code>name</code> [<strong> string </strong>]: The name or path of the image, e.g. "$CONTENT_DATA/image.png".
- <code>background</code> [<strong> string </strong>]: The name of the image background. Defaults to "gui_keybinds_bg".
- <code>spacing</code> [<strong> number </strong>]: The spacing between the image and the highlight box borders. Defaults to 0.

<strong>Returns:</strong> <br></br>

- [<strong> string </strong>]: The hypertext image formatted string.

---
