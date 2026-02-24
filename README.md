The OnBoard Drone Synth is a DIY synthesizer that enables the performance of up to 5 independent voices. Each voice is monophonic with controls over pitch, release time, detune, timbre, pitch wander, vibrato, pulsing amplitude variation, and volume level. The stereo output from all voices is passed through overdrive, filter, two independent delays with cross modulation, and reverb. Sonically, the Drone Synth embraces the post-digital and somewhat gritty aesthetic of DIY audio culture.

This site contains support files for users of the Drone Synth.

The PDF is a user guide for Drone Synth owners.

The "esp32.esp32.lolin_s3_mini" folder contains files for the latest software update. Below are some steps for updating the software. Follow the following steps to install the esptool program to be run at the terminal.

To install the esptool.py on a Mac, use the Terminal-based Homebrew package manager - install instructions here: https://docs.brew.sh/Installation
Then install the esptool:

  brew install esptool

This installs esptool as a standalone tool, allowing you to use it directly from the command line without relying on the Arduino IDE.
After installation, verify it works by running:

  esptool version

This should display the installed version of esptool.

With the esptool installed, follow these steps to update the Drone Synth software.

MacOS
1. Download the software folder with the compiled binary files to your computer.
2. Open the Terminal app and navigate (cd) inside the folder with the compiled binaries.
3.	Connect the ESP32-S3 to the computer via USB.
4.	Check the ESP32 USB port address in the terminal with the command ls /dev/cu* (e.g., /dev/cu.usbserial-0001 or /dev/cu.SLAB_USBtoUART or /dev/cu.usbmodem31401) 
5.	You may need to quit the Arduino IDE (if open) to free up the port.
6.	Put it into boot load mode - hold the boot button and click the reset button.
7.	In the script below, adjust the path to the esptool location (inc. version number) and update the port name for the host computer and connected ESP32, then execute.

"/Users/**userName**/Library/Arduino15/packages/esp32/tools/esptool_py/4.5.1/esptool" --chip esp32s3 --port "/dev/cu.usbmodem**123456**" --baud 921600  --before default_reset --after hard_reset write_flash  -z --flash_mode dio --flash_freq 80m --flash_size 4MB 0x0 "Drone_Machine.ino.bootloader.bin" 0x8000 "Drone_Machine.ino.partitions.bin" 0xe000 "boot_app0.bin" 0x10000 "Drone_Machine.ino.bin" 
