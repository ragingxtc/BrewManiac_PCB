# BrewManiac_PCB
This is a repository for the "homebrew" PCB that I have created that will work with ![vitotai's](https://github.com/vitotai) excellent ![BrewManiac](https://github.com/vitotai/BrewManiacEsp8266) and ![BrewPiLess](https://github.com/vitotai/BrewPiLess) software for the D1 Mini.

# Main Objectives of the Design:
- Board size is limited to 99mm x 99mm, and is designed to be used with 2 layers of 1oz/sq. ft. copper. 100 x 100 with 1 oz is generally the cutoff for cheap PCB printing. For example, 10 of these boards can be printed for $16 by PCBway.com.
- Exclusive use of thru-hole components, because trying to solder SMD components at home sucks. All components used can be readily ordered for fairly cheap from Amazon, or for really cheap from overseas sources like aliexpress.
- Use of D1 Mini or D1 Mini Pro (with external wifi antenna), as the footprint for all D1 Minis is the same, unlike the NodeMCU.
- Multiple 12V input types: 5.5mm barrel plug or 5.08mm two pin header for a locking plug or terminal block.
- Mounting holes are designed around a Mean Well LRS-50-12 power supply. I will be designing some 3D-printed mounts that will secure both the power supply and the PCB.
- Integrated buck converters: 12V to 5V for powering the D1 Mini and various circuits, and a 12V variable buck that is linked only to the DC pump relay output for variable pump control (via slight modification of the buck converter). The buck converter for variable pump control can be bypassed.
- Integrated PCF8574 I/O expander to allow for four buttons to be used on the front panel if desired.
- Integrated buzzer.
- Extensive use of 1/8 watt 1k resistors. Only five resistors are not 1k.
- Pin headers for connections are designed to use 2.54mm JST-XH headers, for non-reversible self-locking connections.
- Almost all pin headers utilize a unique number of pins to prevent improper/dangerous connections.
- Two identical pin headers for dual DS18B20 temperature sensors.
- Pin header for I2C display.
- Expansion headers containing all unused pins from the D1 Mini and PCF8574 I/O expander to allow for future use.
- Test points for all voltages used on the board for initial setup of the power supply and buck converters, and troubleshooting when problems are encountered.
- Proper documentation silk-screened on the board itself for resistor values, transistor types, pin header outputs, etc.
- An optional header for use with an AMS1117 breakout in the event that the 3.3V power supply on the D1 Mini burns out.

# Multiple output configurations:
- Onboard relays to control 12V 3.2A outputs for use with DC recirculating pumps and heaters.
- A 5V low amp header to control a board-mounted external relay module for use with AC recirculating pumps and heaters. Mounting holes to mount an external 2-channel relay module directly to the board are provided, and nylon standoffs should be used to provide proper AC & DC isolation.
- Individual 12V output headers to be used with solid state relays and external automotive-type relays.
- All three output configurations are completely independent and can be mixed and matched to suite most hardware configurations. **However, only one configuration for each output can be safely utilized.** All outputs have their own LED indicator on board for initial setup/troubleshooting.
