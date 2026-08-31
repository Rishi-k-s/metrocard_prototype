# MetroCard

A credit-card-sized PCB that shows real-time Kochi Metro data — a tiny, tappable transit map you can hold in your wallet.

Built by [Rishi Krishna](https://rishikrishna.com) / [Phenomi](https://phenomi.co). 

### Firmware
Checkout the metrocard [Firmware](https://github.com/Rishi-k-s/metrocard_firmware)

![Front of the card](images/Screenshot%20from%202026-08-07%2023-26-36.png)
![Back of the card](images/Screenshot%20from%202026-08-07%2023-26-43.png)

## About

The front silkscreen traces the full Kochi Metro **Phase 1** line, from Aluva to Thripunithura, with every station labeled. A 1206 LED sits at each of the 49 stations (`D00`–`D48`), so the map can light up to reflect train position or other live status along the line.

The back houses the electronics:

- **U1 — HT16K33** LED driver/matrix controller, addressed over **I²C**
- **J1** — 4-pin JST-EH connector breaking out `GND`, `5V`, `SDA`, `SCL`
- **JP2/JP3** — address jumpers (`A0`, `A1`) so multiple cards can share an I²C bus at different addresses
- **JP4/JP5** — I²C bus pass-through/jumpers
- Pull-up resistors and support passives for the I²C bus and driver

The card is standard credit-card dimensions, designed to be carried like any other card.

## Credits

- Metro map artwork inspired by Saneef Ansari
- Station and line data provided by Kochi Metro Rail Limited (KMRL)

## Repository contents

- `metrocard.kicad_pro` / `metrocard.kicad_pcb` / `metrocard.kicad_sch` — KiCad project, PCB layout, and schematic
- `metrocard.csv` — bill of materials
- `DRC.rpt` — latest design rule check report
- `images/` — renders/screenshots of the board
- `libs/`, `fp-lib-table`, `sym-lib-table` — local footprint/symbol library references

## Status

Revision 0.1 — first prototype (`Rev 0.1 | P1 060108026001`).

## License

Open source hardware, licensed under the [GNU GPL v3](LICENSE.md).
