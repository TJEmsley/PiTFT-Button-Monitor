# OctoPi-Touchscreen
Connecting Adafruit 2.8 PiTFT to my Raspberry-Pi, optimized to run OctoPi.
This script monitors the buttons on the PiTFT resistive touch display.
The state of the button is recorded in btn#Memory so that we can toggle things on and off with a single switch.
You can assign scripts or actions to each button.
This example toggles the TFT backlight with button 3, starts/stops OctoPiPanel with button 4, and powers down with button 1
# Prerequisites
Raspberry-Pi loaded with OctoPi http://octoprint.org/download/
OctoPiPanel loaded and set up to run from command line https://github.com/jonaslorander/OctoPiPanel
Adafruit PiTFT2.8 resistive touch display installed https://learn.adafruit.com/adafruit-pitft-28-inch-resistive-touchscreen-display-raspberry-pi/downloads?view=all
X windows configured to boot to the PiTFT and rpi_power_switch enabled https://learn.adafruit.com/adafruit-pitft-28-inch-resistive-touchscreen-display-raspberry-pi/downloads?view=all#extras
# Setup
put PiTFT_Buttons.py.txt in the pi/home directory and rename it PiTFT_Buttons.py

Now add the below lines to /etc/rc.local at the end of the file just before the "exit 0" line

          # launch the PiFTF button monitor
          python /home/pi/PiTFT_Buttons.py
