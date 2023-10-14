# SYZYGY Breakout Flash with Level Shifters
SYZYGY Breakout Board with level shifters for any voltage flash chip. I wanted a way to experiment with flash without having to spin a new board for each footprint or solder yet another BGA or TSOP. Flash programmers with ZIF adapters seemed like the best choice and SYZYGY would make it compatible with a wide range of FPGA boards. So I combined the ZIF and SYZYGY then added a clock and level shifters. This is the mid range version of the other two SYZYGY flash breakout boards and requires 1.8V VIO to shift logic properly so do not change the request VIO in the SYZYGY DNA. It even works with ZUBoard 1CG's dumb VIO.

# Building Firmware
A prebuilt firmware has been provided in the 'firmware' directory. If you want to customize the SMART VIO then modify 'szg-flash-std.json' with the custom power values and use the official [SYZYGY tools](https://github.com/SYZYGYfpga/syzygy-tools/) repo to build the firmware. 
python ..\..\syzygy-tools\dna-tools\syzygy-tools.py -d ..\szg-dna\SZG-FLASH\szg-flash-std.json -f ..\..\syzygy-tools\pod-fw\avr-dna-fw-main.hex

# Fabrication
I use JLCPCB and OSH Park. I used the DRC rules for OSH Park so the board doesn't have any special fabrication requirements. Just pick your favorite PCB shop and color.

# FPGA Development
The board has silkscreen text with corresponding pins for Avnet's [ZUBoard 1CG](https://www.avnet.com/wps/portal/us/products/avnet-boards/avnet-board-families/zuboard-1cg/). If you use a different board then you'll have to change the silkscreen and generate new gerbers. Or you can just look up the pins for your board each time. Theoretically you can use this board with any FPGA dev board that has a SYZYGY connector then you could use the respective controller for your flash device OR find someway to expose it to AXI and PS to use it with flashrom. As I figure out specific tools that work well then I'll update this README with tutorials.

# BOM
You can find datasheets for each component in the datasheets directory. All of the components can be bought from Mouser or Digikey. 
* Epson SG5032VAN
* Texas Instrument TLV1117LV
* Texas Instrument TXS0108EQPWRQ1
* Aries 28-6554-11

# Future Work
I consider this board feature complete. As I find/create IP and software that works with this board then I'll update this README with tutorials on how to use them. Feel free to create a GitHub issue detailing your own success story or use case.

