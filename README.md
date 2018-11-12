Read in Russian (https://github.com/iGorEremenko/VoodooI2C-trackpad-Asus-Vivobook-S510UA-and-Asus-Vivobook-X510UQ/blob/master/README-rus.md)

# Better Scroll VoodooI2C
> Fork of [VoodooI2C](https://github.com/pqml/VoodooI2C) to fix some gesture for ASUS Vivobook ELAN1300

<br><br>

## Disclaimer
This is a fork from [VoodooI2C](https://github.com/pqml/VoodooI2C) base on awsome [VoodooI2C](https://github.com/alexandred/VoodooI2C/tree/master/VoodooI2C) by [Alexandre Daoud](https://github.com/alexandred).

[pqml](https://github.com/pqml) has already fix some gesture for smoothest scroller, i just reEnable some gesture back!!

Ensure that the original VoodooI2C is working on your setup before using this fork. This fork only exists for cosmetic changes.

:warning: __Please, do not post issues on the original VoodooI2C repo concerning this fork. alexandred and the contributors of VoodooI2C have nothing to do with it.__ :warning:


I made this fork especially for my ASUS Vivobook S15 X510UQ (8th gen i7 and 16gb ram).
I only tested it on my own configuration, and this plugin is provided "as is" with no guarantee. Use it at your own risk!

I know almost nothing about GPIO / ACPI / DSDT related issues and will not be able to provide any help for this.

<br><br>

## Todo
- Add Zoom gesture (Mostly work)
- Add Double tap with two finger to launchPad
- Better mouse tracking

## Changes to the pqml's VoodooI2C

> Almost all changes are located in `VoodooI2CCSGestureEngine.cpp`.

- ReEnable 3 finger swipe function, fix two finger tap menu

<br>

## Changes to the original VoodooI2C
- Touching the trackpad with 2 fingers stop the scroll
- More precise deceleration of the momentum. The "linear progression" at the end of the momentum is attenuated.
- More consistant initial momentum after the touchend
- No more treshold for the scroll activation
  - Little two-fingers movements on the trackpad trigger the scroll too
- I also remove documentation and circleci from the fork
  - I don't use CI and I only did minor changes to the VoodooI2C core, so there is no need to duplicate the doc from the original repo

<br>

## Setup and Build

### 1. Requirements
- MacOS >= 10.11
- Xcode Command Line Tools
- Python 3 (for `cpplint`)

###### Xcode Installation

Install Xcode from the App Store

You maybe need to to this:

```sh
$ xcode-select --install
```

###### Python Installation

- Install [brew](https://brew.sh/)
- Use brew to install python: `brew install python`
- Add this line to `~/.bash_profile` (and `~/.zshrc` if needed):
  - `export PATH="/usr/local/opt/python/libexec/bin:$PATH"`


### 2. Clone the repository

```sh
$ git https://github.com/tctien342/VoodooI2C.git
$ cd VoodooI2C
```

### 3. Initialization

Use the `init.sh` script to install `cpplint`, the submodules and the 10.11 OSX SDK

```sh
$ sh init.sh
```

### 4. Build

Use the `build.sh` script to build the kext into the `build` folder.

```sh
$ sh build.sh
```

You can then copy/paste the compiled `build/VoodooI2C.kext` and one of its satellites to your EFI partition or to `System/Library/Extensions` using a kext utility. 

<br><br>

## License

This program is protected by the GPL license. Please refer to the `LICENSE.txt` file for more information

## Or download the latest release from this link
:warning: __ Asus-Vivobook-X510UQ it's not the original driver, use with caution, I warned, well all klatu to Virat and what's next))) __ :warning:


(https://github.com/iGorEremenko/VoodooI2C-trackpad-Asus-Vivobook-S510UA-and-Asus-Vivobook-X510UQ/releases/tag/2.0)
