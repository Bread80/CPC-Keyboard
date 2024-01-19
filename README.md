# Keyboard for Amstrad CPC Computers

This project is a keyboard suitable for direct connection to an Amstrad CPC. The PCB uses tactile switches which can easily be labelled with suitable legends for the keytops. The current layout is that of an Amstrad CPC6128, but the key matrix is the same across all machines. The only differences are in the connector types and pinouts.

This board has connectors which are compatible with:
* CPC464 with PCB keyboard (1x20 pin connector)
* CPC464 with membrane keyboard (2x10 pin connectors)
* CPC664 (1x20 pin connector) **Untested**
* CPC6128 (2x10 pin connectors)

Plus machines: I'm not clear whether they use the same keyboard pinout or not. As such I can't say whether this board works with them or not.

Sadly it's not practical to add mounting holes suitable for mounting the keyboard on top of the CPC mainboard.

The repository includes an SVG file with key legend. This is suitable for the open source [Inkscape](https://inkscape.org) software

## BoM

74x Key switches[1]: Alps Apline SKHCBEA010. Mouser no: 688-SKHCBEA010
74x Keytops + Keycaps[2][3]: Alps Alpine SK2AA00090. Mouser: 688-SK2AA00090
'Standard pin header' (2.54mm spacing)[4]
2x Shunts[4]
Connector(s) (to keyboard)[5]
Connector(s) (to CPC)[6]
Cable (keyboard to CPC)[7]
5x Standoffs, short)[8]: 13mm length, M3 x 0.5, 4.5mm OD, female/female. Mouser: M1260-3005-SS
5x Standoffs, long)[8]: 25mm, M3 x 0.5, 4.5mm OD, female/female. Mouser: 761-M1272-3005-SS
10x Screws[8]: M3 x 6mm. Mouser: 534-9191-3
--also-- key legend (printout)[9]

### Notes:
Mouser codes can be used at http://mouser.com
[1] PCB will accept any generic 12mm 'tactile switch'. The specified model allows a keytop + keycap to be attched. This enables a printed key legend to be used. The same design is available engineered for 'operating force' values. In my tests this model had the best feel.
[2] Other colours are available (for the keytops), product codes SK2AA000x0 where x is 6,7,8,9 (NOTE: other digits are different products!).
[3] This product code includes both keycap and keytop. These are also available separately, but the combined pack is slightly cheaper.
Consult the keyswitch data sheet for the full list of available options: https://www.mouser.co.uk/datasheet/2/15/SKHC-1370786.pdf

[4] For configuration jumpers. Source from ebay etc for sensible pricing. If you don't intend to change settings you can solder an offcut of wire instead.
[5] Unless you need to attach multiple machines your best option here is to directly solder wire to the board. Otherwise pin header is probably the most convenient. You'll either need 1x20 or 2x10 depending on the machine, plus 
[6] Options here depend on your machine. The 20-pin inline connect machines will accept 'Dupont' style connectors, pin header etc. The 2x10 matrix connectors are more of a pin. I've successfully used FPC/FFC cable. With some patience this can be persuaded into the connector. These cables only seem to be available in very short lengths but ribbon (etc) cable can be soldered to the other end to run to the keyboard. Obviously some insulation will be helpful on the joins to prevent it shorting against anything (or each other)! You'll need 2x 10-pin cables, 571-FSN-21A-10 is a suitable Mouser product code.
[7] Discreet cables or a length or ribbon cable is up to you. Not every line is connected but using a 20pin or 2x 10-pin ribbon cable saves you having to etsablish which aren't needed. Cable length is up to you but anything too short will make it difficult to position the keyboard where you want it. I'd suggest a /minimum/ of about eight inches (40cm).
[8] I use standoffs as feet to lift to board of the desk and give space for the wiring underneath. You can give the keyboard some 'raking' by using longer ones at the rear. another option is to use a male/female standoff as an extender. The board is engineered for M3 screws/threads. Note: The PCB has three rows of mounting holes but the central row has not proved necessary and I'll remove them if I do an update. Just use the top and bottom rows.
[9] Provided as an SVG suitable for Inkscape) in this here repository. If creating your own key legend, each key needs to be a maximum 10mm x 10mm

## Known Issues

* The keyswitches have a pair of small lugs on the underside. Fitting them would be easier if the board had siutable holes for them. As is it just needs some care to ensure each switch sits flag and true.

## Assembly guide

### Soldering:
* Pin header. Solder the pin header strips for the settings jumpers. Pin header can easily be snapped into short sections as needed.
* Start with the keyswitches. Mount them any way which fits the holes and you'll be okay! Note that there are small lugs on the underside which make them want to sit at an angle. I /strongly/ recommend taking some care to check they are sitting flat and level. My method is to solder a single leg on each, then inspect and rework as needed to level them. Once they're level solder the remaining pins.
* Connectors. Solder your preference of connector(s), or wire, to the rear of the board. The required connectors are as follows:
For a CPC464 with PCB keyboard: connector J1 (1x20 pin)
For a CPC464 with matrix keyboard: connectors J2 and J3 (2 of 1x10 pin)
For a CPC664: connector J4 (1x20 pin)
For a CPC6128: connectors J2 and J3 (2 of 1x10 pin)

### Keycaps:
* Print out the key legend sheet and cut up. Cutting as accurately to the lines as possible will be beneficial. If you have them available, using a cutting board, craft knife, and steel ruler will probably give a better finish than scissors.
* Before assembling the key top + key legend + key cap consult the assembly diagram at the bottom of page three of the datasheet: https://www.mouser.co.uk/datasheet/2/15/SKHC-1370786.pdf Note the recommended orientation of keytop to keycap and plan which way you'll need to assemble things so your legend ends up the correct way around!
* With the keycap (clear plastic piece) face down on the bench, insert the key legend (paper) face down. Then insert the keytop into the keycap, taking note of the corrent orientation with respect to the key legend.
* Attach the keytop/keycaps to the keyswitches.

### Configuration and Connection

All the connectors are orientated in the same way as those on the Amstrad motherboard. I.e. the pin(s) towards the top of rear of the keyboard PCB are those towards the rear of the motherboard PCB and, for the the dual 10-pin connectors, the right-most connector on the keyboard PCB (when viewed from the top) connects to the right-most connector on the motherboard PCB.

Configuration is *only* needed if using the pair of 10-pin connectors to connect to the motherboard. If connecting to a CPC464, short (with a 'shunt') JP2 and the left-most two pins of JP1. If connecting to a CPC6128 short JP3 and the two right-most pins of JP1. Note that when connecting to a CPC464 JP3 should be left open, when connecting to a CPC6128 JP2 should be left open.

## Keyboard legend file(s)

Keyboard legend files are in the 'legend' folder. The following designs/layouts are available. SVG files can be created, edited and printed with the open source Inkscape software. If you create anything new/interesting please contribute it back to the repository.

UK-CPC6128-with-464-colours.svg - Amstrad CPC6128 layout with UK legend using the colour scheme of an original Amstrad CPC464.

## Licence

My aim with this project is to share something potentially useful with the community but I don't want to see my work being exploited for profit.

Therefore, it's okay to have a board manufactured for your own use and sell off the spare boards for an amount to cover your costs and postage. If you want to sell boards, or derivatives, for profit or as part of a business then talk to me first.

## Contact

Website: https://bread80.com
Github: https://github.com/Bread80
Mastodon: https://mstdn.social/@bread80
Twitter: https://twitter.com/bread80com
