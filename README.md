# Debug ESP-32 setup
## Generic setup for ESP-32 debugging using the ESP-Prog JTAG board

[Blog Reference](https://medium.com/@manuel.bl/low-cost-esp32-in-circuit-debugging-dbbee39e508b)


The ESP-Prog Board is the official debugging board of Espressif, the designers of the ESP32 chip. The design is open source — schematic and PCB layout are available publicly. The boards can be bought from Ebay, Aliexpress and many local distributors and start at about USD 18 including shipping.


![esp-prog](/images/esp-prog.jpg)

## Connecting the board
To debug your program, connect the JTAG and ground pins to the ESP32 boards, e.g. using Dupont wires. The JTAG pins can be found on the biggest connector on the board:

![connection](/images/esp-progpinout.png)



## Pinout
| ESP-prog   | ESP-32 |
| ---------- | ------ |
| TDI        | GPIO12 |
| TDO        | GPIO15 |
| TCK        | GPIO13 |
| TMS        | GPIO14 |
| GND        | GND    |

Add the following lines to the *platformio.ini* file
```
debug_tool = esp-prog
debug_init_break = tbreak setup
```