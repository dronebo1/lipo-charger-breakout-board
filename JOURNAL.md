Title: Lipo charger breakout board

Author: Droneboi

Description: Ever wanted to fully utilize every channel on your 8S/6S lipo charger? Use this board to use every channel at the same time, breaking out up to 8 channels, allowing you to charge 8 1S cells, 2 4S cells, or even one 4S cell with 2 2S cells

Created On: 8/9/2025


# Aug 9th: Put together basic structure of ports, as well as general schematic and functions

Allows for all cell configurations under 8S, excluding the use of 5S lipos, as those are highly uncommon. Also included switches to control the total cell voltage for linking the correct balence pin to the VCC pin on the XT60 port of the charger, as well as indicator LEDs to minimize chance of accidental shorts. 
Also added a buck boost module as a regulator to provide a stable voltage for the LEDs, which can either source from the 1S port, or the USBC in port.

<img width="1006" height="690" alt="image" src="https://github.com/user-attachments/assets/586dfd7a-fb0b-4e05-9878-4d70f7fadb31" />

**Total time spent: 7h**


# Aug 10th: Organized schmatic, looking for parts

Looking through jlc parts library for BJT and USB PD source controller.
Also brainstorming how to configure BJT logic for anti-short warning and prevention

<img width="1350" height="970" alt="image" src="https://github.com/user-attachments/assets/d0cfa377-93e8-4c52-a572-ac861022aa31" />

**Total time spent: 4h**


# Aug 17-18th: DESIGN DESIGN DESIGN

Decided to split boards between bjt logic and interface. Working on interface. Did a LOT of design and part selection (yes I more or less did this in one sitting and no I wasn't being lazy about previous work, this is my first time working on it in a while). I've added LED indicators, reduced some part counts by using one big resistor instead of a few small ones, changed out connectors I decided to use, and added USB connectors for USBPD out. I think that covers most of it. ALthough this log might be a lil off, given that I'm writing this at 2:01 AM local time.

<img width="951" height="674" alt="image" src="https://github.com/user-attachments/assets/ec4f17c8-6247-4415-8114-381723e6bfc0" />

**Total time spent: 13h**
