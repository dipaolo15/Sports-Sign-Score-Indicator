# Sports-Sign-Score-Indicator

Overview:
An 8x16 LED sign that will include scrolling text, scoring indicator of favorite NHL/NFL/MLB team, and speaker to play a song when team is scored.

Module:

CONTROLLER:
ESP32 is used as the MCU. It controls the LED matrix via I2C, Audio via SP.

PROGRAMMING:
ESP32 code is developed using Arduino IDE (C++) and programmed via USB-UART. USB to UART will be done using CP2102 IC.

POWER:
To power the sign will be a barrel connector that takes in 5V and down converts it to 3.3V using OKL_T_6_W5N_C (POL Module) giving both 3.3V and 5V rail. There is an option to power the board through USB is available, but the 3.3V rail must be disabled due to lack of current. The feature is mainly to program the ESP32 with power all the modules.

LED MATRIX:
The 8x16 LED matrix driven by HT16K33. The matrix will be spilt into 2 section; The first section will be the first 7 rows (BLUE LEDS) that will display scrolling text that can be customized by user via webserver. The second section is the 8th and last row that will be used for goal indications (RED LEDS). 

AUDIO
The Audio will be uploaded via micro-SD card and played through a single speaker. The micro-SD is connected to the ESP-32 via SPI and is played through the speaker using MAX98357AETE_T.

GOAL INDICATOR:
To indictor a goal is scored, a Budweiser goal glass circuit will be connected to the board. Specifically, the red LED on Budweiser board will be used as the goal interrupt. This will allow the user to use the Budweiser sports app to choose teams.
