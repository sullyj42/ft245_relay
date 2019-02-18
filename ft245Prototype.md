Prototype environment to test FT245 for use as a relay controller. Tested on Raspberry Pi 3 with latest ADR image installed. 

- Objective

    - Determine if FT245 chip can be used to control logic level relays

    - Characterize software complexity

- Environment setup

    - Flash image from ADR payload (ADPUP/Sandshark/payload/software/image/adr-28Aug2018.img)

        - Etcher on Windows 10. Threw a verfication failure (xxhash). No apparent effect

    - Connect to Wifi

        - ~./wifi_up.sh "<outernet_key>"

    - Update software packages

        - sudo apt-get update; sudo apt-get upgrade; sudo apt-get autoremove (took ~ 1 hour, 20190218)

- Clone github rep

    - Update time, if necesary (sudo apt-get install ntpdate; sudo ntpdate... update?

        - Unclear if this was uninstalled to avoid conflicts w/ GPS RTC

    - git clone https://github.com/tankbiuk/ft245-usb-relay.git; 

        - Follow readme to install dependencies (sudo apt-get install libftdi1, libftdi1-dev); 

        - Compile using command w/ -I option

        - Run commands as sudo (for USB privelages)

- Testing

    - Board responded as-expected, verified w/ multimeter

    - Oddity when measuring w/ gnd reference to USB-B Shield

        - Seeing ~ 1.8 V on "low" pins

        - Not seen when referenced to "GND" pins

        - Not investigated further. Assuming bad connection
