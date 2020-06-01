---
layout: component
title: "ESP32 Development Board"
categories: hardware, esp32
---

The ESP32 is the microcontroller at the heart of this project. The ESP32 is a SOC in a SMD package. It comes in a number of variants, namely WROOM and WROVER. The main difference between these chips is that the WROVER integrates an 8mb SPI PSRAM chip on the module. Under both of these chips are a few variations (e.g. ESP32-WROOM-32D vs ESP32-WROOM-32U) which mostly differentiaties between the inclusion of an onboard antenna or a U.FL connector. A somewhat complete list of the various SMD modeules can be found here: [ESP32#Surface-mount_module_board](https://en.wikipedia.org/wiki/ESP32#Surface-mount_module_boards). The WROVER is more readily available, cheaper and sufficient for this application, hence this is the chip we will be targetting.

The ESP32 being a SMD module is somewhat difficult to develop with. A number of different manufacturers have created development boards with a number of different components soldered alongside the ESP32 chip to add functionality simplify the development purpose. Most of these will include breakouts and UART Bridge over some USB connector to allow for flashing the ESP32 Module. Some boards also integrate Lithium battery connectors (and BMS) and OLED Displays. It is important to note that the ESP32 and these development boards are typically inexpensive, however, due to the current corona situation effecting international deliveries to Australia, there are not many options available that would reach me in any reasonable amount of time.

As such, I have purchased an unlabelled board from eBay, which is targetted from various IDE's as a generic "ESP32 Dev Module". I have also made an order via Amazon US for a TTGO T-Display ESP32. The TTGO Development Board will more than likely be the package that I use in my final product, withstanding availability of GPIO ports. Purchasing from Amazon US is not ideal, however, in my experience Amazon US deliveries are still happening in a timely manner, so I am expecting this board to arrive shortly, at which point I will change over my development process to target this new board.

My two development boards:
### Initial Testing Board
[Generic NodeMCU-32s Development Board](https://www.ebay.com.au/itm/ESP-WROOM-32-ESP32-ESP32S-2-4GHz-WiFi-Bluetooth-Development-Board-for-Arduino-O/223955934987?ssPageName=STRK%3AMEBIDX%3AIT&_trksid=p2057872.m2749.l2649)
This is a no frills ESP32 development, very similair to the ESP32 DevKit-C from Esspresif (As far as I am aware)
* [Pinmap]({{site.baseurl}}{% link /assets/images/components/esp32/Generic_NodeMCU_ebay_pinout.jpg %})

### Final Product Candidate Board: 
[TTGO T-Display ESP32](https://www.amazon.com.au/gp/product/B07XQ5G279/ref=ppx_yo_dt_b_asin_title_o03_s00?ie=UTF8&psc=1)
In a proper production product, a company would opt for the SMD module and integrate the functionalities provided by the development board into their own PCB. However, this is hugely overkill for this project and this board seems to present as a small neat package which will allow for easy flashing. It even comes with a USB Type-C interface and I believe it has a BMS which will charge our Lithium Battery (I am however, not yet certain if this is suitable for use with 18650 Lithium Ion Batteries)
Files: 
* [Schematic]({{site.baseurl}}{% link /assets/images/components/esp32/TTGO T-Display Schematic.pdf %})
* [Github Repo](https://github.com/Xinyuan-LilyGO/TTGO-T-Display)
* [Pinmap](https://github.com/Xinyuan-LilyGO/TTGO-T-Display/blob/master/image/pinmap.jpg)