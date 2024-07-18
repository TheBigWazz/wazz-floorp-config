# wazz-floorp-config
Config files and set up instructions for my Floorp set up with auto-hiding Nav-bar and toggels for side bars to enable Full Window Browsing.

***This has only been tested on Windows 11. Your results on other systems may vary.***

https://github.com/user-attachments/assets/f2c3122f-9f1e-478e-9b18-db5b436727e4

<br/>
<br/>

# Table of Contents
[Installing](https://github.com/TheBigWazz/wazz-floorp-config/edit/main/README.md#installing)
* [Extension Set Up](https://github.com/TheBigWazz/wazz-floorp-config/edit/main/README.md#extension-set-up)
* [Toolbar Set Up](https://github.com/TheBigWazz/wazz-floorp-config/edit/main/README.md#toolbar-set-up)
* [Floorp Settings Set Up](https://github.com/TheBigWazz/wazz-floorp-config/edit/main/README.md#floor-settings-set-up)
* [CSS Set Up](https://github.com/TheBigWazz/wazz-floorp-config/edit/main/README.md#css-set-up)

[CSS Tips]()

[Syncing Floorp Customized Profiles via Cloud services](https://github.com/TheBigWazz/wazz-floorp-config/edit/main/README.md#syncing-floorp-customized-profiles-via-cloud-services)

[Help](https://github.com/TheBigWazz/wazz-floorp-config/edit/main/README.md#help)

[Contributions](https://github.com/TheBigWazz/wazz-floorp-config/edit/main/README.md#contributions)

[Credits](https://github.com/TheBigWazz/wazz-floorp-config/edit/main/README.md#credits)

# Installing
There are 4 main parts to installing this Floorp customization.

* Installing and configuring Extensions
* Arrannging the Toolbar
* Applying Floorp settings
* Applying CSS code

I'm also including a section on syncing your Floorp customized profiles across devices via cloud services. 

*This is optional. The customization will still work without syncing a customized profile.*

<br/>

## 1. Extension Set Up
### Install the following extensions from [https://addons.mozilla.org](https://addons.mozilla.org)
* [Firefox Color](https://addons.mozilla.org/en-US/firefox/addon/firefox-color/?utm_source=addons.mozilla.org&utm_medium=referral&utm_content=search) (For theme coloring)
  - For best theme consistancy, match ```Toolbar Color``` and ```Background Color``` to the same value

* [Sidebery](https://addons.mozilla.org/en-US/firefox/addon/sidebery/) (For vertical tab bar)
  - Turn off: ```Bookmarks sub panel``` and ```History sub panel``` under ***Navigation***
  - Turn on: ```Prevent pinned tabs from unloading``` under ***Pinned Tabs***
  - Turn on: ```Show tab preview on mouse hover``` under ***Tab Preview***
  - Set ```Animation Speed``` to ```Slow``` under ***Appearance***
  - Set ```Switch tab with scroll wheel``` to ```in panel``` under ***Mouse***
  - Under ***Sync*** set all four Save options to ```on```
  - Under ***Keybindings*** set a custom shortcut for ```Open/Close sidebar panel``` (*To toggle the vertical tab sidebar*)

* [Bonjourr](https://addons.mozilla.org/en-US/firefox/addon/bonjourr-startpage/) (New tab page)
  - Configure to your liking

<br/>

## 2. Toolbar Set Up
### Pin these buttons to the toolbar from left to right in this order:
* ```Firefox Profile button```
* ```Back button```
* ```Forward button```
* ```Reload button```
* 5 ```Flexible Space``` blocks
* ```URL Bar```
* 4 ```Flexible Space``` blocks
* ```Downloads```
  - Right click and unselect: ```Hide button when empty```
* ```Profile Manager```

<br/>

## 3. Floorp Settings Set Up
### The following settings are under the ***Design*** section in the Settings of Floorp
* Select: ```Firefox Photon・Lepton UI```
  - Turn these Lepton settings ```On```:
    - ```Automatically hide tabs```
    - ```Automatically hide Toolbar```
    - ```Hide Tab Bar```
    - ```Hide Sidebar Headers```
    - ```Hide Bookmarks Bar icons```
    - ```Hide Bookmarks Bar labels```
    - ```Enable Lepton's context menu icons```
    - ```Center text in the Address Bar```
### These settings are under ***Browser Manager Sidebar***
* Set these settings to ```On```:
  - ```Show the Browser Manager Sidebar```
  - ```Display the Browser Manager Sidebar on the right```
* Set ```Global Web Panels width``` to: ```300```
### Keyboard Shortcuts
* Set shortcuts for:
  - ```Open a new tab```
  - ```Close the current tab```
  - ```Toggle Navigation Panel```
    - You can choose to auto-hide the Nav-bar from Lepton UI settings, or toggle it with a Keyboard Shortcut
  - ```floorp-show-bsm``` (*To hide the Browser Manager Sidebar*)
  - Set shortcuts for all 3 ```Split View Actions```
<br/>

## 4. CSS Set Up
#### Download ```userChrome.css``` and ```sideberyStyle.txt``` from the file list above
### Enable Custom User Styles in Floorp
  - Go to ```about:config``` and accept the warning
  - Paste ```toolkit.legacyUserProfileCustomizations.stylesheets``` into the search bar
  - Set the value to ```true``` by clicking the button on the right
### Locate your Root Directory and make the ```chrome``` folder
  - Go to ```about:profiles``` and identify which profile is in use
  - Click the ```Open Folder``` button in the row labeled ```Root Directory```
  - Create a new folder named: ```chrome``` in the folder that opens
### Add the custom CSS files
  - Place ```userChrome.css``` in the ```chrome``` folder
  - Open Sidebery settings
  - Click ```Styles Editor```
  - Paste the contents of ```sideberyStyle.txt``` into the text field on the right hand side

<br/>

## CSS Tips
### These changes are made in the ```userChrome.css``` file
#### To enable vertical tabs expanding when hovered, adjust the ```hover-width``` with this line:
```css
--uc-sidebar-hover-width: 75px;
```
#### To adjust the hide delay, change this line:
```css
--uc-autohide-sidebar-delay: 600ms;
```
#### To enable a border between the vertical tabs and the browser page, set the ```border-inline``` value with this line:
```css
border-inline: 0px solid rgb(80,80,80);
```
### These changes are made in the ```Sidebery -> Settings -> Styles Editor``` file
#### To enable Sidebery tab toolbar, remove or comment out this line:
```css
.NavigationBar{ display: none }
```
#### Adjust the indent depth on child tabs in tree:
```css
#root.root {--tabs-indent: 10px;}
```
#### Adjust the distance between the tabs and the Nav-bar:
```css
#root.root {padding-top: 0px;}
```

# Syncing Floorp Customized Profiles via Cloud services

### This is a general concept that should work with cloud services that can mount your storage as a drive. 

Popular services that should work:
* Google Drive
* Microsoft OneDrive
* Dropbox
* Mega

#### Step One - Set up Floorp Folders
* Install and set up your choice of cloud storage
* Create a new folder dedicated to Floorp on your cloud storage
* Create a subfolder for your **Customized Profile** in the new Floorp folder
* Copy the contents of your **Root Directory folder** into your new **Customized Profile Folder**
#### Step Two - Configure ```.ini``` files
* Go to ```about:profiles``` and open your **Root Directory folder**
* Navigate up one folder level and find ```installs.ini``` and ```profiles.ini```
* Copy the ```.ini``` files into your **Floorp folder** on your cloud storage
* Edit ```profiles.ini```
```css
[Profile0]
Name=Your profile name
IsRelative=1
Path="P:\ath\to\your\customized\profile\folder"
Default=1
```

* Restart Floorp
* Go to ```about:profiles``` to verify that your Root directory has been changed to the location on your cloud storage
#### Step Three - Use cloud Root Directory on different machine
* Follow **Step Two** again on the new machine to set your **Root Directory folder** to your cloud storage location

This should keep your customizations in sync across devices. 

Make sure your Cloud Storage settings are set to sync any time there's a file change.

<br/>

# Help
Feel free to [open an issue](https://github.com/TheBigWazz/wazz-floorp-config/issues) if you find any bugs. 

This is a customization I made in my free time, so responses to issues may be sporadic.

<br/>

## Contributions
Feel free to fork, make adjustments, and submit pull requests for new features or fixes. 

### Current known issues
- [ ] Right side toolbar buttons shift with window width changes

<br/>

## Credits
Customizations: [TheBigWazz](https://github.com/TheBigWazz)

Sidebery Auto-hide function: [MrOtherGuy](https://github.com/MrOtherGuy/firefox-csshacks/blob/master/chrome/autohide_sidebar.css)

Floorp [Projects Repository](https://github.com/Floorp-Projects)

[https://floorp.app/](https://floorp.app/en)


