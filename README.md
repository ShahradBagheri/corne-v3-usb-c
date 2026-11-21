# Corne Cherry v3 with a USB-C split link

Open `corne-cherry.kicad_pro` in KiCad 9. The project contains both original PCB halves in the original panel. J1 and J3 are now GCT USB4105-GF-A receptacles at the inside edges.

## Connecting the keyboard

With the keyboard unpowered, connect the two ports marked **SPLIT ONLY** using a USB-C to USB-C cable that carries USB 2.0 data. Then connect one controller's own USB port to the computer. Disconnect the computer cable before plugging or unplugging the split cable. Keep both split ports away from computers, chargers, and other USB devices. Power the keyboard from one controller at a time.

The receptacles carry the original Corne single-wire serial protocol over the cable. They have no USB enumeration, Type-C role detection, power negotiation, or isolation. No firmware change is required for the stock wired Corne v3 serial configuration.

| Receptacle contacts | Function |
| --- | --- |
| A4, A9, B4, B9 | Shared controller supply (VCC and VDD on the two halves) |
| A1, A12, B1, B12 and shell | Ground |
| A6 and B6 | Original serial data (USB 2.0 D+ conductor) |
| D−, CC1, CC2, SBU1 and SBU2 | Open |

## Mechanical and electrical checks

All 753 original Edge.Cuts entities match the upstream board, including the perimeter, panel, and LED cutouts. The 170 other footprint placements and the mounting-hole geometry match the original. The USB-C plug shell and insertion opening have a different shape from the audio jack, so check the clearance of your specific case and plug.

KiCad 9 reports zero schematic ERC violations, zero PCB unconnected items, and zero schematic-to-PCB parity issues. The PCB still reports legacy outline, copper-to-edge, and other DRC findings on the original layout, and library mismatch warnings for customized footprints. The USB4105 hole-to-copper exception is scoped to the manufacturer's locating-hole and contact geometry within each connector. The board has not been fabricated or tested. Review the outline and DRC with your board house before ordering.

## Sources

- [Original Corne Cherry v3.0.0 release by foostan](https://github.com/foostan/crkbd/releases/tag/corne-cherry-v3.0.0), commit `ad3892b7500d9b15100ee98f2aa5c35297481b0f`.
- [Corne Cherry v3 build guide](https://github.com/foostan/crkbd/blob/main/docs/corne-cherry/v3/buildguide_en.md).
- [GCT USB4105 series drawing](https://gct.co/files/drawings/usb4105.pdf).

The original project and its bundled footprint library retain their respective license notices.

### Original case fit review

The original v3 PCB perimeter, mounting centers, switch positions and 1.6 mm PCB thickness carry over. Both new port centerlines are at panel Y = 76.05 mm. Relative to the old TRRS axes, move each case opening approximately 1.8 mm toward the thumb keys. The shell is 8.94 mm wide and projects approximately 0.99 mm past the PCB edge. Allow for the plug overmold if the wall is recessed.

The closest lower mounting-hole centers are 2.25 mm (left) and 2.27 mm (right) from the USB-C shell outline in plan. A 4 mm diameter cylindrical post at those centers therefore clears the shell by approximately 0.25 mm nominal. Wider bosses, case ribs, tolerances and cable overmolds require the specific enclosure drawing or a physical fit test.
