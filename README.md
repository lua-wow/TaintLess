# TaintLess

The original repository can be found at [**Townlong Taintless**](https://www.townlong-yak.com/addons/taintless)

I'm hosting the code in github so I can track changes by release and to enbaled me to embed it into others addons.

## Description

TaintLess works around a number of common taint issues in FrameXML, eliminating some occurrences of "Interface action failed because of an AddOn" and "$AddOn has been blocked from an action only available to the Blizzard UI" error messages.

You may install this as a stand-alone addon, or include the TaintLess.xml file in your own addons (no code changes are required; just add the .xml file to your .toc). You may benefit from this if your addon uses UIDropDownMenu, InterfaceOptionsFrame, or parts of FrameXML that interact with these APIs.

TaintLess mitigates these issues:

- UIDropDownMenu_Refresh accesses uninitialized buttons
- UIDropDownMenu displayMode taints dropdown initialization
- Insecure updates taint the Objective Tracker
- Edit Mode systems tainted by dropdown misuse
- CUF taint via dropdowns (Classic Wrath)

## Usage

### Embedding As Git Submodule

```bash
# add this repository as submodule inside your addon
git submodule add --branch master https://github.com/lua-wow/TaintLess.git ./libs/Taintless

# initialize submodule and download it
git submodule init --update
```

### Add the `TaintLess.xml` to your addon `.toc` file

```toc
## Interface: 100200

TaintLess.xml
```

### Update TainLess

To update a submodule you just need to pull from git

```bash
cd ./libs/TaintLess && git pull
```
