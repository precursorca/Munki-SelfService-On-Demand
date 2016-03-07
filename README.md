# Munki-SelfService-On-Demand
No warrantee is offered. Neither express nor implied. Use at your own risk.

To use them:

1) Copy the plist files from the pkgsinfo folder into:
munki_repo/pkgsinfo

2) Copy the icons from the icon folder into:
munki_repo/icons
3) Run the make catalog command:
usr/local/munki/makecatalog

4) Add the Packages to the “Optional Install” property of the desired Manifest.
I used Munki Admin for this.

5) Save the changes in Munki Admin and then update the client to see your new Utilities in a “SelfService” category.

—
The Utilities

￼

PS-dns_flush_cache
Flushes the DNS cache on 10.10.4 and higher. 
10.10.4 or higher
It could work for 10.9.5 too but I did not build in the logic to discern the OS and provide the relevant alternative for 10.0.0 -> 10.0.3. (Maybe in version 2.0)

PS-hello_world
A harmless test for proof of concept. It throes up a dismissible dialog box box.
10.9.5 or higher

PS-iOS_screen_share
It prompts the user to plug in their iOS device and then launches QuickTime and starts a Movie Recording to share the screen with a remote support session.
It does not seem possible at this time to use command line to choose the iPhone/iPad camera - the user must do this manually. (I’ve tried over 20 formulations with no success so if anyone knows how please share!)
10.10.5 or higher

PS-launch_services
Resets launch services to help with problems in window display and open with performance.
10.9.5 or higher.

PS-mail_optimizer
Vacuums the Mail app database to make it more efficient.
10.9.5 or higher.

PS-mail_rebuilder
Deletes the Mail app Envelope and causes Mail to resync with the server and pull down all the messages again. Can take a long time depending on amount of mail and internet speed.
10.9.5 or higher.

PS-spotlight_rebuilder
Deletes the Spotlight index (for both internal and external disks). Performance WILL be impacted during the rebuild.
10.9.5 or higher.

PS-user_font_cache
Deletes the active users font cache.
10.9.5 or higher.


—
Alex Narvey
precursor.ca
