# Assorted Breakout Boards
This is a collection of small breakout boards for small devices that I made with KiCad 

## Time Bug (DS13xx breakout) (`time_bug`)

<img src="images/time_bug_3d_top.png" height="200">
<img src="images/time_bug_3d_bottom.png" height="200">
<img src="images/time_bug_pcb.png" height="200">

This is a breakout for the DS13xx series of RTC chips, with a MSOP-8 package (eg: DS1307, DS1308, DS1337, DS1338, DS1339, DS1341, DS1342, DS1371).  **This won't work with the DS1302 or DS1347**.  The board is designed to work with chips with the following pinout:

<img src="images/time_bug_pinout.png" height="200">

The two pads at the top of the board are connected to the crystal pins of the DS13xx (X1 and X2).  The board is designed such that the crystal can be placed beside the PCB, and the pins of the crystal are bent at 90°, so they can be soldered to the pads on the PCB.  The capacitor is a decoulping capacitor, and should be 0.1µF (look at the datasheet to see if there is a better capacitance for that chip).

## PCIe Friend (`pcie_friend_2`)

<img src="images/pcie-friend-top.png" height="200">
<img src="images/pcie-friend-bottom.png" height="200">
<img src="images/pcie-friend-pcb.png" height="200">

This is a very very simple debug board for PCIe x1 cards.  It basically acts as a man-in-the-middle for each of the signals on the PCIe x1 connector, hopefully making it easier to measure each signal.  

A PCIe card plugs into the device, which itself plugs into a PCIe slot.  Each pin for both connectors are brought to the middle of the board, to a 2.54mm header.  Normally most pairs of pins will be shorted using a jumper to allow the signal to pass, but debug probes can be connected to the pins to measure the signal.

Since PCIe makes use of several pairs of differential signals, using this board *might* have an impact on signal integrity, meaning there will probably be an impact on the bus' throughput.  I've tried to keep the traces length matched, but they aren't impedance matched.  I don't have the right equipment to assess how much the PCIe Friend changes the signal, so I would only recommend using it for debugging simple devices.

## ESP32 WROVER (`esp32-wrover-breakout`)

<img src="images/esp32-3d.png" height="200">
<img src="images/esp32-pcb.png" height="200">

This is a breakout board for the ESP32-WROOM-32 and ESP32-WROVER modules.  This probably won't work with the ESP32-S2.

## I²S Microphone (`i2c-mic-breakout`)

<img src="images/i2s_mic_top.png" height="200">
<img src="images/i2s_mic_bottom.png" height="200">
<img src="images/i2s_mic_pcb.png" height="200">

This is a breakout for the really tiny [SPH0645LM4H-B](https://cdn-shop.adafruit.com/product-files/3421/i2S+Datasheet.PDF), which is an I²S microphone.

## Alps 5 Way Switch (`alps-5-way-switch`)

<img src="images/alps-switch-top.png" height="200">
<img src="images/alps-switch-bottom.png" height="200">
<img src="images/alps-switch-pcb.png" height="200">

A breakout board for two five way switches designed by ALPS.  One of the switches is the [SKQUCAA010](https://cdn-shop.adafruit.com/datasheets/SKQUCAA010-ALPS.pdf), which is now discontinued.  The other switch is the [SKRHAxE010](https://www.mouser.co.uk/datasheet/2/15/SKRH-1370966.pdf), which isn't discontinued.

## QFN-16 (`qfn-16-3mm-breakout`)

<img src="images/qfn-16-top.png" height="200">
<img src="images/qfn-16-bottom.png" height="200">
<img src="images/qfn-16-pcb.png" height="200">

This is a breakout board for 3x3mm or 4x4mm QFN-16 chips that are 0.5mm pitch.

## QFN-24 (`qfn-24-breakout`)

<img src="images/qfn-24-top.png" height="200">
<img src="images/qfn-24-bottom.png" height="200">
<img src="images/qfn-24-pcb.png" height="200">

A breakout board for 3x3mm QFN-24 chips, with 0.4mm pitch.  It is delibrately designed so that the chip is parallel with the board so chips like IMUs point upwards when connected to a breadboard.

## SOT-23 (`sot23-breakout`)

<img src="images/sot-23-3d.png" height="200">
<img src="images/sot-23-pcb.png" height="200">

A breakout board for SOT23 chips with (up to) 6 pins.  The pins are broken out in an anticlockwise way, so pin one on the SOT23 chip correlates to pin 1 on the board.  There's a little circle beside pin one on the board.