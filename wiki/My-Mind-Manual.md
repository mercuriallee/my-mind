This page documents the basic usage of the [My Mind](https://mercurial.top/my-mind) application.

## Moving around
You can move the map around using the **W/A/S/D** keys or by dragging the map background with a mouse. Note that dragging a map node does something different - it initiates a drag-drop node operation.

To zoom the map (adjust text size), use the **+/-** keys or the mouse wheel. You can center the map by pressing the **End** key.

Nodes can be folded (collapsed) to save some space; a folded node does not show its children. Instead, an "unfold" icon is visible. To fold a node, hit the **F** key or click the blue plus/minus sign next to an active node.

## Selecting nodes 
There is always one node selected. All node-related operations apply to this node. There are multiple ways of selecting a node.

Clicking a node to select it is the most straightforward approach. Keyboard **arrows** select its children, siblings and parent node with respect to topology. **Home** key selects the root node, **backspace** moves the selection to the parent node.

## Editing nodes
Node contents are edited in-place via a tiny WYSIWYG feature. Enter the edit mode either by double-clicking a node, or by pressing **spacebar**. The **F2** key does the same thing.

Once you begin editing a node, you can apply various styling to the selected text:

Key    | Styling
-------|--------
Ctrl+B | Bold
Ctrl+I | Italic
Ctrl+U | Underline
Ctrl+S | Strike-through
Ctrl+Enter, Shift+Enter | Forced line break

Hyperlinks are automatically detected and underlined.

### Layout
Individual nodes can use different layout algorithms for their children. By default, the root node uses the _Map_ layout that is inherited by all other nodes. You can override this by using the **LAYOUT** drop-down in the right UI pane.

### Shapes
Node shape can be changed using the **SHAPE** drop-down in the right UI pane.

### Values
Every node can contain a numerical value. This value is independent of the node's text. Node values are displayed in parentheses. You can also assign a mathematical function (currently: **sum**, **avg**, **max**, **min**) as a value: this allows for easy aggregation of children's values.

To set a value, either use the **VALUE** drop-down in the right UI page or press the **V** key.

### Status
A boolean (yes/no) status icon can be shown next to a node. It is possible to set this status in an explicit manner or to compute it automatically, based on child statuses. Use the **STATUS** drop-down in the right UI or **Y/N/C** keys to do so.


### Colors
Once you assign a color to a node, all of its children (and their connector lines) will inherit it. Pick a color by clicking it in the right UI pane.

## Manipulating nodes
Adding new nodes: **Insert** (or **Tab**) key inserts a new child; **Enter** key inserts a sibling.

Removing nodes: **Delete** removes a node with all its children.

Clipboard: **Ctrl+C/Ctrl+X/Ctrl+V** are working as expected, copying and moving nodes around. You can even copy/paste to/from an external application; simple tab-indented serialization is used.

To swap with a previous/next sibling, hit **Ctrl+up/down**. To switch sides (left/right), hit **Ctrl+left/right** (this only works for direct descendants of the root node using a Map layout).


## Saving and loading maps
There is a [[dedicated page|Saving and loading]] for this topic.

## Creating map images
There is a [[dedicated page|Saving-images-client-side]] for this topic.

## Other
You can show/hide a quick help window by hitting the **?** key or by pressing the "Help" button. The right UI pane can be hidden by hitting the asterisk (<strong>*</strong>) key or by clicking the round arrow button in the bottom-right area.

Undo/redo arbitrary number of actions using the **Ctrl+Z/Ctrl+Y** keys.

Right-clicking (or a "tap-for-a-longer-time") operation opens up the context menu. This is suitable for keyboard-less control.
