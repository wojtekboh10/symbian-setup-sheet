# Symbian Setup Sheet

How to configure your Nokia Symbian phone in 2026



## Factory reset

Why? To be sure that any old software on your phone won't casue problems.

- Remember to backup your files from phone memory (files, contacts, calendar, etc.). [Nokia PC Suite](https://archive.org/details/pc-suite-7.1) works well for that.
- Enter number *#73070# to reset your phone. Enter security code (12345 by default). Don't use build in option to factory restet the phone as is does not delete installed applications.
- Power on the phone. Skip first time configuration questions (press "No" few times) until you reach homescreen.

## Unlocking the phone

Why? Because you won't be able to install most softwares until you do this.

- Set date to 7.07.2022
- Install X-plore
- Configure X-plore
    - Menu -> Tools -> Configuration
    - Show ROM drive
    - Show RAM drive
    - Show system folders
- Unpack tmquarantine.zip to C: drive
    - Highlight tmquarantine.zip in X-plore
    - Menu -> File -> Open
    - Highlight tmquarantine
    - Menu -> File -> Extract to
    - Highlight C: drive
    - Menu -> File -> Select
- Install TM Mobile Security
    - Set date to 7.07.2011
    - Install
    - Reset the phone
- Unpack quarantine
    - Open TM Mobile Security
    - Options -> Quarantine List
    - Options -> Mark All
    - Options -> Restore
    - Uninstall TM Mobile Security
- Install ROM Patcher Plus
    - Set date to 7.07.2015
    - Install
    - You can set date to current
- Before you install any software on your hone you need to open ROM Patcher Plus, switch both Install Server RP+ and Open4All RP+ to green (not blue).

## Internet setup

Why? To test if it even works and configure switching to Wi-Fi if available (optional).

- Install Opera Mini web browser
- Install and configure SmartConnect (it could already be be preinstalled, search for icon with antenna and "SC" name)
    - New Group
    - Group name: abc (or anything)
    - On better connection: Stay connected
    - Destination: Internet
    - Next, Done
