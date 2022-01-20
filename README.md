# <img src="https://github.com/KoBeWi/Godot-Action-Icon/blob/master/Media/Icon.png" width="64" height="64"> Godot Action Icon

Action Icon is a TextureRect-based custom GUI node that you can put on a scene and it will display the associated action. Just activate the plugin and add ActionIcon to your scene. Note that in-editor preview is limited.

![](https://github.com/KoBeWi/Godot-Action-Icon/blob/master/Media/Screenshot1.png)

It has a couple of display modes to configure:

- Action Name: the name of the action from project's Input Map
- Joypad Mode: whether the action should display keyboard key or joypad button. If set to "Adaptive", the icon will automatically change when it detects keyboard or joypad input. Only relevant to actions that have both assigned.

![](https://github.com/KoBeWi/Godot-Action-Icon/blob/master/Media/ReadmeActions.gif)

You can define a custom action, by going to `ActionIcon.gd` script and editing the `CUSTOM_ACTIONS` constant. By default there is a "move" action that displays WSAD/Left Stick.

- Joypad Model: model of the joypad to display. Supported are: Xbox, DualShock, Joy-Con. If set to auto, the script will try to auto-detect the controller based on joy name returned by Godot. You need to bind the action with some device to enable detection, "Any Device" option won't work. Fallbacks to Xbox if detection fails. All auto-model icons are refreshed when new device is connected, so icons will auto-update if joypad changes.
- Favor Mouse: if an action has a keyboard and mouse button configured, `favor_mouse` set to true will display the mouse button
- Fit Mode: Node = the icon will use whatever size you set. Match Width = the icon minimum width will match its height. Useful e.g. inside HBoxContainer. Match Height = same, but matches height to width.

![](https://github.com/KoBeWi/Godot-Action-Icon/blob/master/Media/ReadmeSize.gif)

If you change your input mappings in-game, you can use `get_tree().call_group("input_actions", "refresh")` to refresh all visible icons to match the newly assigned input.

You can customize the appearance of buttons by going to 'addons/ActionIcon` and relevant button folders. By default the Action Icon comes with keyboad, mouse and XBox buttons from [xelu's CC0 input icons pack](https://opengameart.org/content/free-keyboard-and-controllers-prompts-pack).