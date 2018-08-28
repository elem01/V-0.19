= How to compile the code on Windows =

1. Install SDCC (https://sourceforge.net/projects/sdcc/files/snapshot_builds/x86_64-w64-mingw32-setup/) version 3.7 or higher. Make sure to add it to your PATH (option in one of the last screens of the installer... )
2. Git clone the project or download zip file: https://github.com/OpenSource-EBike-firmware/TongSheng_TSDZ2_motor_controller_firmware (make sure to get the master branch)
3. Use any text editor to make the desired firmware changes.
4. Double-click Start_Compiling.bat to compile the firmware. The resulting main.ihx can be programmed in the controller.