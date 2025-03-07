[![Build Status](https://travis-ci.org/Infineon/XMC-for-Arduino.svg?branch=master)](https://travis-ci.org/Infineon/XMC-for-Arduino)
# Infineon's XMC Microcontroller Boards for Arduino

This repository integrates [Infineon's](https://www.infineon.com/) XMC microcontrollers into the [Arduino IDE](https://www.arduino.cc/en/main/software) and [PlatformIO IDE](https://platformio.org/platformio-ide?utm_source=github&utm_medium=xmc-for-arduino).

## Contents
- [Infineon's XMC Microcontroller Boards for Arduino](#infineons-xmc-microcontroller-boards-for-arduino)
  - [Contents](#contents)
  - [Supported Microcontroller Boards](#supported-microcontroller-boards)
  - [Additional Information](#additional-information)
  - [Installation Instructions](#installation-instructions)
    - [Prework for SEGGER J-Link](#prework-for-segger-j-link)
    - [Using Arduino IDE](#using-arduino-ide)
      - [Separation of release packages from version 2.0.0 onwards](#separation-of-release-packages-from-version-200-onwards)
    - [Using PlatformIO IDE](#using-platformio-ide)
  - [Contributing and Third Party Libraries](#contributing-and-third-party-libraries)
  - [Additional Contributors](#additional-contributors)

## Supported Microcontroller Boards

* [XMC1100 XMC 2Go](https://www.infineon.com/cms/en/product/evaluation-boards/kit_xmc_2go_xmc1100_v1/)
* [XMC1100 Boot Kit](https://www.infineon.com/cms/en/product/evaluation-boards/kit_xmc11_boot_001/)
* [XMC1300 Boot Kit](https://www.infineon.com/cms/de/product/evaluation-boards/kit_xmc13_boot_001/)
* [XMC1400 Kit for Arduino](https://www.infineon.com/cms/en/product/evaluation-boards/kit_xmc1400_arduino/)
* [XMC4200 Platform 2Go](https://www.infineon.com/cms/en/product/evaluation-boards/kit_xmc_plt2go_xmc4200/)
* [XMC4400 Platform 2Go](https://www.infineon.com/cms/en/product/evaluation-boards/kit_xmc_plt2go_xmc4400//)
* [XMC4700 Relax Kit](https://www.infineon.com/cms/en/product/evaluation-boards/kit_xmc47_relax_v1/)

## Additional Information

Please visit also the Wiki for additional information, e.g. datasheets, pin out diagrams, etc.:

[XMC-for-Arduino Wiki](https://github.com/Infineon/XMC-for-Arduino/wiki)

* Page for [XMC1100 XMC 2Go](https://github.com/Infineon/XMC-for-Arduino/wiki/XMC-2Go)
* Page for [XMC1100 Boot Kit](https://github.com/Infineon/XMC-for-Arduino/wiki/XMC1100-Boot-Kit)
* Page for [XMC1300 Boot Kit](https://github.com/Infineon/XMC-for-Arduino/wiki/XMC1300-Boot-Kit)
* Page for [XMC1400 Kit for Arduino](https://github.com/Infineon/XMC-for-Arduino/wiki/XMC1400-Kit-for-Arduino)
* Page for [XMC4200 Platform 2Go](https://github.com/Infineon/XMC-for-Arduino/wiki/XMC4200-Platform2Go)
* Page for [XMC4400 Platform 2Go](https://github.com/Infineon/XMC-for-Arduino/wiki/XMC4400-Platform2Go)
* Page for [XMC4700 Relax Kit](https://github.com/Infineon/XMC-for-Arduino/wiki/XMC4700-Relax-Kit)

Additionally, please consult the [releases](https://github.com/Infineon/XMC-for-Arduino/releases) for information about the changes and new versions.

## Installation Instructions

### Prework for SEGGER J-Link

In order to use and program the Infineon XMC microcontrollers in the Arduino IDE, [SEGGER J-Link](https://www.segger.com/downloads/jlink) must be installed on your PC. Please follow this link to [SEGGER J-Link](https://www.segger.com/downloads/jlink) and install the J-Link Software and Documentation Pack for your operating system.
If you have already installed '[DAVE™ - Development Platform for XMC™ Microcontrollers](https://infineoncommunity.com/dave-download_ID645)', you can skip this step as the respective drivers/programs are already installed on your system.

![J-Link](https://raw.githubusercontent.com/infineon/assets/master/Pictures/J-Link_Packages.png)

**Note:** The XMC-for-Arduino BSP installs the **XMC Flasher** tool used to flash the compiled firmware (.hex) into the XMC device. However this tool requires **Java(TM) SE Runtime Environment** to be installed in the host system. Java(TM) SE Runtime Environment version **1.8.0** is known to be compatible with the tool.  

### Using Arduino IDE

![Preferences](https://raw.githubusercontent.com/infineon/assets/master/Pictures/Preferences.png)

Paste the following URL into the 'Additional Boards Manager URLs' input field under **File** > **Preferences** to add Infineon's microcontroller boards to the Arduino IDE.


https://github.com/Infineon/XMC-for-Arduino/releases/latest/download/package_infineon_index.json

Easier to copy (no clickable link):

```
https://github.com/Infineon/XMC-for-Arduino/releases/latest/download/package_infineon_index.json
```

![Adding a Board JSON](https://raw.githubusercontent.com/infineon/assets/master/Pictures/Preferences_JSON.png)

To install the boards, please navigate to **Tools** > **Board** > **Boards Manager...** and search for XMC. You will find options to install the board files for the microcontrollers. Click "Install" to add the boards to your Arduino IDE.

![Infineon Board Entry](https://raw.githubusercontent.com/infineon/assets/master/Pictures/Boards_Manager_Entry.png)

**Note:** For information on separation of release packages from version 2.0.0 onwards, see [below](#Separation-of-release-packages-from-version-2.0.0-onwards). 

In the boards list **Tools** > **Board**, the XMC microcontroller boards are added and can be used from now on.

![Board List](https://raw.githubusercontent.com/infineon/assets/master/Pictures/Board_List.png)

**Important Notes**

* This integration will only work for Arduino IDE >=1.5
* The XMC1100 Boot Kit has limitations if compared to the official Arduino boards (consult the [XMC-for-Arduino Wiki](https://github.com/Infineon/XMC-for-Arduino/wiki) for more information)
* Refer also to the LICENSE.md/txt file for further information
* Arduino 1.8.0 IDE might have problems with the XMC-for-Arduino releases
* XMC-for-Arduino support for 'arm-linux-gnueabihf' only until version 1.1.


#### Separation of release packages from version 2.0.0 onwards

Certain obsolete boards (see wiki) and non-functional libraries were removed from the board support package for the release version 2.0.0, alongwith some other major changes (see release notes). However, in order to support legacy code, these removed boards/libraries are still available as a part of release version 1.7.0. Hence, the release packages have been split as shown in the pictures below.

![Board Manager](https://raw.githubusercontent.com/Infineon/Assets/version-2.x/Pictures/Boards_Manager_Entry_v2.png)

The boards until version 1.7.0 have been clubbed under *XMC Family V1.x*.  

![Board list v1x](https://raw.githubusercontent.com/Infineon/Assets/version-2.x/Pictures/Board_List_v1x.png.jpg)

Any new board or feature integration will only be done in the *XMC Family V2.x*

![Board list v1x](https://raw.githubusercontent.com/Infineon/Assets/version-2.x/Pictures/Board_List_v2x.png.jpg)


### Using PlatformIO IDE

- [What is PlatformIO?](http://docs.platformio.org/en/latest/what-is-platformio.html?utm_source=github&utm_medium=xmc-for-arduino)
- [PlatformIO IDE](http://platformio.org/platformio-ide?utm_source=github&utm_medium=xmc-for-arduino)
- [PlatformIO Core (CLI)](http://docs.platformio.org/en/latest/core.html?utm_source=github&utm_medium=xmc-for-arduino) (command line tool)
- [Integration with Cloud and Desktop IDEs](http://docs.platformio.org/en/latest/ide.html?utm_source=github&utm_medium=xmc-for-arduino) -
  Cloud9, Codeanywhere, Eclipse Che (Codenvy), Atom, CLion, Eclipse, Emacs, NetBeans, Qt Creator, Sublime Text, VIM, Visual Studio, and VSCode
- [Project Examples](https://github.com/Infineon/platformio-infineonxmc/tree/master/examples)

## Contributing and Third Party Libraries

To contribute enhancements, fixes and the like see *Contributors.md*. in root folder

Third Party or external library maintainers see *Libraries.md*. in root folder
    
Also see [Wiki](https://github.com/Infineon/XMC-for-Arduino/wiki) for any additional information

## Additional Contributors

* [Paul Carpenter](https://github.com/techpaul)
