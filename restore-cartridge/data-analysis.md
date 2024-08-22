# NFC Cartridge Data Analysis for Water Filter System

## Overview
This folder contains the analysis of the NFC data extracted from a **Restore** cartridge.  
The system tracks cartridge usage, CO2 consumption, and other internal parameters.

The main focus areas of the analysis are:
1. **Consumption Counter**: Tracks the number of bottles filtered by the cartridge.
2. **CO2 Consumption**: Captures the data for different CO2 levels and their respective usage patterns on certain memory pages.
3. **Expiration and Usage Duration**: Tracks expiration data and the usage duration within 3 months after activation.

The NFC files in this directory were collected:
- After one full bottle was filled with water through the cartridge.

### Filename examples:
- **Format:** *ddmm_bottlenumber_CO2-level_keystate*
    - `1508_1_n_locked`: 15th of August, bottle 1 of that day, no CO2, NFC file is password protected.
    - `1608_2_l_unlocked`: 16th of August, bottle 2 of that day, low CO2, NFC file is unlocked.
    - `1709_3_m_locked`: 17th of September, bottle 3 of that day, maximum CO2, NFC file is password protected.

### Cartridge Information
- **Lot number:** MHO0523A
- **Production date:** 23-05-11
- **Capacity:** 250 Bottles
- **Expiration:** End of 2025
- **Usage duration:** Within 3 months after activation.

---

## Cartridge Consumption Counter

The consumption counter is likely stored on **Pages 28-29** of the NFC chip. This counter increments by `1` after each bottle is processed.

| File                  | CO2 Level | Page 28          | Page 29          | Observation            |
|-----------------------|-----------|------------------|------------------|------------------------|
| `1508_1_l_unlocked`    | Low       | 14 B0 00 **BA**  | BD 95 00 **BA**  | Initial value          |
| `1508_2_l_unlocked`    | Low       | 14 B0 00 **BB**  | C5 95 00 **BB**  | +1 after a bottle      |
| `1608_1_l_unlocked`    | Low       | 14 B0 00 **BC**  | C5 95 00 **BC**  | +1 after a bottle      |
| `1608_2_l_unlocked`    | Low       | 14 B0 00 **BD**  | CD 95 00 **BD**  | +1 after a bottle      |
| `1608_3_l_unlocked`    | Low       | 14 B0 00 **BE**  | CD 95 00 **BE**  | +1 after a bottle      |
| `1708_1_l_unlocked`    | Low       | 14 B0 00 **BF**  | BD 95 00 **BF**  | +1 after a bottle      |
| `1708_2_l_unlocked`    | Low       | 14 B0 00 **C0**  | CD 95 00 **C0**  | +1 after a bottle      |
| `1708_3_m_unlocked`    | Max       | 14 B0 00 **C1**  | D5 95 00 **C1**  | Max CO2 increment      |
| `1708_4_l_unlocked`    | Low       | 14 B0 00 **C2**  | D5 95 00 **C2**  | +1 after a bottle      |
| `1808_1_l_unlocked`    | Low       | 14 B0 00 **C3**  | D5 95 00 **C3**  | +1 after a bottle      |
| `1808_2_m_unlocked`    | Max       | 14 B0 00 **C4**  | D5 95 00 **C4**  | Max CO2 increment      |
| `1808_3_l_unlocked`    | Low       | 14 B0 00 **C5**  | DD 95 00 **C5**  | +1 after a bottle      |
| `1808_4_l_unlocked`    | Low       | 14 B0 00 **C6**  | DD 95 00 **C6**  | +1 after a bottle      |
| `1908_1_l_unlocked`    | Low       | 14 B0 00 **C7**  | DD 95 00 **C7**  | +1 after a bottle      |
| `1908_2_l_unlocked`    | Low       | 14 B0 00 **C8**  | E5 95 00 **C8**  | +1 after a bottle      |
| `2008_1_m_unlocked`    | Max       | 14 B0 00 **C9**  | ED 95 00 **C9**  | Max CO2 increment      |
| `2008_2_l_unlocked`    | Low       | 14 B0 00 **CA**  | ED 95 00 **CA**  | +1 after a bottle      |
| `2108_1_n_unlocked`    | None      | 14 B0 00 **CB**  | ED 95 00 **CB**  | No CO2 added           |
| `2108_2_l_unlocked`    | Low       | 14 B0 00 **CC**  | ED 95 00 **CC**  | +1 after a bottle      |
| `2108_3_l_unlocked`    | Low       | 14 B0 00 **CD**  | F5 95 00 **CD**  | +1 after a bottle      |
| `2208_1_l_unlocked`    | Low       | 14 B0 00 **CE**  | F5 95 00 **CE**  | +1 after a bottle      |

---

## CO2 Consumption Data

The CO2-related data seems to be stored on **Pages 30-33**. Significant changes can be observed in these pages depending on the CO2 level used for each bottle. The hypothesis is that these values represent the consumption of CO2 pulses or related system parameters.

| File                  | CO2 Level | Page 30          | Page 31          | Page 32          | Page 33          | Observation                     |
|-----------------------|-----------|------------------|------------------|------------------|------------------|---------------------------------|
| `1508_1_l_unlocked`    | Low       | BE 77 8B 81      | 44 F4 C1 B8      | 93 00 01 EA      | D4 7C A7 3E      | Initial Low CO2 bottle          |
| `1508_2_l_unlocked`    | Low       | 6E D4 71 60      | 5B 1A 7A 89      | FA C2 2C D7      | 3F C9 BA 8A      | New values after bottle 2       |
| `1608_1_l_unlocked`    | Low       | 6E D4 71 60      | 5B 1A 7A 89      | FA C2 2C D7      | 3F C9 BA 8A      | Stable after Low CO2 bottle     |
| `1608_2_l_unlocked`    | Low       | 6E D4 71 60      | 5B 1A 7A 89      | FA C2 2C D7      | 3F C9 BA 8A      | Stable after Low CO2 bottle     |
| `1608_3_l_unlocked`    | Low       | 6E D4 71 60      | 5B 1A 7A 89      | FA C2 2C D7      | 3F C9 BA 8A      | Stable after Low CO2 bottle     |
| `1708_1_l_unlocked`    | Low       | BE 77 8B 81      | 44 F4 C1 B8      | 93 00 01 EA      | D4 7C A7 3E      | Initial Low CO2 bottle          |
| `1708_2_l_unlocked`    | Low       | 6E D4 71 60      | 5B 1A 7A 89      | FA C2 2C D7      | 3F C9 BA 8A      | New values after bottle 2       |
| `1708_3_m_unlocked`    | Max       | D6 89 AC C3      | CC F3 A4 41      | 19 CC 57 5B      | 7D 43 72 CF      | Max CO2: Significant changes    |
| `1708_4_l_unlocked`    | Low       | 5A 15 42 A5      | E3 66 6E D3      | 60 01 14 21      | 3C C5 B1 E0      | Stable after Low CO2 bottle     |
| `1808_1_l_unlocked`    | Low       | 5A 15 42 A5      | E3 66 6E D3      | 60 01 14 21      | 3C C5 B1 E0      | Stable after Low CO2 bottle     |
| `1808_2_m_unlocked`    | Max       | D6 89 AC C3      | CC F3 A4 41      | 19 CC 57 5B      | 7D 43 72 CF      | Max CO2: Significant changes    |
| `1808_3_l_unlocked`    | Low       | D6 89 AC C3      | CC F3 A4 41      | 19 CC 57 5B      | 7D 43 72 CF      | Stable after Low CO2 bottle     |
| `1808_4_l_unlocked`    | Low       | 5A 15 42 A5      | E3 66 6E D3      | 60 01 14 21      | 3C C5 B1 E0      | Stable after Low CO2 bottle     |
| `1908_1_l_unlocked`    | Low       | 5A 15 42 A5      | E3 66 6E D3      | 60 01 14 21      | 3C C5 B1 E0      | Stable after Low CO2 bottle     |
| `1908_2_l_unlocked`    | Low       | AA FE 1A 28      | 78 75 63 AE      | 96 0B 77 3D      | D3 92 12 C5      | Significant changes after bottle|
| `2008_1_m_unlocked`    | Max       | AD 90 8F 05      | 5A 3A B8 2B      | 8B C2 63 2A      | 4A C6 19 2E      | Max CO2: Significant changes    |
| `2008_2_l_unlocked`    | Low       | AD 90 8F 05      | 5A 3A B8 2B      | 8B C2 63 2A      | 4A C6 19 2E      | Stable after Low CO2 bottle     |
| `2108_1_n_unlocked`    | None      | AD 90 8F 05      | 5A 3A B8 2B      | 8B C2 63 2A      | 4A C6 19 2E      | No CO2 added                    |
| `2108_2_l_unlocked`    | Low       | 88 64 93 D5      | FF 1A EF C7      | ED D7 97 09      | 77 97 91 F3      | Stable after Low CO2 bottle     |
| `2108_3_l_unlocked`    | Low       | 88 64 93 D5      | FF 1A EF C7      | ED D7 97 09      | 77 97 91 F3      | Stable after Low CO2 bottle     |
| `2208_1_l_unlocked`    | Low       | D9 38 64 DB      | 38 03 E7 B1      | 20 D8 70 88      | 13 40 10 99      | Stable after Low CO2 bottle     |

### Observations
- **Pages 28-29** seem to consistently track the total number of bottles processed by the cartridge.
- **Pages 30-33** show significant changes depending on the CO2 level used and possibly track the number of CO2 pulses or other dynamic parameters.
- The values on **Pages 30-33** differ significantly between Low and Max CO2, which might indicate CO2 consumption per bottle.
- **No CO2 values** are stable across the related pages, reflecting no additional CO2 consumption.

### Hypotheses
1. **Pages 28-29** serve as the main consumption counter for the cartridge.
2. **Pages 30-33** could be tracking CO2 consumption (measured by the number of CO2 pulses) or another internal parameter that changes dynamically with usage.
3. Changes between Low and Max CO2 are reflected in significantly different HEX values on these pages, indicating resource consumption.

---

## Next Steps
1. **Further Data Collection**: Continue gathering data from additional bottles to further refine the understanding of the role of pages 30-33.
2. **CO2 Pulse Tracking**: Investigate whether the number of CO2 pulses (8 for Low, 17 for Max) is directly represented by the changes in pages 30-33.
3. **Analysis of Static Pages**: Explore the static pages (34-39) to understand their role in the system and whether they are tracking long-term parameters or configuration data.
