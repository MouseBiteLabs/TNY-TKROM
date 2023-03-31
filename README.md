# TNY-TKROM

This is a custom TKROM board for the TinyTendo handheld console by <a href="https://github.com/Redherring32">Redherring32</a>. This board replicates <a href="https://www.nesdev.org/wiki/TKROM">standard TKROM NES boards</a>. TKROM boards are versatile and can make the majority of NES games that use the MMC3 mapper. TKROM uses CHR ROM and PRG RAM, and can have a backup battery if the game saves data on the PRG RAM. You can also make TLROM games with this board and remove the PRG RAM.

To use this board, you must remove an MMC3 mapper from an original NES board, and mount it where U1 is indicated. Since these boards use the 39SF040 for both PRG and CHR ROM, you should use FamiROM or some other utility to duplicate the ROM files to completely fill up the entire space on the Flash chip if necessary.

![image](https://user-images.githubusercontent.com/97127539/229019438-b57b42ae-9ddf-4004-bb34-828f756b974b.png)

(Note this image shows outdated board revisions.)

# Board Characteristics

- Thickness: 1.6 mm
- Surface Finish: ENIG
- Chamfered edges (45°)
- Compatible NES board types: TBROM, TEROM, TFROM, TLROM, **TKROM**, TSROM

# How to Use This Board

Here's a brief description on how to use this board with the TinyTendo. The process to make a board is similar to the preparation required for a regular-sized NES board. <a href="https://mousebitelabs.com/2017/06/25/how-to-make-an-nes-reproduction-cartridge">You may want to review the process of ROM preparation detailed on this page.</a> 

## Board Type Requirements

*Note: Do not solder U2 and U3 to the board before programming them.*

TKROM games require every component on the board. **DO NOT** solder bridge the pads labelled "NO BATT."

TSROM games are the same as TKROM, but without the battery, R1, D1, and D2. You must also bridge the two pads labelled "NO BATT" with solder.

TBROM, TEROM, TFROM, and TLROM games are the same as TSROM, but without U4, R2, R4, C5, and C6. You don't need to bridge the "NO BATT" pads.

## Flashing the Game

Prepare the ROM using FamiROM or other similar program, ensuring the entire 4Mbit space is filled for both the PRG and CHR components. You then need to program the 39SF040s before soldering them to the board. I use a FlashCat with a TSOP adapter to achieve this.

# Bill of Materials

Capacitors should be at least 16V rated. Resistor wattage is negligible.
C6 allows the use of modern Alliance-brand SRAM (55 ns). If you are using an older SRAM with slower access times, you may need to remove C6.

| Reference Designator  | Part Number/Value | Footprint  |
| ------------- | ------------- | ------------- |
| U1  | MMC3  | QFP44  |
| U2  | <a href="https://www.mouser.com/ProductDetail/Microchip-Technology/SST39SF040-70-4C-WHE?qs=Oo69DRhzroe%2FJKrgAmUE5Q%3D%3D">39SF040</a>  | TSOP32 (14mm) |
| U3  | <a href="https://www.mouser.com/ProductDetail/Microchip-Technology/SST39SF040-70-4C-WHE?qs=Oo69DRhzroe%2FJKrgAmUE5Q%3D%3D">39SF040</a>  | TSOP32 (14mm) |
| C1  | 22 uF | 1206  |
| C2-C5  | 0.1 uF | 0603  |
| C6  | 1 nF | 0603  |
| D1, D2  | <a href="https://www.mouser.com/ProductDetail/Vishay-Semiconductors/BAT54W-HG3-18?qs=BJlw7L4Cy79w8lzctLBe5g%3D%3D">BAT54</a> | SMA (SOD-123) |
| R1  | 1 kΩ | 0603  |
| R2  | 27 kΩ | 0603  |
| R3, R4  | 10 kΩ | 0603  |

# Revision History

## v1.2

- Added 1nF capacitor to fix MMC3 misbehavior with PRG RAM

## v1.1

- Flipped U2 and U3 text to stop myself from putting chips in backwards
- Changed clone mapper SMD133 to original MMC3
- Renamed board from TxROM to the more accurate TKROM
- Changed SRAM from 256K to 64K footprint

## v1.0

- Initial version

## License
<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/80x15.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>. You are able to copy and redistribute the material in any medium or format, as well as remix, transform, or build upon the material for any purpose (even commercial) - but you **must** give appropriate credit, provide a link to the license, and indicate if any changes were made.

©MouseBiteLabs 2022
