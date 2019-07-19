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

To build:

    make dz60:cpetz16

To build and flash:

    make dz60:cpetz16:dfu

**IMPORTANT**

In order to flash the HEX file onto the keyboard, launch the build and flash command above, then hold `spacebar` + `b` to put the keyboard into RESET mode *or* use the predefined RESET key. If you get an error when trying to flash, such as

    Error: Bootloader not found. Trying again in 5s.

press the RESET key again at this point. The HEX file will then be flashed onto the keyboard.

## **Base Layer**
---

Layer 0 - ANSI layout with arrow keys

TASK is used to open task manager (using LCTL(LALT(KC_DEL)) chained together)

2 Function layers represented by FN1, FN2 (shown below)

```
 ,-----------------------------------------------------------------------------------------.
 | ESC |  1  |  2  |  3  |  4  |  5  |  6  |  7  |  8  |  9  |  0  |  -  |  =  |   Bkspc   |
 |-----------------------------------------------------------------------------------------+
 | Tab    |  Q  |  W  |  E  |  R  |  T  |  Y  |  U  |  I  |  O  |  P  |  [  |  ]  |    \   |
 |-----------------------------------------------------------------------------------------+
 | Caps    |  A  |  S  |  D  |  F  |  G  |  H  |  J  |  K  |  L  |  ;  |  '  |    Enter    |
 |-----------------------------------------------------------------------------------------+
 | Shift     |  Z  |  X  |  C  |  V  |  B  |  N  |  M  |  ,  |  .  |  /  | FN1 |  U  | TASK|
 |-----------------------------------------------------------------------------------------+
 | Ctrl |  Cmd  |  Alt  |              Space                | Menu | FN2 |  L  |  D  |  R  |
 `-----------------------------------------------------------------------------------------'
```

## **Function Layer**
---

Layer 1 - reached by FN1 key

Contains: 
- F keys
- Audio keys
- Some functionality-based keys
```
 ,-----------------------------------------------------------------------------------------.
 | ` ~ |  F1 |  F2 |  F3 |  F4 |  F5 |  F6 |  F7 |  F8 |  F9 | F10 | F11 | F12 |           |
 |-----------------------------------------------------------------------------------------+
 |        | Prev| NEXT|     |     |     |     |     |     |     | PGUP| PGDN|     |        |
 |-----------------------------------------------------------------------------------------+
 |         | VOL+|     |     |     |     |     |     |     |     |     |     |             |
 |-----------------------------------------------------------------------------------------+
 |           | VOL-|     |     |     |     |     |     |     |     |     |TRNS |     |     |
 |-----------------------------------------------------------------------------------------+
 |      |       | MUTE |               PLAY                | MYPC |      |     |     |     |
 `-----------------------------------------------------------------------------------------'
```
## **Settings Layer**
---

Layer 2 - reached by FN2 key
Contains:
- RGB underglow settings
- Key backlight settings
- Reset
```
 ,-----------------------------------------------------------------------------------------.
 |     | RGBT|RGBM+|RGBM-| HUE+| HUE-| SAT+| SAT-| VAL+| VAL-| SPD+| SPD-|     |           |
 |-----------------------------------------------------------------------------------------+
 |        | BL T| BL+ | BL- | BLBR|     |     |     |     |     |     |     |     |        |
 |-----------------------------------------------------------------------------------------+
 |         |     |     |     |     |     |     |     |     |     |     |     |             |
 |-----------------------------------------------------------------------------------------+
 |           |     |     |     |     |     |     |     |     |     |     |     |     |     |
 |-----------------------------------------------------------------------------------------+
 | RESET |      |       |                                   |     | TRNS |     |     |     |
 `-----------------------------------------------------------------------------------------'
```
