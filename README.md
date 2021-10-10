# Shelly-Plus1
The first thing i did after receiving my newly released Shelly+1, was to take it apart and see what’s inside. I quickly realized that the normal programming port was way smaller then the one of the none + series and that there wehre some more pins. So i searched on the Shelly webpage for some more info about the device, but sadly they didn’t add anything (at least when i checked) no pin layout on there knowledge base tap like they did for the Shelly 1. After realizing this i went back on google and searched for “Shelly pinout” and found that the Shelly 2.5 had a somewhat similar layout to the Shelly 1. 

![pin_out](https://user-images.githubusercontent.com/38843794/136706046-0f4d035d-a319-4dd9-9c54-039a3613e6e6.png)
# First light
So i tried to solder some dupont wires to the connector and startet serial reading, with success. I thought that i now just needed to add a new device at ESP Home, select a generic ESP32 board to start with and create a .bin file. But after uploading wich worked right away for my surprise, the Shelly kept restarting with an error message in the serial monitor (“Running on single core chip, but application is built with dual core support.”). Now i realized that it wasn’t as simple as i thought it would be and started digging even more for a solution in the web and found this post on the ESPHome GitHub page  https://github.com/esphome/issues/issues/1560#issuecomment-866286717 .
There where discussing a similar problem with a single core esp 32 board. With this added to my config file i created a new .bin and started uploading, after rebooting the first sings of life started to appear. The Shelly started up successfully and connected to the wifi. Now i just needed to figure out where every thing was connected to. 

# Pin Out
The on board LED seemed to be on GPIO 0, the rely on GPIO 26 and the switch input on GPIO 4. The only thing i couldn’t figure out was the onboard button but i figured i wouldn’t need it anyways.

# Conclusion
So i hope this small post helps anyone who also wants to flash ESP Home firmware to an Shelly +1 and not wants to use the newly developed features and everything else that comes with the new Shelly. 
