<img src="https://github.com/Krangh1337/Mitte-Home/blob/main/images/mitte-logo.jpeg" width="25%" height="25%">

This project aims to rewrite the NFC tags used in the filter cartridges of the "Mitte Home" 3-in-1 water system.

## Why
- The company went bankrupt without informing customers.
- The app is bricked: You can no longer see the remaining bottle fills of the cartridge or the CO2 bottle status.
- You can no longer order new cartridges, rendering the whole device useless once the cartridge is recognized as empty by the system.

# General Product Information
- **Manufacturer**: Mitte
- **System Type**: 3-in-1 system - water filtration, mineral enrichment, and CO2 infusion
- **CO2 Levels**: None, Low, Max
- **CO2 Pushes per Level**:
  - **None**: No CO2 added
  - **Low**: 8 CO2 pushes per bottle
  - **Max**: 17 CO2 pushes per bottle
- **Cartridge Names**: Active, Balance, Light, Restore
- **Minimum Bottle Fill**: Approx. 875 ml (checked with the water container)
- **Maintenance**: After 7 days or more without usage, the filter must be cleaned with a full bottle of water.

# How the NFC Cartridges work
1. Each cartridge has a built-in NFC chip, which can be read by mobile apps or specialized devices like the [Flipper Zero](https://flipperzero.one).
   - The NFC chip in the cartridge is located on the backside, in the center, as shown in the image below.
   - <img src="https://github.com/Krangh1337/Mitte-Home/blob/main/images/restore-cartridge.jpeg" width="25%" height="25%">
2. When a cartridge is inserted into the device, it is locked in place by turning it into the locking mechanism.
3. Once the cartridge is locked in place, the NFC chip on the cartridge aligns with the NFC reader of the main device.
4. The NFC reader of the main device is marked in the image below.
   - <img src="https://github.com/Krangh1337/Mitte-Home/blob/main/images/device-nfc-reader.jpeg" width="25%" height="25%">
5. Every time a bottle is filled with water, the main device's NFC reader exchanges information with the NFC chip in the cartridge, such as the number of remaining bottle fills, CO2 usage, etc.

## Read Contents of NFC Chip on a Cartridge and Unlock the NFC File with a Flipper Zero
The video below demonstrates how to read and unlock the NFC chip using a [Flipper Zero](https://flipperzero.one) running the custom [Unleashed firmware](https://github.com/DarkFlippers/unleashed-firmware).

https://github.com/user-attachments/assets/67dcc935-3bb4-4c1b-8d21-ea85570ee7d6

1. Select "NFC" and click on "Read".
2. Hold the Flipper Zero at the NFC chip location shown in image 1 of the "How the NFC Cartridges Work" section.
3. Wait for the device to read the NFC chip.
4. Click on "More" and select "Unlock".
5. Choose "Unlock with Reader".
6. Hold the Flipper Zero at the NFC reader location as shown in image 2 of section "How the NFC Cartridges work".
7. Wait for "Password Captured!" and click "Continue".
   - **WARNING**: Using an incorrect password may block the NFC chip!
8. Hold the Flipper Zero at the NFC chip location again.
9. Wait for "All Pages Are Unlocked!" to appear, then click "More".
10. Save the file with an identifiable name.
11. The file will be saved in the NFC app and can be accessed or exported from the SD card.

# Data Analysis
1. [Restore Cartridge Data Analysis](restore-cartridge/data-analysis.md)
