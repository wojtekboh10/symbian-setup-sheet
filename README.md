# Symbian Setup Sheet

## How to configure your Nokia Symbian phone in 2026.

Here is some information I would like to know before I started using [Nokia E52](https://en.wikipedia.org/wiki/Nokia_E52/E55) as my daily device.
It's just a cheat sheet, not a foolproof, step by step instruction.
Let me know in [issues](https://github.com/wojtekboh10/symbian-setup-sheet/issues) if something is confusing or wrong.
I'll maybe add it to this sheet (or only answer with message).
All described things were tested on my phone in polish language, so there may be some translation errors (sorry!).

## What can you achieve?

| What         | Configuration | External Software | Networking improvements | TLS Upgrade     |
|--------------|---------------|-------------------|-------------------------|-----------------|
| Phone calls  | -             | -                 | -                       | -               |
| SMS          | -             | -                 | -                       | -               |
| MMS          | **Required**  | -                 | -                       | -               |
| Email        | **Required**  | [Optional](https://www.lonelycatgames.com/apps/profimail-symbian)          | **Recommended**         | **Recommended** |
| Web browsing | -             | [**Required**](http://www.m.opera.com/?act=opts&vid=0x9c7f9c859a2dd90a&ua=NokiaE90)      | -                       | Optional        |
| Maps         | -             | [**Required**](https://github.com/artem78/s60-maps)      | -                       | Optional        |
| Basic GPS    | -             | -                 | -                       | -               |
| Assisted GPS | **Required**  | -                 | -                       | **Required**    |

## Factory reset

Why? To be sure that any old software on your phone won't cause problems.

- Remember to back up your files from phone memory (files, contacts, calendar, etc.). [Nokia PC Suite](https://archive.org/details/pc-suite-7.1) works well for that.
- Enter number *#7370# to reset your phone. Enter security code (12345 by default). Don't use build in option to factory reset the phone as it does not delete installed applications.
- Power on the phone. Skip first time configuration questions (press "No" few times) until you reach home screen.

## Unlocking the phone

Why? Because you won't be able to install most software until you do this.

- Set date to 7.07.2022
- Install [X-plore](https://www.lonelycatgames.com/apps/xplore-symbian)
- Configure X-plore
    - Menu -> Tools -> Configuration
    - Show ROM drive
    - Show RAM drive
    - Show system folders
- Unpack [tmquarantine.zip](https://mega.nz/folder/jH4QAL5J#jUQJTDDSmU-5z_GJBCMJAg/folder/uGw2nZqR) to C: drive
    - Highlight tmquarantine.zip in X-plore
    - Menu -> File -> Open
    - Highlight tmquarantine
    - Menu -> File -> Extract to
    - Highlight C: drive
    - Menu -> File -> Select
- Install [TM Mobile Security](https://mega.nz/folder/jH4QAL5J#jUQJTDDSmU-5z_GJBCMJAg/folder/uGw2nZqR)
    - Set date to 7.07.2011
    - Install
    - Reset the phone
- Unpack quarantine
    - Open TM Mobile Security
    - Options -> Quarantine List
    - Options -> Mark All
    - Options -> Restore
    - Uninstall TM Mobile Security
- Install [ROM Patcher Plus](https://mega.nz/folder/jH4QAL5J#jUQJTDDSmU-5z_GJBCMJAg/folder/uGw2nZqR)
    - Set date to 7.07.2015
    - Install
    - You can set date to current
- Before you install any software on your phone you need to open ROM Patcher Plus, switch both Install Server RP+ and Open4All RP+ to green (not blue)

Alternative instructions: [text](https://lpcwiki.miraheze.org/wiki/Jailbreaking_S60_devices), [video](https://www.youtube.com/watch?v=ewrOsBmLaLM)

## Internet connection setup (To validate)

Why? To test if it even works and configure switching to Wi-Fi if available (optional).

- Install [Opera Mini](http://www.m.opera.com/?act=opts&vid=0x9c7f9c859a2dd90a&ua=NokiaE90) web browser
- Control Panel -> Settings -> Connection -> Target Networks -> Internet
- Add packet data to Internet group
- Test Opera Mini in some basic pages (google.com, wikipedia.org)

To configure automatic switch to Wi-fi if available:
- Add Wi-fi connections
- Install and configure [SmartConnect](https://web.archive.org/web/20100813202340/http://www.birdstep.com/upload/Enterprise/smartconnect/Birdstep_SmartConnect_1.3.55-tct_sign.zip) (it could already be preinstalled, search for icon with antenna and "SC" name)
    - New Group
    - Group name: abc (or anything)
    - On better connection: Stay connected
    - Destination: Internet
    - Next, Select All, Done
    - Change priority if needed
    - Click Back
    - Options on abc -> Advanced -> Settings -> Disable notification level and prompting on new connection


## Internet fixes

Some fixes are required for certain software to work. You can install them all, or test if they are necessary for you.
- [Networking Improvements](https://github.com/mrRosset/Symbian-Archive/files/7231059/CACerts-2021-update.zip)
    - Required at least for email configuration
    - Export networking_improvements.zip to C: drive while the phone is unlocked
- [TLS 1.2](https://nnproject.cc/tls/) upgrade
    - Required to speed up GPS localization
    - Install MBedTLS.sis (Select to install TLS 1.2 only, deselect CA Upgrade)
    - Extract ssl.zip to C: drive while the phone is unlocked
- CACerts update
    - Optional, it may help in some cases (I think it's inside TLS upgrade as well.)
    - Extract [CACerts.zip](https://github.com/mrRosset/Symbian-Archive/files/7231059/CACerts-2021-update.zip) to C: drive while the phone is unlocked

## Email setup

There are 2 options. One with profimail program, second with build-in email software. Here is the second option. I managed it to work with Gmail and Wirtualna Polska (wp) accounts. Tried with Outlook but failed.

- Installed networking_improvements.zip are required for email.
- Enable any kind of Two Factor Authentication (2FA) in your Gmail account (do not skip this point)
- Generate password for application
- Configure new email account in your phone:
    - Enter email, password (enter your password for application, not the main one)
    - Type: IMAP
    - Incoming messages server: imap.gmail.com
    - Incoming messages port: default (or 993)
    - Encryption: yes (SSL/TLS)
    - Outgoing messages server: smtp.gmail.com
    - Outgoing messages port: default (or 465)
    - Encryption: yes (SSL/TLS)
    - Confirm configuration
- Account should be added and working at this moment
- You can set default internet connection as abc to use Wi-Fi if possible or packet data if outside.
- For Wirtualna Polska (wp) configuration:
    - Enable 2FA and generate password for application
    - Incoming messages server: imap.wp.pl
    - Outgoing messages server: smtp.wp.pl
    - Rest is the same as in Gmail account

## MMS setup

Tested on T-Mobile in Poland. (In fact [T-Mobile configuration](https://www.t-mobile.pl/informacje-i-pomoc/pomoc-techniczna/konfiguracja-mms) didn't work, I had to add 8080 port number.)
If you use different provider, check its server configuration.

- Create access point:
    - Settings -> Connection -> Packet data -> Access point -> "MMS"
- In Target Networks add MMS access point in MMS group
- Set MMS access point settings:
    - MMS
    - Packet data
    - mms
    - mms
    - No
    - Leave empty
    - Normal
    - http://mms/servlets/mms
    - Automatic
    - Options -> Advanced settings
        - IPv4
        - Automatic
        - Automatic
        - 213.158.194.226
        - 8080
- Main menu -> Messages -> Options -> Settings -> MMS -> Access Point in use -> MMS

## Minor things

- Change theme to dark one with Darkmod.sis
- Disable camera sounds with QuietCam.sis

## Maps setup

- [Here](https://github.com/artem78/s60-maps) you can find awesome Open Street Maps for Symbian.

## Increase GPS startup speed

- Disable all location sources expect unassisted GPS
- Open maps to enable GPS in your phone and perform cold start
- Enable all other location sources
- Set location server to supl.grapheneos.org (or supl.google.com)
- Longer explanation can be found [here](https://github.com/mahomaps/mm-v1)

## Some random usefull links

- [Email configuration](https://www.reddit.com/r/symbian/comments/12na59p/making_gmail_work_in_nokia_e72_native_email_client/)
- [Email configuration](https://www.youtube.com/watch?v=INwZxfjluK8)
- [Symbian apps](https://phoneky.co/applications/?q=calendar)
- [Patches (polish)](https://www.mobilneforum.pl/archive/index.php/f-7.html)
- [Python for Symbian](https://lpcwiki.miraheze.org/wiki/Developing_for_old_phones/PyS60)
- [Python for Symbian](https://web.archive.org/web/20081219051632/http://www.mobilenin.com/pys60/menu.htm)
- [Fix for missing SMS notifications (not tested yet)](https://wade.be/no-message-alerts-problem-on-nokia-n95/)


Huge thanks for [Internet Archive](https://archive.org/) and [Nokia Hacking](https://nokiahacking.pl) for existing.

wojtekboh10