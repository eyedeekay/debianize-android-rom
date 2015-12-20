Android ROM Debianizer
======================

Script to automate this process: http://whiteboard.ping.se/Android/Debian and
turn it into a flashable file. See the TODO LIST below for a more detailed
explanation of what it actually does.

WARNING:
========
This is a highly perilous, somewhat difficult to automate process which involves
modifying parts of your system which may be essential to it's operation, and
could also potentially modify parts which would be essential to recovering your
system. There's no way in hell your local Sprint store is going to know what to
do with this if anything goes wrong. You probably don't want to tell them, to be
perfectly honest. It's not illegal or even a TOU violation that they could
really do anything to you over, but what I'm trying to say is that like always,
if you want to be in charge of your hardware(which you should) you're pretty
much on your own. I mean, I'll do what I can, and there's a huge community
around Android ROM modification, and ultimately you're better off with them than
you are with your phone company. Especially if you're in the United States.
US Phone companies are terrible.

TODO LIST:
----------

  1. Format SD Card(Works)
    * For now, you select the SD card you want to use to create it manually, and
      it does the rest automatically.
  2. Create modified initramfs(Works)
    * This step will need some options and confirmation steps when I make it so
      that it will work with the system on a running phone.
  3. Generate Debian Root FS(Works, because it's entirely standard)
  4. Generate new Android Root FS(Works but is probably fragile)
    1. During this step the linux kernel source package is retrieved in the
       current directory so that the scripts can be used.
    2. Busybox is also downloaded and built from the latest stable Debian source
       package.
  5. Setup init scripts(Untested)
  6. Install the modified boot image to the phone(Untested)
    * This step will be optional in the final version.
  7. Configure users and groups(Unimplemented)
    * This creates a normal user in the debian system, configures sudo, then
      adds the debian user to the appropriate Android groups to control the
      system. It should also make any necessary modification to sudo to give it
      the same permissions as root on the Android system.
  8. Configure the desktop environment and the VNC server on Debian system.
  9. De-Androidize Android system. Remove everything except the services
     required to drive the Android hardware and connect the VNC client to the
     Debian system. Lastly, automatically start the VNC client pointed at the
     Debian VNC service.
  10. Create a flashable zip package(This will have to be broken down into many
     more steps. It'll be done last.)

