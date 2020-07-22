# Church-Controller
Controller for Church Status Signs

## Introduction
After I finished the status signs for my church, the only way I had to control them was using POST links from a document on my phone.
If I was not attending on a given day, then no one else could use them.
I decided to make a hand-held control, similar to a television remote control, that was simple enough for anyone to pick up and use.

## Hardware
The core of the controller is an ESP-12e module. There are 3 LEDs the match the color options for the status signs, Green, Yellow, and Red.
There are 2 buttons which will be labelled Change and Save. Pressing the Change button will cycle through the 3 LEDs. Once you are on the correct color
press the Save button to send the change to the status signs. All connected signs will change to the same color.
The controller is powered by 3 standard replaceable AA batteries. There is also a low battery indicator LED on the front of the controller.

The hardware was designed using KiCAD. As this was a one-off device, I decided to etch my own 2 sided board instead of ordering from a low cost PCB manufacturer.
This will also allow me to rapidly iterate through designs of there are any mistakes.

## Software
The controller, just like the status signs, is programmed using the Arduino IDE. The status signs publish their Hostname and IP using mDNS. When first powered on, the controller
will search the local network for any such signs. It will perform a connection test with each sign and store the connected devices for future use. If no signs are located, the controller
will use it's LEDs to indicate an error status.

## Case
The case was designed in Fusion 360, and printed in ABS with a standard desktop FDM printer.
