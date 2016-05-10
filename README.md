# i2c-mux-pca9545a
RPi Device Tree Overlay for TCA9545a

So here is what you need to do to get the Device Tree Overlay working for the TCA9545:

1) Make sure you are on Raspberry Pi Kernel 4.4 (may require sudo BRANCH=next rpi-update).

2) Add the device tree overlay file for the TCA9545a to the /boot/overlays directory.

3) Add the following line to you /boot/config.txt file:

dtoverlay=i2c-mux-pca9545a,addr=0x73

4) Reboot your RaspberryPi

You should now see multiple i2c devices in your /dev directory, where i2c-1 is your raspberry pi's i2c bus, and the additional i2c devices are your mux where the first (after i2c-1) is Bus 0 on the mux, etc.
