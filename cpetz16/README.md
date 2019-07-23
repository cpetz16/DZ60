# My keymap for DZ60 with arrow keys
Keyboard specs: 
- PCB: DZ60 (Layout 5 if ordered preassembled)
- Plate: Aluminum
- Case: Tofu Acrylic
- Switches: Zealios V2 62g (Tactile switches with similar actuation force to Cherry MX Blacks)
- Keycaps: DSA Seafoam keyset
- Stablizers: GMK Screw In
- Backlight: White LEDs
- USB-C

*All parts with the exception of keycaps can be found on KBDFans website*

## **Base Layer**
---

Layer 0 - ANSI layout with arrow keys

Function layer represented by FN1 (Shown below)

```
 ,-----------------------------------------------------------------------------------------.
 | ESC |  1  |  2  |  3  |  4  |  5  |  6  |  7  |  8  |  9  |  0  |  -  |  =  |   Bkspc   |
 |-----------------------------------------------------------------------------------------+
 | Tab    |  Q  |  W  |  E  |  R  |  T  |  Y  |  U  |  I  |  O  |  P  |  [  |  ]  |    \   |
 |-----------------------------------------------------------------------------------------+
 | Caps    |  A  |  S  |  D  |  F  |  G  |  H  |  J  |  K  |  L  |  ;  |  '  |    Enter    |
 |-----------------------------------------------------------------------------------------+
 | Shift     |  Z  |  X  |  C  |  V  |  B  |  N  |  M  |  ,  |  .  |  /  | RSft|  U  | DEL |
 |-----------------------------------------------------------------------------------------+
 | Ctrl |  Cmd  |  Alt  |              Space                | PSCR | FN1 |  L  |  D  |  R  |
 `-----------------------------------------------------------------------------------------'
```

## **Function Layer**
---

Layer 1 - reached by FN1 key

Contains: 
- F keys
- Audio keys
- RGB underglow settings
- Key backlight settings
- Some functionality-based keys
- RESET

```
 ,-----------------------------------------------------------------------------------------.
 | ` ~ |  F1 |  F2 |  F3 |  F4 |  F5 |  F6 |  F7 |  F8 |  F9 | F10 | F11 | F12 |           |
 |-----------------------------------------------------------------------------------------+
 |        | Prev| NEXT|     | RGBT|RGBM+|RGBM-|     |     | BL T| BL+ | BL- |     |        |
 |-----------------------------------------------------------------------------------------+
 |         | VOL+|     |     | HUE+| HUE-| SAT+| SAT-|     |     |     |     |             |
 |-----------------------------------------------------------------------------------------+
 |           | VOL-|     |     | VAL+| VAL-| SPD+| SPD-|     |     |     |     | PGUP|     |
 |-----------------------------------------------------------------------------------------+
 | RESET |      | MUTE |               PLAY                | MYPC | TRNS |     | PGDN|     |
 `-----------------------------------------------------------------------------------------'
```

To build:

    make dz60:cpetz16

To build and flash:

    make dz60:cpetz16:dfu

Last Revised: 7/22/2019
