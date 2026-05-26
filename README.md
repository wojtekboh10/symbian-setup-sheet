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

## Internet connection setup (To validate)

Why? To test if it even works and configure switching to Wi-Fi if available (optional).

- Install Opera Mini web browser
- Install and configure SmartConnect (it could already be be preinstalled, search for icon with antenna and "SC" name)
    - New Group
    - Group name: abc (or anything)
    - On better connection: Stay connected
    - Destination: Internet
    - Next, Done
- Add connections in options
- Test Opera Mini in some basic pages (google.com, wikipedia.org)

## Internet fixes

Some fixes are required for centain softwares to work. You can install them all, or test if there are necessery for you.
- Networking Improvements
    - Required at least for email configuration
    - Export networking_improvements.zip to C: drive while the phone is unlocked
- TLS 1.2 upgrade
    - Required to speed up GPS localisation
    - Install MBedTLS.sis
    - Extract ssl.zip to C: drive while the phone is unlocked
- CACerts update
    - Optional, it may help in some cases
    - Extract CACerts.zip to C: drive while the phone is unlocked

## Email setup

There are 2 options. One with profimail program, second with build in email software. Here is the second option. I menaged it to work with Gmail and Wirtualna Polska (wp) accounts. Tried with Outlook but did not succeed.

- Installed networking_improvements.zip are required for email.
- Enable any kind of Two Factor Authentication (2FA) in your Gmail account (do not skip this point)
- Generate password for application
- Configure new email account in your phone:
    - Enter email, password (enter your password for application, not the main one)
    - Type: IMAP
    - Incomming messages server: imap.gmail.com
    - Incomming messages port: default (or 993)
    - Encryption: yes (SSL/TLS)
    - Outgoing messages server: smtp.gmail.com
    - Outgoing messages port: default (or 465)
    - Encryption: yes (SSL/TLS)
    - Confirm configuration
- Account should be added and working at this moment
- You can set default internet connection as abc to use Wi-Fi if possible or packet data if outside.
- For Wirtualna Polska (wp) configuration:
    - Enable 2FA and generate passord for application
    - Incomming messages server: imap.wp.pl
    - Outgoing messages server: smtp.wp.pl
    - Rest is the same as in Gmail account
