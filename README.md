# Guide: My DZ60 Layout & How to Use QMK Firmware
The files in this repository can be used to configure a keyboard with a DZ60 PCB and layout that includes arrow keys (example layout below)

For the complete layout and layers used on my keyboard, view the README that is located in the cpetz16 folder.

**A full guide on all things QMK (as well as all documentation) can be found on [here](https://beta.docs.qmk.fm/)**

```
 ,-----------------------------------------------------------------------------------------.
 | ESC |  1  |  2  |  3  |  4  |  5  |  6  |  7  |  8  |  9  |  0  |  -  |  =  |   Bkspc   |
 |-----------------------------------------------------------------------------------------+
 | Tab    |  Q  |  W  |  E  |  R  |  T  |  Y  |  U  |  I  |  O  |  P  |  [  |  ]  |    \   |
 |-----------------------------------------------------------------------------------------+
 | Caps    |  A  |  S  |  D  |  F  |  G  |  H  |  J  |  K  |  L  |  ;  |  '  |    Enter    |
 |-----------------------------------------------------------------------------------------+
 | Shift     |  Z  |  X  |  C  |  V  |  B  |  N  |  M  |  ,  |  .  |  /  |Shift|  U  | DEL |
 |-----------------------------------------------------------------------------------------+
 | Ctrl |  Cmd  |  Alt  |              Space                | Menu | FN1 |  L  |  D  |  R  |
 `-----------------------------------------------------------------------------------------'
```

## How to Use
---
There are 2 ways to use the files in this repository in order to flash a keyboard that uses a DZ60 PCB
1. Use a build environment on a local computer
2. Use the online graphical QMK Configurator

The online graphical configurator is extremely easy to use and ideal for those who are just looking to design keymaps and flash them to their board. Creating a local build environment and cloning the GitHub repository allows for greater levels of customization and control.

## Method 1: QMK Configurator (Online GUI)
---
A good tutorial for using this tool can be found on YouTube by [MechMerlin](https://www.youtube.com/watch?v=tx54jkRC9ZY)

There are two ways to use the [Configurator](https://config.qmk.fm/#/dz60/LAYOUT_60_ansi).
1. Click keys on the virtual keymap, then drag from the keycodes below to the desired location on the keymap (or click a key on the keymap and press the desired key on your keyboard)
2. Import a .json file with an already created keymap (the import button is to the right of the green KEYMAP. JSON box)

In this repository is a .json file titled `dz60_revised.json` that can be imported and already contains the layered keymap I use. Simply download the .json file, and then in QMK Configurator import it.

## Flashing Your Keymap to Your Keyboard

After creating your layout, click the green COMPILE button.

Once it is compiled, click the firmware button and save the .hex file. It might be beneficial to also save the `keymap.c` file, which can be found by clicking the KEYMAP ONLY button (in case you later decide to go about working on your keyboard configuration locally). You can also save the .json file by clicking the export button to the left of KEYMAP.JSON. This will allow you to easily import your keymap again in the future in order to make any changes or adjustments.

You are now ready to flash your keyboard. To do so, you need to download [QMK Toolbox](https://github.com/qmk/qmk_toolbox/releases). It is recommended to use the latest version (at this time it is version 0.0.11). Make sure to download the `qmk_toolbox.exe` file. After downloading and launching the program, click the 'Open' button and navigate to your .hex file.

Click 'Flash' on the right side of the window, and make sure to put your keyboard into RESET mode before plugging it in. In the case of the DZ60, this can be done by holding the `Spacebar` + `B` keys. After connecting the keyboard to your computer, you can release the RESET keys. 

After the flashing is completed, your keyboard should be all set and ready to use. A good way to test and make sure everything works is to use a [Keyboard Tester](https://config.qmk.fm/#/test).

## Method 2: Setting up a Local Build Environment (Using MSYS2)
---
A good tutorial series for this process can be found on YouTube by [Chokkan](https://www.youtube.com/watch?v=-HLV6mUxNnU&list=PLYEUsdlqPD2a3kzQgnF98Prj-4IzZJGYG)

Before cloning the QMK GitHub repository and setting up a layout, you need a build environment. First download [MSYS2](https://www.msys2.org/). From there you need to run a few commands to set up the environment for building and flashing .hex files to your keyboard. To do so, once MSYS2 is launched, run the following commands (commands are case sensitive):

- `pacman -Syu` (then 'y' to continue when prompted) after it completes, close MSYS2 and reopen it.
- `pacman -Su` (then 'y' to continue when prompted) it's worth doing another restart of MSYS2 at this point

Now, fork the [QMK repository](https://github.com/qmk/qmk_firmware) and clone it to your local machine. To keep things simple, I cloned the folder to my desktop, but you can put it wherever you want.

In MSYS2, navigate to the folder you cloned, which should be titled `qmk_firmware` (this can be done by typing cd for change directory followed by the path to the `qmk_firmware` folder) In my case the command would be: ` cd C:/Users/cpetz16/Desktop/qmk_firmware`

*IMPORTANT: On Windows, the default paths use "\\" but in order to navigate to the appropriate directory you need to use "/" in MSYS2*

After navigating to the QMK folder, run the following command to finish the setup process:

- `util/msys2_install.sh` (When prompted, just use the default installation settings, so 'Enter', 'Enter', 'y', 'A', 'y', 'y', 'y')

## Importing the Keymap

1. Go to the keyboards folder --> dz60 --> keymaps
2. Clone the cpetz16 folder in this repository and add it to the keymaps folder
3. The folder contains 3 files:
    - `keymap.c` which is where the layouts are defined
    - `rules.mk` which is used to define build options at the time the code is compiled
    - `README.md` is for giving an overview of the keyboard layout as well as any addtional information

    *The Rules and README files are optional and not required to build your layout and flash it to your keyboard*

## Creating Your Own Layout

You can also create your own layout or modify the layout above if it doesn't suit your needs. To do so, all you have to do is change the keycodes defined in the `keymap.c` file to the ones you prefer. All of the keycodes are listed in QMK's [documentation](https://beta.docs.qmk.fm/reference/keycodes).

To add function layers the keycode is `MO()` 

You can also chain keys together to create actions that only require a single key press. For example: `LCTL(LALT(KC_DEL))` chains DELETE + Left ALT + Left CONTROL in order to open the task manager by only pressing one key.

## Building and Flashing the Keymap to Your Keyboard

While inside the `qmk_firmware` folder in MSYS2 use the following command to build the .hex file for your keyboard

    make dz60:cpetz16

Alternatively, if you named the folder for your layout differently, use that name instead of 'cpetz16'. If your layout is formatted correctly, it will build without any errors.

To build and flash the keyboard all in one single command, instead use:

    make dz60:cpetz16:dfu

In order to flash the .hex file, you have to put your keyboard into RESET mode. On the DZ60 PCB, this can be done by holding `Spacebar` + `B`

After the keyboard is done being flashed, it should be all set and ready to use with your desired layout. Feel free to check that everything works by using a [Keyboard Tester](https://config.qmk.fm/#/test). If you decide to make any changes in the future, just edit the `keymap.c` file and re-build and flash it.

## Troubleshooting
---
If you experience an error while compiling your keymap, make sure to read the program's output in MSYS2. Within the error message will be the specific location where the problem exists. Sometimes it can be something as simple as a mispelled keycode.

If you have flashed your keyboard before and are simply looking for a new layout, holding `space` + `b` might not put your keyboard into RESET mode if you have already defined your own RESET key. In my case, its found by holding `FN1` + `Left Ctrl`.

If you experience an error when trying to flash the keyboard such as the following:

    Error: Bootloader not found. Try again in 5s

rather than constantly trying to unplug and plug the keyboard in, if you have already defined a RESET key (such as my example above) simply hit the reset while the error is on your screen and it should flash the keyboard.

### Additional Note
---
The intention of this repository is to be used as a reference for QMK as well as a centralized location containing references to various aspects of the process. I have written out this guide as a reminder for any future keyboard projects I undertake, as the general guidelines above can be applied to any other QMK-based keyboard. If you have any suggestions about improvements or edits to make to this guide, feel free to let me know. I will periodically review these contents whenever making any changes to my current keyboard or if I purchase another keyboard in the future.

Guide Version: 1

Last Revised: 7/22/2019
