<img src="https://github.com/Krangh1337/Mitte-Home/blob/main/images/mitte-logo.jpeg" width="25%" height="25%">
<br/>
This project aims for rewriting the NFC-tags used in the filter cartridges of the "Mitte Home" 3-in-1 watersystem.<br/><br/>
<p><b>Why</b></p>
<ul>
<li>The company went bankrupt without informing customers.</li>
<li>App is bricked: You can no longer see the remaining bottle fills of the cartridge and the CO2-bottle</li>
<li>You can no longer order new cartridges, which renders the whole device useless once the cartridge is seen as empty by the device.</li>
</ul>

# General product information
- Manufacturer: Mitte
- 3-in-1 system: water filter, enriching water with minerals, adds CO2 to water
- 3 CO2-levels: none, low, max
- CO2-pushes per level:
  - none: no CO2 added
  - low: 8 CO2-pushes per bottle
  - max: 16 CO2-pushes per bottle
- Cartridge names: Restore
- Minimum fill for a bottle: approx. 875 ml (checked with the water container)
- After 7 days or more without usage, the filter must be cleaned with a full bottle of water

# How the NFC-cartridges are working
1. Every cartidge has a built-in NFC-Chip which can be read with mobile apps, specialized devices like <a href="https://flipperzero.one">Flipper Zero</a> etc..
   - The NFC-Chip in the cartridge is located at the backside in the center as marked in the below image.
   - <img src="https://github.com/Krangh1337/Mitte-Home/blob/main/images/restore-cartridge.jpeg" width="25%" height="25%">
2. When a cartridge is inserted into the device, the cartridge is being locked in place by turning it into the locking mechanism.
3. After the cartridge has been locked in place, the NFC-Chip of the cartridge aligns with the NFC-Reader of the main device.
4. The NFC-Reader of the main device is marked in the image below.
   - <img src="https://github.com/Krangh1337/Mitte-Home/blob/main/images/device-nfc-reader.jpeg" width="25%" height="25%">
5. Every time a bottle is filled with water, the main-devices NFC-Reader exchanges information with the NFC-Chip in the cartridge, like remaining bottles, CO2-usage etc.

# Read contents of NFC-Chip on a cartridge and unlock the NFC-file with a Flipper Zero
TBD
