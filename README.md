# Custom-9-Key-RGB-Macropad

OVERVIEW

This project is a custom 9-key macropad designed for shortcuts, productivity, & keyboard customization, for example you can have a shortcut for opening apps or controlling volume. This Macropad utilizes a Raspberry Pi Pico W as the microcontroller and has a 3x3 Cherry MX switch layout, per key RGB lighting, an OLED display, a rotary encoder, & a slide potentiometer.

My goal for this project was to make a useful macropad that has more features than just Keys. instead of only pressing buttons, you can also turn a knob, move a slider & see information on a small screen. The PCB was designed in KiCad & the case was designed in Onshape.

FEATURES

9 Cherry MX Compatible mechanical switches 
3x3 key matrix with diodes
Raspberry Pi Pico W microcontroller
Per key SK6812 MINI-E Reverse mount RGB LEDs
128x64 OLED display
Rotary encoder for volume or scrolling
Slide potentiometer for analog control
Custom PCB designed in KiCad
Custom top & bottom plate design
USB powered through the Pico W

Why I made this

I made this project because I wanted a custom macropad that was more intresting than a normal keypad. I wanted it to have RGB lighting, a screen, a knob, and a slider so it could be used for shortcuts, media control, volume control, or other custom actions.

This project also helped me learn PCB design, KiCad, routing, Keyboard matricies, RGB LED Wiring, CAD Modeling, and how to use different types of software files for PCB manufacturing & 3D printing.

How it works

The macropad uses a Raspberry Pi Pico W to read the 9 switches in a matrix. Each switch is connected through a diode to prevent ghosting when multiple keys are pressed.

The RGB lighting uses SK6812 MINI-E reverse mounted LEDs. These LEDs are Placed under the switches and shine through the clear switch housing. The LEDs are connected in a data chain, Where the Pico sends data to the first LED, which is interconected in a chanin with the rest of the 9 LEDs, in which the each LED passes the signal to the next one and to the Raspberry Pi Pico W.

The OLED display connects through 12C. The rotary encoder connects to the GPIO pins &  can be used fpr things like volume control. The slide potentiometer connects to an ADC pin on the Raspberry Pi Pico W and can be used for analog input.

Main Components

| Component | Purpose |
| :--- | :--- |
| **Raspberry Pi Pico W** | Main controllor |
| **GATERON G Pro V3 3.0 Pro Switch** | Key inputs |
| **1N4148 DO-35 diodes** | Prevents key ghosting |
| **SK6812 MINI-E LEDs** | RGB key lighting|
| **128x64 OLED display** | Visual output |
| **Rotary encoder** | Knob input |
| **Slide potentiometer** | Analog slider input |
| **Custom PCB** | Holds & connects all of the components  |
| **Custo Case** | Enclosure & style |





