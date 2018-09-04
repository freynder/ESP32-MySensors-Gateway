A basic ESP32 board designed to function as a Mysensors Gateway with the following features:

- Designed to fit in a cheap enclosure available from AliExpress such as [this](https://www.aliexpress.com/item/100x60x25mm-ABS-DIY-Plastic-Electronic-Project-Box-Enclosure-Instrument/32816989679.html?spm=2114.search0104.3.14.1dba6875AXjoca&ws_ab_test=searchweb0_0,searchweb201602_3_10152_10151_10065_10344_10068_10342_10325_10546_10343_10340_10548_10341_10696_10084_10083_10618_10304_10307_10820_10843_10059_100031_524_10103_10624_10623_10622_10621_10620,searchweb201603_6,ppcSwitch_5&algo_expid=a927ddcc-0543-4e6f-9c48-a30857222de3-2&algo_pvid=a927ddcc-0543-4e6f-9c48-a30857222de3&priceBeautifyAB=0)
- Footprints for RFM69 and nRF24L01 breakout board/
- uFL antenna connector for RFM69.
- Optional onboard LEDs for POWER, ERROR, TX, RX, Inclusion. Header for external LEDs if desired.
- Inclusion button and general purpose custom button.
- Powered and programmed over USB. Auto-reset and flash provision.

Please note that this is a work in progress and has not been tested yet. I will update the project asap.

Update Aug 10th: Tested the boards and some issues came up:
- TX and RX LEDs connected to IO34 and IO35 do not work as ESP32 does not support pull-up on those pins.
- Wrong labeling of RX led (mentioned 36 but should be 34)
- C4 capacitor was located near the CH340G chip but should have been near AMS1117
- Missing pull-up on EN pin.
- Missing capacitor to ground on EN pin.
- auto flash does not work due to missing pull-up on EN pin.

Update Aug 13th: Updated design to remedy flaws. Increased font size and optimized borders. Tagged as V2

Update Aug 29th: Found an issue with the inclusion button connected to IO33 which was also used by a LED. Corrected this by connecting to IO35 instead. Tagged as V3

Update Sept 4th: Found a design flaw causing with the power circuit which may impact transceiver operation. Temporary fix in V3.1. Will redesign the board in a future version.

