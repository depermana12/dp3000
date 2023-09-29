# DP3000 Macropad
<img width="150" src="https://i.imgur.com/cgdVpCk.png" alt="dp3000 macropad" title="dp3000 macropad">

dp3000 is a simple yet elegant macropad, embedded with an Atmel 32u4 chip. I created this dev board named dp3000, the first and second letters are my initials and the three digit numbers are just random numbers like i love u 3000.

# Features
+ 2x4 (8 keys)
+ dual rotary encoder
+ oled display (support 128x32 or 128x64)
+ hot-swap socket (support mx style or kailh choc low profile)
+ mx style or low profile choc v1, v2* switch
    * *for choc v2 u need to file the center hole in the pcb, don't file pass the white circle line
+ RGB light underglow or RGB matrix
+ support QMK, VIA, VIAL
+ basic stacked acrylic case

# Gallery

<img width="250" src="https://i.imgur.com/sQ4ibtDh.jpg" alt="dp3000 macropad" title="dp3000 macropad"> <img width="250" src="https://i.imgur.com/syD0cwoh.png" alt="dp3000 macropad" title="dp3000 macropad"> <img width="250" src="https://i.imgur.com/vf11E3wh.png" alt="dp3000 macropad" title="dp3000 macropad">
<img width="250" src="https://i.imgur.com/zyeyvmIh.jpg" alt="dp3000 macropad" title="dp3000 macropad"> <img width="250" src="https://i.imgur.com/Y8gjBzFh.jpg" alt="dp3000 macropad" title="dp3000 macropad"> <img width="250" src="https://i.imgur.com/7isRSlUh.jpg" alt="dp3000 macropad" title="dp3000 macropad"> <img width="250" src="https://i.imgur.com/9Bno4R3h.jpg" alt="dp3000 macropad" title="dp3000 macropad"> 
<img width="250" src="https://i.imgur.com/woYWa3lh.jpg" alt="dp3000 macropad" title="dp3000 macropad"> <img width="250" src="https://i.imgur.com/pPlGpSOh.jpg" alt="dp3000 macropad" title="dp3000 macropad">

# Getting started

dp3000 have 2 different types of firmware, QMK and VIA. Each firwmare have 2 version.
I recommend using VIA, it's user friendly, and easy to customize.

* rev1 version support `rgb_matrix`
* rev2 version support `rgblight` underglow
* (unofficial) rev3 version support both `rgb_matrix` and `rgblight` (hardware modification needed!)

1. choose your preferred firmware
2. flash the firmware
3. customize your keymap using VIA
4. profit?

# Default keymap
<img src="https://i.imgur.com/CVwRCO8.jpg" width="500" />

both firmware QMK and VIA come with above default keymap. However, it is important to note that the purpose of this board is primarily to serve as a customizable and programmable for macros.

so, the keymap configuration is intended to be personalized according to the user's specific needs and preferences. 
feel free to assign different keycodes or commands to each key, tailoring the macropad to your own workflow and requirements. 
