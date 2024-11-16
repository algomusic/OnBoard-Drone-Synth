The OnBoard Drone Synth is a DIY synthesizer that enables the performance of up to 5 independent voices. Each voice is monophonic with controls over pitch, release time, detune, timbre, pitch wander, vibrato, pulsing amplitude variation, and volume level. The stereo output from all voices is passed through overdrive, filter, two independent delays with cross modulation, and reverb. Sonically, the Drone Synth embraces the post-digital and somewhat gritty aesthetic of DIY audio culture.

The PDF is a user guide for Drone Synth owners.

The "esp32.esp32.lolin_s3_mini" folder contains files for the latest software update. Below are some steps for updating the software. It assumes you have the Arduino IDE and the ESP32 board package (version 2.0.17) from Espressif installed.

MacOS
1. Download the software folder with the compiled binary files to your computer.
2. Open the Terminal app and navigate (cd) inside the folder with the compiled binaries.
3. Connect your Drone Synth to the computer via USB.
4. You may need to quit the Arduino IDE to free up the port after checking the current port number.
5. In script below, adjust the path to the esptool location (inc. version number) and update the port name for the host computer and connected ESP32, then execute.

"/Users/userName/Library/Arduino15/packages/esp32/tools/esptool_py/4.5.1/esptool" --chip esp32s3 --port "/dev/cu.usbmodem141101" --baud 921600  --before default_reset --after hard_reset write_flash  -z --flash_mode dio --flash_freq 80m --flash_size 4MB 0x0 "Drone_Machine.ino.bootloader.bin" 0x8000 "Drone_Machine.ino.partitions.bin" 0xe000 "boot_app0.bin" 0x10000 "Drone_Machine.ino.bin" 
