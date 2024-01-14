# Flashing a Troodon v1.0 MCU with Klipper
https://www.teamfdm.com/forums/topic/1181-klipper-in-a-duet2-wifi/#comment-9166
https://advanced3dprinting.com/wp-content/uploads/2021/03/Advanced-3D-Printing-Klipper-Kit-Installation-Guide-v0.1.pdf

There are a few articles that describe the "How".

make menuconfig
Microcontroller: SAM3/SAM4 (Due and Duet)”
Processor model: “SAM4e8e (Duet Wifi/Eth)”
Use USB for communication.

# Troubleshooting
Many articles describe flashing the board with Klipper and finding the command:

    ls /dev/serial/by-id/*

No longer reports correctly. I found errors for enumerating that USB device in my dmesg.

I was able to fix this by flashing a Raspberry Pi 3 with Raspberry PI OS Buster, I used this image:
https://downloads.raspberrypi.com/raspios_lite_arm64/images/raspios_lite_arm64-2020-08-24/
I then installed kiauh (to then install klipper), and this missing dependency libwxgtk3.0-dev .
https://github.com/dw-0/kiauh
Using this installation of Klipper the board flashes correctly. I am then able to connect from the regular controller.