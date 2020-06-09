---
layout: component
title: "PCB Design"
categories: hardware, pcb
---

Part of this build involves designing and printing a custom PCB for the keebpad. There are some services from China that allow for cheap printing of custom PCB's. Generally the charge is ~$5USD for 5 boards and ~$20USD for shipping to Australia. Thanks to the availability of these services, I have opted to produce a PCB for my initial POC instead of building everything onto perfboard first. I do not recommend this, inevitably my first PCB design will have some errors that will need correction and reprinting. This is a risk I am willing to assume to save myself the pain of creating my perfboard POC.

EasyEDA is web based EDA to design schematics and PCB layouts. The idea is very simple in concept, but learning this tool may some time. I highly recommend watching this video before starting: https://www.youtube.com/watch?v=utBQqcuOt9U
Since this is completely new to me, I had some unanswered questions after watching this video, which I will just dump here:

Schematic:
* Start by building your schematic first
* Labelling your nets is just like naming the interconnects between your components. This allows you to neatly split your schematic into different collections of components without creating a mess of wires everywhere. I opted to use net flags AND net labels because I think net flags are sometimes clearer and cleaner.
* Under "Design Manager" you can check your nets. Basically this will give an error if a net is unconnected. Make sure all your nets are connected and if you purposefully do not want to connect something, use the "no connect flag" in the wiring tools
* When picking components, you can see both the schematic pinout and the PCB design of the component. Make sure you check the PCB design of the component (specifically physical dimensions of the pin placements) to make sure the pin layout matches the components you are going to use

PCB:
* Click and drag Mouse Button 1 to move components
* Click and drag Mouse Button 2 to move your view
* Scroll for zoom
* R for rotate
* Autowire seems cool, but it never worked for me. You have to manually connect components with the "Track" tool
* To create breakouts on your board use the "Pad" tool
* Alot of youtube videos talk about copper area. It is unclear to me if this is needed, but you have to set a net for your copper area layer. I've set both of mine to ground, no idea if this is correct. We will see. It does look neater though, and creates an "island" for a track instead of just a simple copper track. My hunch is that some people do this mostly for aesthetics. It does indeed have a function, but I am yet to work out what that is.
* You can move different components to different layers (as well as the tracks)
* A strategy I used to overcome impossible interconnects is to skip between layers to bridge over existing tracks. Make sure that when you change the layer mid track, you connect the layers with a via.
* Similarly to checking nets in your schematic, you can perform a DRC on the PCB. This will tell you about any design rule violations your design has.

That's it! After some time with the tool, no doubt it will make more sense. I would rate it average on the intuitive scale, it definitely takes some playing with to get used to, but once you have moved passed a problem, in hindsight the solution seems to make sense. 

I have created my PCB and Schematic and have ordered the PCB. I will not share my initial POC just yet, as I am sure it has many problems and do not want anyone accidently ordering the POC. Immediately after ordering the PCB, I noticed that I forgot to add an inline resistor on the data output to the WS2182B LED's. Hopefully the LED's function without it, otherwise I will have to try to hack in a resistor onto the PCB.

The initial POC is wiring an 18650 Battery Holder straight to some Pads. When the PCB arrives I will solder a microJST connector to the pads and plug it in directly into the TTGO T-Display battery input. This MicroJST connector will sit under the ESP32 TTGO Dev Board on the PCB. I am still unsure about this solution; I am not sure if this connector will be beefy enough to power the board and all the LED's. Ideally everything is fine and I can leave it as is. A possible improvement for the next PCB design will be to include my own powersupply and 18650 battery charger. Something I definitely want to change is to include a physical power switch for the device.

On this page I will document issues with my PCB as I find them as well as improvements I want to make on the next revision.

Issues:
* No inline resistor for led_data line

Improvements:
* Physical Switch to disconnect Battery Supply
* DIY Power Supply with LiPo Charger