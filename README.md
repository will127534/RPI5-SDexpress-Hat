# RPI5-SDexpress-Hat

Basically a clone from my [CFE Hat](https://github.com/will127534/RPI5-CFE-Hat) and just changed the CFexpress Socket to SDexpress.  

Hardware-wise SDexpress requires additional 1.8V DC-DC and I'm using PAM2306 here, note that you can see in the photo the FB resistors are actually missing, the board is design for the adjustable version but this chip has 1.8V/3.3V fixed output variant and in that case you can put the 0 ohm resistor and that's what I have in the photo.  

Raspberry Pi's software-wise it is the exact same as CFE hat, the FW on MCU is slightly different that for layout reasons I shifted the LED output to another port and the FW in HEX is in this repo. See this [Youtube](https://youtu.be/_K-CHcIZxTY) for the HAT in action (automount/manual unmount).