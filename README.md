# Sublime Text Atomic Soft Tab Nav

In Sublime Text, soft tabs (multiple spaces used as tabs) require as many arrow key presses as there are spaces to navigate. The purpose of this package is to make it so that soft tabs can be navigated just like tabs when using the arrow keys.

![Standard Demo](https://raw.githubusercontent.com/ruiokada/sublime-text-atomic-soft-tab-nav/assets/demo.gif)

Set `astn_enable_line_nav` to `true` in your Sublime Text settings file to enable atomic soft tabs when navigation by lines:

![With 'astn_enable_line_nav' True Demo](https://raw.githubusercontent.com/ruiokada/sublime-text-atomic-soft-tab-nav/assets/demo-by-lines.gif)

## Manual Install

    git clone https://github.com/ruiokada/sublime-text-atomic-soft-tab-nav.git "Atomic Soft Tab Nav"

By default, Sublime Text does not visually distinguish tabs and soft tabs so it is recommended to set `draw_white_space` to `all` in your settings file:

    {"draw_white_space": "all"}

## Functions

The functionality of this package is simple. When the text cursor encounters a soft tab during arrow key input, this plugin will modify the arrow key input accordingly. The following are the arrow key input modification details:

* Soft tabs are assumed to appear only at the beginning of lines so multiple spaces that do not span to the beginning of the line are ignored.
* If the cursor is on the edge of a soft tab, then the left/right arrow keys move the cursor as if the soft tabs were tabs.
* If the cursor is in the middle of a soft tab, then the left/right arrow keys move the cursor as if the soft tab is multiple spaces until either end of the soft tab is reached.
* If `astn_enable_line_nav` is set to true in settings then the up/down arrow keys will also treat soft tabs in a similar manner.
* The above modifications are applied even in the case when the cursor is making a text selection.
* The above modifications will not be applied if there are multiple active cursors.

If the spaces as tabs function is disabled in the current file view then this plugin will be disabled. The size of soft tabs depends on the tab size of the current file view. If there are multiple cursors, then navigation input will not be modified.
