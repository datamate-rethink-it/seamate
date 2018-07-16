Seamate is an add-on for [Seahub](https://github.com/haiwen/seahub), the web interface of the file syncing and sharing software [Seafile](https://github.com/haiwen/seafile), that allows the easy modification of Seahub‘s look. 

It integrates in the global settings of Seahub and requires no coding knowledge whatsoever. Modifying Seahub to meet your personal / corporate standards is no more than changing a few field values in the familiar Seahub settings.

## Technical implementation
Seamate expands the Branding section in the settings menu in Seahub's admin panel. Seamate writes the customized field values in the Seahub database. Modified HTML templates call these variables every time a Seahub page is loaded.

The implementation approach entails the following consequences:
* ENABLE_SETTINGS_VIA_WEB = True in seahub_settings.py: Unless web settings are enabled, custom changes must be made directly in seahub-settings.py, but Seamate's CSS classes (see below) can be used.
* Seamate integrates on a low level: Changes made in custom HTML or CSS files overwrite changes made in Seamate.
* Seamate can't handle Seafile upgrades: When you upgrade Seafile, Seahub loads a fresh set of HTML templates and the changes do not apply any more.

Seahub employs several hundred CSS classes. With Seamate, some 35 can be modified right within Seahub. Why "only" this small fraction? Things get unwieldy quickly! We believe -- till proven wrong -- that the set of configurable parameters meets the demand of the large majority of Seamate users. For all other users, more classes would mean more headache. Additionally, all those that wish to take the customization of Seahub even further can still import separate custom HTML/CSS files or make use of the custom CSS in the Seahub settings.

## Use
Open Seahub's admin panel, click on Settings and scroll down to the Branding section. 

Seahub-wide (global) settings can be set and individual changes made to Seahub's five central UI elements (login, top bar, navigation sidebar, main, and popups). Whenever possible, colorpickers or dropdown lists are provided for ease of use.

In Seamate's *global settings*, four CSS classes can be manipulated (the class' name in brackets):
* Font                          [GLOBAL\_FONT]
* Border color                  [GLOBAL\_BORDER\_COLOR]
* Border radius                 [GLOBAL\_BORDER\_RADIUS]
* Border thickness              [GLOBAL\_BORDER\_THICKNESS]

For each of Seahub's *five central UI elements*, the following six CSS classes can be modified using colorpickers (the class' name in brackets):
* Background color              [...\_BACKGROUND]
* Text default color            [...\_TEXT]
* Text link color               [...\_LINK]
* Text hover color              [...\_LINK\_HOVER]
* Icon and button color         [...\_ICBU]
* Icon and button hover color   [...\_ICBU_HOVER]

Additionally, the following two elements can be modified in the main element (the class' name in brackets):
* Border color                  [MAIN_TABLE_BORDER_COLOR]
* Border thickness              [MAIN_TABLE_BORDER_THICKNESS]

The custom CSS field in the Branding box can be used to manipulate any other CSS classes not addressed by Seamate. Any specification must be made in [common CSS syntax](https://www.w3schools.com/css/css_syntax.asp). 

## Installation

### FTP
0. Safety first: Go to the current Seafile Server folder ~/seafile-server-latest/ and backup the seahub folder (~200MB)
1. Download Seamate and unzip to find several folders
2. Copy the content of the folder which fits your Seafile version into ~/seafile-server-latest/ - some new files are created, some overwritten (disregard the other folders)
3. Restart seahub

### Bash
...

## Change log
### Seamate 1.0 (DATE)
Initial release of Seamate

Release statement in the [Seafile Forum](...)


## Compatability list
Seamate can be used with Seafile's community as well as professional server. 

As a rule, a Seamate version that works with the community server also works nicely with the professional server and vice versa. Since the CSS classes for the two servers partially vary, there may be exceptions. For more details, see compatability tables below which shows known working combinations.

### Seafile Server Community Edition 

| Seafile 6.3.2     | Seafile 6.3.1     | Seafile 6.3.0       | Seafile 6.2.x       | Seafile 6.1.x       | Seafile 5.x       |
| ----              | -----             | ----                | ---                 | ---                 | ---               |
| Seamate 1.0       | Seamate 1.0       | Seamate 1.0         | untested            | untested            | untested          |     

### Seafile Server Professional Edition

| Seafile 6.3.0     | Seafile 6.2.x     | Seafile 6.1.x       | Seafile 5.x         |
| ----              | -----             | ----                | ---                 |
| Seamate 1.0       | untested          | untested            | untested            |      

## Outlook
Seamate is a first step, but there are many ideas for extensions:
* Presets
* Multiple login designs
* Email template customization
* Column selection in the main element
* Auto refresh after modification

If you want to share your favorite skin for Seafile, make it available and it could be one of the presets. If you want to help developing any other additions, come forward!
