# Highlight trailing spaces and delete them in a flash

Open vscode and rigth click on the Activity Bar and click on Extensions. New Icon shows in the Activity Bar. Click on Icon and type in the Search Trailing Spaces.

Install the extension and Reload

Add to the keybinding code below to delete all spaces.
```
{ "key": "alt+shift+t",        "command": "trailing-spaces.deleteTrailingSpaces",
                                  "when": "editorTextFocus" },
```
Add to the keybinding code below to delete modified lines only.
```
{ "key": "alt+shift+m",        "command": "trailing-spaces.deleteTrailingSpacesModifiedLinesOnly",
                                  "when": "editorTextFocus" },
```
For more information https://marketplace.visualstudio.com/items?itemName=shardulm94.trailing-spaces