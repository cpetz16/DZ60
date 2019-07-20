# (WIP) My DZ60 Layout & How to Use
The files in this repository can be used to configure a keyboard with a DZ60 PCB and layout that includes arrow keys (example layout below)

For the complete layout and different layers on my layout, view the README that is located in the cpetz16 folder.

**A full guide on all things QMK (as well as all documentation) can be found on [here](https://github.com/qmk/qmk_toolbox/releases)**

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

## How to Use
---
There are 2 ways to use the files in this repository in order to flash a keyboard that uses a DZ60 PCB
1. Use a build environment on a local computer
2. Use the online graphical QMK Configurator

The online graphical configurator is extremely easy to use and ideal for those who are just looking to design simple keymaps and flash them to their board. Creating a local build environment and cloning the GitHub repository allows for greater levels of customization and control.

### QMK Configurator (Online GUI)
---
A good tutorial for using this tool can be found on YouTube by [MechMerlin](https://www.youtube.com/watch?v=tx54jkRC9ZY)

There are two ways to use the [Configurator](https://config.qmk.fm/#/dz60/LAYOUT_60_ansi).
1. Click the keys on the keymap and then drag the keys from the keycodes below to the desired location (or simply click a key on the keymap and then press the desired key on your keyboard)
2. Import a .json file with an already defined keymap (the import button is to the right of the green KEYMAP.JSON box)

In this repository is a .json file titled `dz60_directional.json` that can be imported and already contains a layered keymap. Simply download the .json file, and then in QMK Configurator import it.

After creating your desired layout, click the green COMPILE button in the top right corner.

Once finished click the firmware button and save the .hex file. It might be beneficial to also save the `keymap.c` file, which can be found by clicking the KEYMAP ONLY button. You can also save the .json file by clicking the export button to the left of KEYMAP.JSON. This will allow you to easily import your keymap again in the future in order to make any changes or adjustments.

You are now ready to flash your keyboard. To do so, you need to download [QMK Toolbox](https://github.com/qmk/qmk_toolbox/releases). It is recommended to use the latest version (at this time it is version 0.0.11). Make sure to download the `qmk_toolbox.exe` file.

After downloading and launching the program, click the Open button and navigate to your previously created .hex file.

Click the Flash button on the top right side of the program, making sure to put your keyboard into RESET mode before plugging it in. In the case of the DZ60, this can be done by holding the `space` + `b` keys. After connecting the keyboard to your computer, you can release the RESET keys. 

After the flashing is completed, your keyboard should be all set and ready to use. A good way to test and make sure everything works is to used a [Keyboard Tester](https://config.qmk.fm/#/test).

### Cloning the GitHub Repository
---
A good tutorial series for this process can be found on YouTube by [Chokkan](https://www.youtube.com/watch?v=-HLV6mUxNnU&list=PLYEUsdlqPD2a3kzQgnF98Prj-4IzZJGYG)

1. Fork the [QMK repository](https://github.com/qmk/qmk_firmware) and clone it to your local machine
2. Go to the keyboards folder --> dz60 --> keymaps
3. Clone the cpetz16 folder in this repository and add it to the keymaps folder
4. The folder contains 3 files:
    - `keymap.c` which is where the layouts are defined
    - `rules.mk` which is used to define build options at the time the code is compiled
    - `README.md` is for giving an overview of the keyboard layout as well as any addtional information

    *The Rules and README files are optional and not required to build your layout and flash it to your keyboard* 

## Troubleshooting
---
If you have flashed your keyboard before and are simply looking for a new layout, holding `space` + `b` might not put your keyboard into RESET mode if you have defined a RESET key function. In my case, its found by holding `FN2` and then `Left Ctrl`.

If you experience an error when trying to flash the keyboard such as the following:

    Error: Bootloader not found. Try again in 5s

rather than constantly trying to unplug and plug the keyboard in, if you have already defined a RESET key (such as my example above) simply hit the reset while the error is on your screen and it should flash the keyboard.

### Additional Note
---
The intention of this repository is to be used as a reference for QMK as well as a centralized location containing references to various aspects of the process. I have written out this guide as a reminder for any future keyboard projects I undertake, as the general guidelines above can be applied to any other QMK-based keyboard. If you have any suggestions about improvements or edits to make to this guide, feel free to let me know. I will periodically review these contents whenever making any changes to my current keyboard or if I purchase another keyboard in the future. 
