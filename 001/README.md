### Why this repo
This repository contain the configurated Marlin firmware, configuration and other usefull stuff for the 3D printer it refers to (if you found the link to this page looking the prints at startup of the machine or in the "Credits and Info" section of the display menu, you are in the right place).


### Folders in this repo
- In the `Marlin-2.0.x_firmware_TMC2130` folder you can find the last configured firmware, but you can also search in commit history to match the tate that you see in the prints at startup (most likely it will be the same of the last commit).

- In the `Binary_and_settings_backup` folder you can find some backups of the binary code uploaded on the board, dumped from the flash memory of the Arduino using the command `avrdude -v -c stk500v2 -p m2560 -P /dev/ttyACM0 -b 115200 -U flash:r:File.bin:i` where `/dev/ttyACM0` is the serial port name (replace with yours), 115200 is the baud rate (there are a few standard values, try 115200, 250000 or 9600) and `File.bin` is the output filename.
You can restore those binary files uploading them on the board with the command `avrdude -v -c stk500v2 -p m2560 -P /dev/ttyACM0 -b 115200 -U flash:w:File.bin:i -D` (same parameters as before).
You can also find the dump of the EEPROM content that you can restore using [this](https://github.com/francesco-scar/arduino-EEPROM-backup_restore) program and the startup prints output of the values of the parameters of the printer before I uploaded the new firmware.

- In the `BLTouch_probe_support` folder you can find the FreeCAD and STL files of the 3D printed support of the BLTousch probe installed on the extruder. If it breaks you can print it again using the STL file, or you can edit it using the FreeCAD project files.

- The `Slic3r_config.ini` file is the [Slic3r](https://slic3r.org/) slicing configuration and parameter file used for this printer (and 1.75 mm filament).
