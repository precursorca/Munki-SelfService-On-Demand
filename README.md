# Munki-SelfService-On-Demand

> v. 1.0.14  
> April 8, 2020  
> Alex Narvey / Precursor.ca  

![Self Service Screenshot](SelfServices_ScreenShot.png)

Here is a set of utilities that take advantage of Munki’s On Demand nopkg script delivery capability which can be run over and over since they do not actually “Install”.

No warrantee is offered. Neither express nor implied. Use at your own risk.

To use them:

1) Copy the plist files from the pkgsinfo folder into:
munki_repo/pkgsinfo

2) Copy the icons from the icon folder into:
munki_repo/icons
3) Run the make catalog command:
/usr/local/munki/makecatalogs

4) Add the Packages to the “Optional Install” property of the desired Manifest.
I used Munki Admin for this.

5) Save the changes in Munki Admin and then update the client to see your new Utilities in a “SelfService” category.


## The Utilities

### PS-cc_updater
Initiates an update of all installed Creative Cloud apps so that Standard Users can update their Creative Cloud. Requires that an Admin has already packaged and installed a RemoteUpdateManager enabled version of Creative Cloud Desktop App using the Adobe Creative Cloud Packager.
10.9.5 or higher

### PS-clean_var_folders
This utility will clear the contents of the folder /private/var/folders which caches various things that may become corrupt and - among other things - prevent an app from launching. 
This is “big medicine” and should only be undertaken under the advisement of your system administrator. After performing this function you should then choose "Restart" from the Apple menu to start up the computer. It will automatically rebuild anything it needs in /private/var/folders.
10.9.5 or higher

### PS-dns_flush_cache
Flushes the DNS cache on 10.10.4 and higher. 
10.10.4 or higher
It could work for 10.9.5 too but I did not build in the logic to discern the OS and provide the relevant alternative for 10.0.0 -> 10.0.3. (Maybe in version 2.0)

### PS-eject_cd_dvd
Ejects the media from the optical drive for older Macs and Macs with USB SuperDrives. For those times when the digital eject button is just not working.
10.9.5 or higher

### PS-force_empty_trash
Forces the Trash on all mounted volumes to empty, purging locked and "in use" files that standard users normally can't get rid of.
10.9.5 or higher

### PS-enable_ard
Enables Apple Remote Desktop client for all users. (a more complete script with the ability to enable for specific users only is discussed at:
http://scriptingosx.com/2016/01/control-apple-remote-desktop-access-with-munki/.
10.9.5 or higher

### PS-home_permissions
Resets the permissions of the user's Home folder as per Apple Tech Note: https://support.apple.com/en-ca/HT203538. 
10.11 or higher

### PS-hello_world
A harmless test for proof of concept. It throes up a dismissible dialog box box.
10.9.5 or higher

### PS-iOS_screen_share
It prompts the user to plug in their iOS device and then launches QuickTime and starts a Movie Recording to share the screen with a remote support session.
It does not seem possible at this time to use command line to choose the iPhone/iPad camera - the user must do this manually. (I’ve tried over 20 formulations with no success so if anyone knows how please share!)
10.10.5 or higher

### PS-launch_services
Resets launch services to help with problems in window display and open with performance.
10.9.5 or higher.

### PS-library_invisible
Makes the ~/Library invisible again - if a user has made it visible and wants to return it to its natural state.
10.9.5 or higher.

### PS-library_visible
Makes the normally invisible ~/Library folder visible and opens it in the Finder.
10.9.5 or higher.

### PS-log_collect
Gathers all System and Install logs and places an archive into the user's downloads folder.
10.9.5 or higher.

### PS-lpadmin
Adds standard user to lpadmin group to allow for administration of print queues.
10.12.6 or higher.

### PS-mail_optimizer
Vacuums the Mail app database to make it more efficient.
10.9.5 or higher.

### PS-mail_rebuilder
Deletes the Mail app Envelope and causes Mail to resync with the server and pull down all the messages again. Can take a long time depending on amount of mail and internet speed.
10.12.6 or higher.

### PS-malware_scan
Initiates a malware scan utilizing Malwarebytes for Mac 3.0 or higher provided it is properly installed and access privileges are granted - see included document "Munki and osascript Notes"
10.12.6 or higher.

### PS-purge
Runs the "purge" command to free up memory without requiring a restart. It may aid in performance. Modern versions of macOS are quite good at managing memory on their own so this command may only result in the cached files being cleaned out.
10.9.5 or higher.

### PS-speedtest
Test your internet speed (upload and download) using speedtest.cli and pops up the results in a Safari window. Flash is NOT required.
10.9.5 or higher.

### PS-recovery_diagnstic_reboot
Lets a standard user reboot to Recovery mode or Hardware Diagnostic mode based on Rich Trouton's script for Jamf pro.
https://derflounder.wordpress.com/2020/03/28/booting-to-macos-recovery-or-diagnostics-via-jamf-pros-self-service/#more-10856
10.12.0 or higher.

### PS-spotlight_rebuilder
Deletes the Spotlight index (for both internal and external disks). Performance WILL be impacted during the rebuild.
10.9.5 or higher.

### PS-startup_chime
Enable the Startup Chime on T1 and T2 chip Macs from 2016 on.
10.13.0 or higher.

### PS-user_font_cache
Deletes the active users font cache.
10.9.5 or higher.

### PS-view_console_as_admin
Lets a standard user view the System log with the /Applications/Utilities/Console app.
10.9.5 or higher.

## Updates

* March 6, 2016 Version 1.0 
* March 7, 2016 Version 1.0.1 Added logic to the DNS Flush Cache to handle 10.9.5 and up by dealing with the special cases of 10.0.0-10.0.3.
* March 11, 2016 Version 1.0.2 Added a Speedteest module and touched up the PS-mail-rebuilder icon.
* April 2, 2016 Version 1.0.3 Added a Log Collection module. Fixed category of PS-iOS_screen_share. Reduced size of all icons to improve performance.
* August 16, 2016 Version 1.0.4 Added an Adobe Creative Cloud updater (for those admins who have packaged and installed a RemoteUpdateManager enabled CC Desktop App).
* September 3, 2016 Version 1.0.5 Added a module to reset the permissions of the users Home folder.
* October 6, 2016 Version 1.0.6 Added macOS Sierra compatibility to PS-mail_optimizer and PS-mail_rebuilder.
* October 9, 2016 Version 1.0.7 Added Oliver Hetzner's AppleScript and other mods to PS-cc_udpater. Added PS-force_empty_trash, PS-library_visible, PS-library_invisible, and PS-eject_cd_dvd. Edited comments in PS-mail_optimizer and PS-mail_rebuilder
* November 29, 2016 Version 1.0.8 Added PS-clean_var_folders to clean up corrupted cache files that may prevent apps from launching - among other things.
* January 4, 2017 Version 1.0.9 Added PS-purge and PS-view_console_as_admin. Updated PS-clean_var_folders to attempt to remove contents of zz folder.
* April 5, 2017 Version 1.0.10 Added PS-enable_ard to enable the Apple Remote Desktop client (more info at http://scriptingosx.com/2016/01/control-apple-remote-desktop-access-with-munki/).
* October 16, 2017 Version 1.0.11 Added PS-malware_scan to initiate a Malwarebytes for Mac 3.0 scan. (May require some other manipulations. See included "Munki and osascript Notes").
* February 23, 2020 Version 1.0.12 Added PS-startup_chime to enable the missing Startup Chime on Macs from 2016 on with T1 or T2 chips.
* February 26, 2020 Version 1.0.13 Added PS-lpadmin to put standard users into lpadmin print group to allow for administration of print queues. Updated PS-Mail_Rebuilder and PS Mail_Optimizer to work for Sierra up to Catalina
* April 8, 2020 Version 1.0.14 Added PS-Recovery_Diagnostic_Reboot based on Rich Trouton's (Der Flouder's) script.

## Contributors
* Alex Narvey
* Oliver Hertzner

—
Alex Narvey
precursor.ca
