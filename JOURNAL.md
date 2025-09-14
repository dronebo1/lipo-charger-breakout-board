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

# Aug 19-20: Finishing up (Schematic) !!!

Finally finished configuring the control scheme for the input on the USBPD chip so that it can operate both within the spec inside the normal PD chip range, but also has another buck converter that it will switch the input to on its own when the input voltage exceeds the range of the PD chip, allowing it to work efficentially under both conditions

<img width="1355" height="961" alt="image" src="https://github.com/user-attachments/assets/f366fb5c-d2be-46e0-af86-703167527408" />

**Total time spent: 7h**

# Aug 20-25: Major updates

Redid schematic to split the design into multiple boards to optimize space and keep the board reasonably small, started laying out the PCB, gonna start routing soon.

<img width="394" height="643" alt="image" src="https://github.com/user-attachments/assets/a73d5c51-d5b1-4d4f-bda3-72be4ffa8fc6" />

**Total time spent: 6h**

# Sept 2: Grounded got an extension I have been saved :O

So I thought the Grounded event from hackclub was gonna end on Aug 31 so there was a lot of panic and cram but turns out it was extended. I've routed the primary board and began laying out components on the power regulation boards while I also try to figure out the logic for the safety functions through some BJTs. Also trying to find space on the back of the board to solder on the additional boards. I've also decided to make the primary board a 6 layer board with 0.5 oz inner copper weight instead of a 4 layer board with 1 oz inner copper weight as it is cheaper, and I just duplicated the inner layers.

<img width="400" height="692" alt="image" src="https://github.com/user-attachments/assets/f4b6134d-629e-43ac-8fd8-0359b8481f95" />
<img width="720" height="744" alt="image" src="https://github.com/user-attachments/assets/a820af21-711d-4488-b3bb-35aec738389b" />
<img width="687" height="732" alt="image" src="https://github.com/user-attachments/assets/ed0db22e-6c42-4f24-ace1-d1fb47846d87" />
<img width="1441" height="989" alt="image" src="https://github.com/user-attachments/assets/6fb2f614-b66b-49dd-831c-b114f2d9c611" />

**Total time spent: 17h**

# Sept 3-4: Working out the protection logic board

Now working on the board (that solders onto the main board) that uses BJT logic to do things like low voltage protection, ensuring battery cells are connected properly, and checking that no more then one cell is connected to VCC (only the highest cell should be connected to the VCC line)

<img width="1369" height="976" alt="image" src="https://github.com/user-attachments/assets/096e8728-f33d-4403-a1e4-5038b66dae85" />

**Total time spent: 6h**

# Sept 4-5: Finished protection logic board schematic

Schematic is done! See below for pics:

<img width="1472" height="1033" alt="image" src="https://github.com/user-attachments/assets/25413f32-0bbf-41a8-92d2-30b3da3cd718" />
<img width="1464" height="1024" alt="image" src="https://github.com/user-attachments/assets/5d706233-11c3-4a3a-86fe-fe008dbce386" />

**Total time spent: 4.5h**

# Sept 5: Nevermind, the schematic isn't done

I decided to change a few things. Namely: Switching the MMBT4401 BJT model to one that has no loading fee with JLC to save $3. I also increased some of the resistor values to reduce the logic power draw/power going to waste. I also swaped out the MMBT4403 BJTs for ones that were promotional extended as well, saving another $3. 

<img width="987" height="721" alt="image" src="https://github.com/user-attachments/assets/e8c705fb-07f0-4eeb-9f67-2b9ad25fefb5" />
<img width="992" height="719" alt="image" src="https://github.com/user-attachments/assets/b93f2d5f-3fd0-49b3-be6e-5684d20cc660" />

**Total time spent: 1.5h**

# Sept 5-6: (Layout) I told myself I would finish it up quickly. I did not.

So I decided that I hate my mental health and decided at 12:30 AM that I would grind this out until the layout was **entirely** finished, but little would I know I would still be working on it past 2:00 AM. Anyhow, the layout is now done for the protection logic board.

<img width="520" height="831" alt="image" src="https://github.com/user-attachments/assets/74d99a5e-ae73-45a8-8da3-814e1940b37d" />

**Total time spent: 5h**

# Sept 7: A lot of routing

Got through routing the other three boards, although I'm most behind on the logic board, for olvious reasons.

<img width="508" height="815" alt="image" src="https://github.com/user-attachments/assets/40c4e92b-ffe7-4817-ab66-79d45a46e938" />
<img width="574" height="829" alt="image" src="https://github.com/user-attachments/assets/8d7923e8-f6be-411a-b459-ae23d4987ab5" />
<img width="584" height="818" alt="image" src="https://github.com/user-attachments/assets/b1b2c17f-8849-436d-b3e1-7acdd8a62260" />

**Total time spent: 10.5h**

# Sept 9: Finishing protection logic board routing

The sept 20th deadline is creeping closer... so I'm trying to finish soon. Hopefully. So I grinded out all of the rest of the routing for the protection logic PCB, which was a little harder then I thought, as there was many intersecting ratlines.

<img width="606" height="960" alt="image" src="https://github.com/user-attachments/assets/a098f247-ceb7-49d0-b806-01b9be70f558" />
<img width="603" height="953" alt="image" src="https://github.com/user-attachments/assets/4f62667c-3842-4770-b4cf-801fc4efab45" />

**Total time spent: 4h**

# Sept 10: Finalizing

Finishing things up:

Adding pads to the back of the logic protection board 

Adding tooling holes to the main board and modifying outline to accommodate for holes

<img width="531" height="578" alt="image" src="https://github.com/user-attachments/assets/25fdf90a-0124-4131-ab36-4759a73943ef" />
<img width="415" height="567" alt="image" src="https://github.com/user-attachments/assets/90701e71-5a5a-480f-931e-fdd0f75ef3bc" />

**Total time spent: 3h**

# Sept 11: Final stretch!

Added pads to the back of the main board for wiring to other boards

Added pads to other two power converter boards also for wiring

Also added tooling holes for all boards, and finialized everything

Also now trying to export everything and throw it into JLC so I can see how much it costs... scary...

<img width="592" height="860" alt="image" src="https://github.com/user-attachments/assets/4e668926-f5d5-4285-b999-88bd10f9f4ae" />
<img width="629" height="830" alt="image" src="https://github.com/user-attachments/assets/91cf6bde-0ee1-4f3c-8368-352dd2b0ae6c" />
<img width="592" height="860" alt="image" src="https://github.com/user-attachments/assets/5d2aa0ff-959f-4a46-98b7-62d2645b3405" />

**Total time spent: 5**

# Sept 12: JLC doesn't have parts I need T-T

I stupidly design the high side switch oof the USBPD module (to turn it on an off) with a pretty specific chip with new features, but it went out of stock by the time I actually finished everything, so I spent basically the entire day looking for alturnatives until I stupidly realized that I can just connect a P channel MOSFET driven low by a N channel MOSFET with a pullup resistor on the gate

<img width="1286" height="909" alt="image" src="https://github.com/user-attachments/assets/87add065-f5b3-4353-96d4-5912582549ec" />

**Total time spent: 7h**

# Sept 14: Finishing up (for real this time)

Finalizing the board, routing new design with schmatic changes, looking for any JLC extended parts that I can replace with basic parts to save money and adding some capacitors for filtering. Going through all the resistors and capacitors that I have and recalculating what possible options work with the ICs so that I can use basic ones takes a *ton* of time.

<img width="575" height="821" alt="image" src="https://github.com/user-attachments/assets/3506d32e-5704-44ec-bcb1-3454678bb921" />

BEC: ($71 before optimization :O )

<img width="1756" height="897" alt="image" src="https://github.com/user-attachments/assets/8cdd33bf-eb20-4409-8faa-06d09a0f88a9" />

USBPD chip: ($78 before optimization)

<img width="1935" height="992" alt="image" src="https://github.com/user-attachments/assets/120b8630-ff29-426e-b566-058bcff9c6df" />

**Total time spent: 10h**

Final costs:

<img width="751" height="1003" alt="image" src="https://github.com/user-attachments/assets/539f0628-5e93-4d2a-b290-2f830f5fdc80" />
