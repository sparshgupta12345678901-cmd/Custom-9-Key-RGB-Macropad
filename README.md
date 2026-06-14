# Custom-9-Key-RGB-Macropad

**OVERVIEW**

This project is a custom 9-key macropad designed for shortcuts, productivity, & keyboard customization, for example you can have a shortcut for opening apps or controlling volume. This Macropad utilizes a Raspberry Pi Pico W as the microcontroller and has a 3x3 Cherry MX switch layout, per key RGB lighting, an OLED display, a rotary encoder, & a slide potentiometer.

My goal for this project was to make a useful macropad that has more features than just Keys. instead of only pressing buttons, you can also turn a knob, move a slider & see information on a small screen. The PCB was designed in KiCad & the case was designed in Onshape.

**FEATURES**

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

**Why I made this**

I made this project because I wanted a custom macropad that was more intresting than a normal keypad. I wanted it to have RGB lighting, a screen, a knob, and a slider so it could be used for shortcuts, media control, volume control, or other custom actions.

This project also helped me learn PCB design, KiCad, routing, Keyboard matricies, RGB LED Wiring, CAD Modeling, and how to use different types of software files for PCB manufacturing & 3D printing.

**How it works**

The macropad uses a Raspberry Pi Pico W to read the 9 switches in a matrix. Each switch is connected through a diode to prevent ghosting when multiple keys are pressed.

The RGB lighting uses SK6812 MINI-E reverse mounted LEDs. These LEDs are Placed under the switches and shine through the clear switch housing. The LEDs are connected in a data chain, Where the Pico sends data to the first LED, which is interconected in a chanin with the rest of the 9 LEDs, in which the each LED passes the signal to the next one and to the Raspberry Pi Pico W.

The OLED display connects through 12C. The rotary encoder connects to the GPIO pins &  can be used fpr things like volume control. The slide potentiometer connects to an ADC pin on the Raspberry Pi Pico W and can be used for analog input.

**Main Components**

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

**PCB Design**

The PCB was designed in KiCad. It includes a switch matrix, diode wiring, RGB LED chain, OLED header, rotary encoder, slide potentiometer, & a Raspberry Pi Pico W which everything is wired to.

The RGB LEDs are powered from the VBUS/5V from the Pico, while the OLED & potentiometer use 3.3V. The LED data line goes through a 330 ohm resistor before reaching the first LED.

(PCB IMAGE)

**CASE Design**
The case was designed in Onshape and has 2 parts TOP case which is the top piece and BOTTOM case which is the bottom piece and they both join together using pegs. My case design is themed like Jojo's Bizzare Adventure and has a decal of the logo on the bottom piece, & multiple different types of decals of the top case design. the top plate also has cutouts for all of the components, & the bottom case has a mount for my PCB.

(FULL MACROPAD PICTURE & ONLY CASE PICTURE)

**Wiring**
The 9 key 3x3 Matrix Visual

| Row / Colum | Colum 0 | colum 1 | colum 2 |
| Row 1 | Switch 1 | Switch 2 | Switch 3 |
| Row 2 | Switch 4 | Switch 5 | Switch 6 |
| Row 3 | Switch 7 | Switch 8 | Switch 9 |

Each switch is conected to a diode, and each diode conects to a row line.

(IN DETAIL)
Basically put all 9 switches in a 3x3 matrix then wire the switches in a colum & in a row then put a diode next to each switch and run the row line through one of the connections while the other side is connected to the switch then connect each of the 3 rows & colums to a GPIO pin on the Raspberry Pi Pico W.

(Switch Wiring picture)

**RGB LED Chain Wiring**

The RGB Leds are connected in a chain:

Pico GPIO pin > 330 Ohm resistor > LED1 DIN > LED 1 DOUT > LED 2 DIN > LED 2 DOUT > LED 3 DIN > LED 3 DOUT > LED 4 DIN > LED 4 DOUT > LED 5 DIN > LED 5 DOUT > LED 6 DIN > LED 6 DOUT > LED 7 DIN > LED 7 DOUT > LED 8 DIN > LED 8 DOUT > LED 9 DIN > LED 9 DOUT is conected to nothing since there are no other LEDs.

Power Line for the LED is Pico VBUS > LED VDD for all LEDs
Ground line is GND > LED VSS for all LEDs

**OLED Display Wiring**

The OLED Screen uses 12C:

OLED VCC > 3V3 on Pico
OLED GND > Pico GND
OLED SCL > Pico I2C SCL Pin
OLED SDA > Pico I2C SDA Pin

**Potentiometer Wiring**

The Slide potentiometer is connected as a analog input:

Side with single pin > 3V3 on Pico
Square hole pin > GND on Pico 
Last Pin > Pico ADC Pin


**How to use**

Once assembled & programed, the macropad can be used as a custom keyboard accessory. Each key can be assigned to shortcuts, macros, or commands. The rotary encoder can be used for volume, scrolling, or schanging settings. The Slide Potentiometer can be programed as a analog control, for things such as brightness, volume, or other custom input.

The RGB LEDs can be programmed for static colors, animations, or per-key effects. The OLED can display information such as mode, volume, or custom text.

**Future improvements**
1. Adding custom oled animations
2. Adding more RGB like a underglow
3. Improving case design
4. Making the PCB smaller with more compact wiring
5. Adding hot-swap switch sockets.

BOM (Bill Of Materials)

| **Component** | **Quantity** | **Price** | **Link** |
| Raspberry Pi Pico W | 1 | $6 | https://www.microcenter.com/product/650108/raspberry-pi-pico-w |
| Slide Potentiometer | 1 | $4.17 | https://www.aliexpress.us/item/3256804677836323.html?spm=a2g0o.order_list.order_list_main.17.412e1802YyiC0s&gatewayAdapt=glo2usa |  
| Rotary Encoder | 1 | $1.71 | https://www.aliexpress.us/item/3256807457768762.html?spm=a2g0o.order_list.order_list_main.23.412e1802YyiC0s&gatewayAdapt=glo2usa |
| .96in OLED Display | 1 | $2.83 | https://www.aliexpress.us/item/3256805954920554.html?spm=a2g0o.order_list.order_list_main.29.412e1802YyiC0s&gatewayAdapt=glo2usa |
| Rotary Cap (Optional) | 1 | $2.60 | https://www.aliexpress.us/item/2261799870168498.html?spm=a2g0o.order_list.order_list_main.35.412e1802YyiC0s&gatewayAdapt=glo2usa |
| 1N4148 DO-35 Diode | 9 | $1.17 | https://www.aliexpress.us/item/3256806021685533.html?spm=a2g0o.order_list.order_list_main.41.412e1802YyiC0s&gatewayAdapt=glo2usa |
| GATERON G PRO V3 3.0 Switch | 9 | $10.30 | https://www.aliexpress.us/item/3256810373229330.html?spm=a2g0o.order_list.order_list_main.47.412e1802YyiC0s&gatewayAdapt=glo2usa |
| SK6812 MINI-E LEDs | 9 | $3.29 | https://www.aliexpress.us/item/3256808405274987.html?spm=a2g0o.productlist.main.2.b26bhcC6hcC6ap&algo_pvid=2beda12f-d9cf-4384-922a-8b38e549f833&algo_exp_id=2beda12f-d9cf-4384-922a-8b38e549f833-1&pdp_ext_f=%7B%22order%22%3A%2219%22%2C%22eval%22%3A%221%22%2C%22fromPage%22%3A%22search%22%7D&pdp_npi=6%40dis%21USD%214.99%213.29%21%21%214.99%213.29%21%402101e8f317814070843542477ed33e%2112000045863230980%21sea%21US%216480927448%21X%211%210%21n_tag%3A-29911%3Bd%3A57939ebb%3Bm03_new_user%3A-29895&curPageLogUid=TwpPrRvrq6CR&utparam-url=scene%3Asearch%7Cquery_from%3A%7Cx_object_id%3A1005008591589739%7C_p_origin_prod%3A |
| 330 omh Resistor | 1 | $1.45 | https://www.aliexpress.us/item/2251832681907061.html?spm=a2g0o.productlist.main.2.383fd4mBd4mBI5&algo_pvid=6a9a3102-369a-46f7-a84b-bca3f28c6226&algo_exp_id=6a9a3102-369a-46f7-a84b-bca3f28c6226-1&pdp_ext_f=%7B%22order%22%3A%22214%22%2C%22eval%22%3A%221%22%2C%22fromPage%22%3A%22search%22%7D&pdp_npi=6%40dis%21USD%211.27%211.27%21%21%211.27%211.27%21%402103129f17814072495678610e4f2a%2165490438043%21sea%21US%216480927448%21X%211%210%21n_tag%3A-29911%3Bd%3A57939ebb%3Bm03_new_user%3A-29895&curPageLogUid=0f0I94nAdFd8&utparam-url=scene%3Asearch%7Cquery_from%3A%7Cx_object_id%3A32868221813%7C_p_origin_prod%3A |




























