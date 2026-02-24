Flashing OnBoard Drone Synth Firmware onto ESP32 with ESPConnect

Follow these steps to flash the Beat Machine firmware onto your ESP32 using the web-based ESPConnect.

Prerequisites
• Computer with Chromium web browser and internet access
• Drone Synth device and USB cable
• Firmware file (latest xxx.ino.bin) from github repo: https://github.com/algomusic/OnBoard-Drone-Synth

Steps
1. Open a Chromium browser on your computer and visit the ESPConnect site:
https://thelastoutpostworkshop.github.io/microcontroller_devkit/espconnect/
2. Connect the Drone Synth to the computer via USB. USB C -> C seems to work best.
3. In ESPConnect tick the ‘Connect’ button and select the port for the Beat Machine and click
‘connect’ in the popup dialog. ESPConnect should display info about the ESP32 chip.
4. On the left of the ESPConnect site, click ‘Flash Tools’. Scroll down to the ‘Flash Firmware’
section of the page.
5. Drag the Drone_Machine...ino.bin from your computer onto the Firmware Binary
area of the site.
6. From the ‘Recommended OXsets’ menu select ‘app0 - 0X10000’
7. Click the ‘Flash Firmware’ button, confirm if required, then wait for the firmware to be
uploaded.
8. The Drone Synth should restart.
9. If the buttons on the Drone Synth are unresponsive then press the Reset button on the ESP32.
10. Close the Browser.