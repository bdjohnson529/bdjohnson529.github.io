---
title: "Context Menu"
layout: default
---
# Configure the Windows Context Menu
The Windows context menu is the menu which appears when you right click in the Windows file explorer. The menu can be customized to launch new applications. Adding applications to the context menu saves time!

## Registry Editor
The registry editor can be customized to add and remove programs from the context menu. Press Windows + R and enter `regedit.exe` and enter to launch the Registry Editor.

The context menu settings are saved at the following path.
```
HKEY_CLASSES_ROOT\Directory\Background\shell
```
In this folder, you will notice the programs which appear when you right click within a folder. My directory looks like this:
```
AnacondaPrompt
cmd
Sublime
```
These are the same programs which appear when I right-click in a directory.

### Adding a program to the Context Menu
To add a program to the context menu, you will need to add several keys to the Registry Editor. Within the folder below, add a new key. The key will appear as a folder in the registry editor object explorer. Give the key a descriptive title, for example, my Sublime key is simply named `Sublime`.

`HKEY_CLASSES_ROOT\Directory\Background\shell`

On the right hand side of the registry editor, you can view the key. Right click on the key, and select **Modify**. Change the value of the key to the title you wish displayed in the Context Menu. My Sublime key has a value of `Lanuch Sublime Here`.

Now add a second key, within the first. Name this key `command`. Set the key's value to the location of the program which you wish to launch. My key has a value of `C:\Program Files\Sublime Text 3\sublime_text.exe "%V"`.

Voila! Now you should be able to launch your program from the context menu!

# References
* [Add Anaconda to Right Click Menu](https://gist.github.com/jiewpeng/8ba446acf329b1801bf91db767d179ea)