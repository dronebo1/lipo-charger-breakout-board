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
