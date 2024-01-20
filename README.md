# TaintLess

This code is not of my author. The original code can be found at [Townlong Taintless](https://www.townlong-yak.com/addons/taintless)

I'm host it in a repository to help me track changes and to easy embed it in other addons.

## Description

TaintLess works around a number of common taint issues in FrameXML, eliminating some occurrences of "Interface action failed because of an AddOn" and "$AddOn has been blocked from an action only available to the Blizzard UI" error messages.

You may install this as a stand-alone addon, or include the TaintLess.xml file in your own addons (no code changes are required; just add the .xml file to your .toc). You may benefit from this if your addon uses UIDropDownMenu, InterfaceOptionsFrame, or parts of FrameXML that interact with these APIs.

TaintLess mitigates these issues:

- UIDropDownMenu_Refresh accesses uninitialized buttons
- UIDropDownMenu displayMode taints dropdown initialization
- Insecure updates taint the Objective Tracker
- Edit Mode systems tainted by dropdown misuse
- CUF taint via dropdowns (Classic Wrath)

## Embedding

### Add TaintLess as a submodule

```bash
# add this repository as submodule inside your addon
git submodule add --branch master https://github.com/pedrozc90/taintless ./libs/Taintless

# initialize submodule and download it
git submodule init --update
```

### Add the `TaintLess.xml` to your addon `.toc` file

```toc
## Interface: 100200

TaintLess.xml
```

### Update TainLess

```bash
cd ./libs/TaintLess

# you can git pull changes that are made in my repository
git pull
```
