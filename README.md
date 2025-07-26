# RPI5-SDexpress-Hat

Basically a clone from my [CFE Hat](https://github.com/will127534/RPI5-CFE-Hat) project and just changed the CFexpress Socket to SDexpress.  
![_DSC9346](https://github.com/user-attachments/assets/da201f2d-dddb-46df-8180-21155665d7b8)

Hardware-wise SDexpress requires additional 1.8V DC-DC and I'm using PAM2306 here, note that you can see in the photo the FB resistors are actually missing, the board is design for the adjustable version but this chip has 1.8V/3.3V fixed output variant and in that case you can put the 0 ohm resistor and that's what I have in the photo.  

Raspberry Pi's software-wise it is the exact same as CFE hat, the FW on MCU is slightly different that for layout reasons I shifted the LED output to another port and the FW in HEX is in this repo. See this [Youtube](https://youtu.be/_K-CHcIZxTY) for the HAT in action (automount/manual unmount).

<img width="1590" height="1084" alt="image" src="https://github.com/user-attachments/assets/9125ba06-486f-4f36-a256-4784828ec52f" />
<img width="2119" height="1472" alt="image" src="https://github.com/user-attachments/assets/6acf37dc-1d6b-4622-9298-7770a6e19aee" />
[Interactive BOM](https://htmlpreview.github.io/?https://github.com/will127534/RPI5-SDexpress-Hat/blob/main/bom/ibom.html) [(provided by InteractiveHtmlBom)
](https://github.com/openscopeproject/InteractiveHtmlBom) 

### Random notes
In general, I don't really see a point of using microSD express card: If you need external storage, M.2 SSD is cheaper; If you need removable storage, M.2 SSD in CFexpress Type B is cheaper.  

microSD express reading speed is indeed faster then microSD card, however it's writing speed is more about the same as high-end microSD express card (160~200MB/s). Now you might see some microSD express advertise for >200MB/s writing speed, but that is not *sustained* performance, similar to how NVMe SSD works, some microSD express have pSLC cache for higher burst write speed. So it make sense as a gaming storage but I don't see the point for camera recording or any type of high speed recording device given the pricing comparing to standard high-end microSD card / USB flash or M.2 SSDs. I actually waited for a while to see if there are cheaper options other then the Nintendo branded one but there is none. I'm guessing that there is a physical/power limit on how many NAND channel you can fit in microSD card format, which limits the sustained write performance because that is based on RAW NAND speed.  

Thermal-wise with and without external fan doesn't change the performance during the stress test that last for an hour, it does get a little bit warm but it is not hot at all so that is some good news. Something I didn't expect though is that there aren't a lot of options for the socket either, and there is no self-ejection options out there currently and it actually took me a lot of force to pull the card out.  

One last note: I won't do PCBA for this board because microSD express card is not there(Cost/Performance/Prevalent) yet, but this project is in MIT license so do whatever you want with this.
