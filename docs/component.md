---
title: Component Selection
---

## Required & Selected Components

Component Name      | Selection
--------------------|-----------------
Microcontroller     | PIC18F47Q10-I/PT  
Volatage Regulator  | AP63203WU-7  
Hall Effect Sensor  | AS5600L-ASOM SOIC LF T&RDP  
Temperature Sensor  | HIH6030-021-001  
Humidity Sensor     | HIH6030-021-001  
Air Pressure Sensor | LPS22HBTR
Comparator          | MCP6541RT-E/OT

### Microcontroller

Option |  Pros | Cons
---|---|---
![micro1](./assets/images/micro1.jfif)<br>[PIC18F47Q10-I/PT](https://www.digikey.com/en/products/detail/microchip-technology/PIC18F47Q10-I-PT/10187786) <br> $1.65/each<br>[datasheet](https://ww1.microchip.com/downloads/en/DeviceDoc/PIC18F27-47Q10-Data-Sheet-40002043E.pdf) | - Familiar due to use in course<br><br>- 128kB Memory<br><br>- 36 IO pins<br><br>- Fast 64MHz processing<br><br>- Inexpensive | - Low power range<br><br>- Could be limiting with amount of peripherals
![micro2](./assets/images/micro2.jpg)<br>[PIC24FJ256GA705-I/PT](https://www.digikey.com/en/products/detail/microchip-technology/PIC24FJ256GA705-I-PT/6565015) <br> $2.13/each<br>[datasheet](https://ww1.microchip.com/downloads/en/DeviceDoc/PIC24FJ256GA705-Family-Data-Sheet-DS30010118E.pdf) | - Supports 16-bit<br><br>- 256kB Memory<br><br>- 40 IO pins | - Unfamiliar product family<br><br>- Unnecessary for requirements<br><br>- Small operational voltage range
![micro3](./assets/images/micro3.jfif)<br>[PIC18LF8723-I/PT](https://www.digikey.com/en/products/detail/microchip-technology/PIC18LF8723-I-PT/1681042) <br> $16.85/each<br>[datasheet](https://ww1.microchip.com/downloads/en/DeviceDoc/39894b.pdf) | - 128kB Memory<br><br>- 70 IO pins<br><br>- Allows for more redundant wiring | - Excessive connection points<br><br>- Expensive<br><br>- Overkill for requirements

Selected Component: Option 1 - PIC18F47Q10-I/PT  
Rational: This option satisfies the requirements for my team's microcontroller. It is also the easiest to work with as it is used compiously within our course and is familiar. This option also uses very little of the budget and allows for funds to be allocated elsewhere.

### Voltage Regulator

Option | Pros | Cons
---|---|---
![pwr1](./assets/images/pwr1.jpg)<br>[AP63203WU-7](https://www.digikey.com/en/products/detail/diodes-incorporated/AP63203WU-7/9858426)<br>$1.38/each<br>[datasheet](https://www.diodes.com/assets/Datasheets/AP63200-AP63201-AP63203-AP63205.pdf) | - Large input voltage range<br><br>- 2A output capacity<br><br>- Simple application circuitry<br><br>- Reduced electromagnetic interference | - Smaller operational temperature range<br><br>- Small package
![pwr2](./assets/images/pwr2.jfif)<br>[TPS62132RGTR](https://www.digikey.com/en/products/detail/texas-instruments/TPS62132RGTR/2786726)<br>$1.71/each<br>[datasheet](https://www.ti.com/lit/ds/symlink/tps62130.pdf?HQS=dis-dk-null-digikeymode-dsf-pf-null-wwe&ts=1738923213197) | - 3A output capacity<br><br>- High switching speed<br><br>- Lowest minimum input voltage<br><br>- Provides short circuit protection | - Smaller input voltage range<br><br>- Difficult solder pads<br><br>- Complicated application circuitry
![pwr3](./assets/images/pwr3.jpg)<br>[LM2675MX-3.3/NOPB](https://www.digikey.com/en/products/detail/texas-instruments/LM2675MX-3-3-NOPB/366907)<br>$4.36/each<br>[datasheet](https://www.ti.com/lit/ds/symlink/lm2675.pdf?HQS=dis-dk-null-digikeymode-dsf-pf-null-wwe&ts=1738976377161&ref_url=https%253A%252F%252Fwww.ti.com%252Fgeneral%252Fdocs%252Fsuppproductinfo.tsp%253FdistId%253D10%2526gotoUrl%253Dhttps%253A%252F%252Fwww.ti.com%252Flit%252Fgpn%252Flm2675) | - Large input voltage range<br><br>- High maximum input voltage<br><br>- Larger operational temperature range<br><br>- Has variable output version | - Limited 1A output capacity<br><br>- Higher minimum input voltage<br><br>- Lower switching frequency<br><br>- Expensive

Selected Component: Option 1 - AP63203WU-7  
Rational: This switching power supply has the desired output of 3.3 volts and has an adequate current capacity. It is also in a package that is easily soldered by hand. The required supporting circuitry is simple and will take up less space. The higher switching frequency makes it better suited to the lower input voltages.

### Hall Effect Sensor (Wind Speed)

Option | Pros | Cons
---|---|---
![hall2](./assets/images/hall2.jpg)<br>[HAL3726DJ-A](https://www.digikey.com/en/products/detail/tdk-micronas-gmbh/HAL3726DJ-A/5271756)<br>$2.70/each<br>[datasheet](https://www.digikey.com/en/products/detail/tdk-micronas-gmbh/HAL3726DJ-A/5271756) | - Provides self diagnosis<br><br>- Rotary hall effect sensor<br><br>- Can read 2D position | - Requires separate voltage regulator(doesn't operate at 3.3V)<br><br>- More expensive option<br><br>- No serial communication
![hall3](./assets/images/hall3.jpg)<br>[A1304ELHLX-T](https://www.digikey.com/en/products/detail/allegro-microsystems/A1304ELHLX-T/4552949?gclsrc=aw.ds&&utm_adgroup=&utm_source=google&utm_medium=cpc&utm_campaign=PMax%20Shopping_Product_High%20ROAS%20Categories&utm_term=&utm_content=&utm_id=go_cmp-20222717502_adg-_ad-__dev-c_ext-_prd-4552949_sig-Cj0KCQiA-5a9BhCBARIsACwMkJ7cF_KgTJqyZMYP8CbcNho2u9uOeVeN2OHf7pAXgWwaTmbPvqIEFq4aAnqREALw_wcB&gad_source=1&gclid=Cj0KCQiA-5a9BhCBARIsACwMkJ7cF_KgTJqyZMYP8CbcNho2u9uOeVeN2OHf7pAXgWwaTmbPvqIEFq4aAnqREALw_wcB)<br>$0.96/each<br>[datasheet](https://www.allegromicro.com/~/media/Files/Datasheets/A1304-Datasheet.ashx) | - Simple analog output<br><br>- Inexpensive<br><br>- Easy implementation | - Linear hall effect sensor<br><br>- No serial communication<br><br>- Narrow operational voltage range<br><br>- Higher current draw
![hall4](./assets/images/hall4.jpg)<br>[AS5600L-ASOM SOIC LF T&RDP](https://www.digikey.com/en/products/detail/ams-osram-usa-inc/AS5600L-ASOM-SOIC8-LF-T-RDP/10324317)<br>$4.54/each<br>[datasheet](https://www.digikey.com/htmldatasheets/production/1647438/0/0/1/as5600-datasheet.pdf) | - I2C data communication<br><br>- Rotary hall effect sensor<br><br>- Operates at 3.3v | - Most expensive option<br><br>- Sensitive to moisture<br><br>- Limited reprogramming

Selected Component: Option 3 - AS5600L-ASOM SOIC LF T&RDP  
Rational: This option provides an I2C compatible rotary hall effect sensor. The rotary design allows for the easiest implementation of sensor. It is the most expensive option, but comes with the most ideal features.

### Temperature Sensor

Option | Pros | Cons
---|---|---
![temp1](./assets/images/temp1.jfif)<br>[TC74A4-3.3VCTTR](https://www.digikey.com/en/products/detail/microchip-technology/TC74A4-3-3VCTTR/443268)<br>$1.15/each<br>[datasheet](https://ww1.microchip.com/downloads/en/DeviceDoc/21462D.pdf) | - Wide operational voltage range<br><br>- I2C data interface<br><br>- Returns raw temperature(doesn't require further calculations)<br><br>- Multiple versions with different addresses | - Lower resolution(7b)<br><br>- More expensive<br><br>- Negative temperatures require further calculations<br><br>- Slower I2C clock limit
![temp2](./assets/images/temp2.jpg)<br>[LM75AD,118](https://www.digikey.com/en/products/detail/nxp-usa-inc/LM75AD-118/1692795)<br>$0.66/each<br>[datasheet](https://www.nxp.com/docs/en/data-sheet/LM75A.pdf) | - I2C data interface<br><br>- Higher resolution(11b)<br><br>- Programmable limit<br><br>- Inexpensive | - Larger component<br><br>- Unnecessary extra features<br><br>- Requires further data transformation<br><br>- Requires more connections
![temp3](./assets/images/temp3.jfif)<br>[TMP1075DGKR](https://www.digikey.com/en/products/detail/texas-instruments/TMP1075DGKR/9692553)<br>$0.47/each<br>[datasheet](https://www.ti.com/lit/ds/symlink/tmp1075.pdf) | - I2C data interface<br><br>- Higher resolution(12b)<br><br>- Most inexpensive option | -More data to be communicated<br><br>- Requires further data transformation<br><br>- Requires more connections

Selected Component: Other - HIH6030-021-001  
Rational: The selected component for the humidity sensor doubles as a temperature sensor. This eliminates the need for a standalone sensor.

### Humidity Sensor

Option | Pros | Cons
---|---|---
![hum1](./assets/images/hum1.jpg)<br>[HIH6030-021-001](https://www.digikey.com/en/products/detail/texas-instruments/HIH6030-021-001/17884961)<br>$2.55/each<br>[datasheet](https://www.ti.com/lit/ds/symlink/hdc3020.pdf) | - I2C data interface<br><br>- Has temperature output<br><br>- Most inexpensive option<br><br>- Highest accuracy | - Extremely difficult to solder<br><br>- Tiny chip size<br><br>- Lacks standard mode I2C speed
![hum2](./assets/images/hum2.jfif)<br>[H6030-021-001](https://www.digikey.com/en/products/detail/honeywell-sensing-and-productivity-solutions/HIH6030-021-001/4291625)<br>$6.67/each<br>[datasheet](https://prod-edam.honeywell.com/content/dam/honeywell-edam/sps/siot/en-us/products/sensors/humidity-with-temperature-sensors/honeywell-humidicon-hih6000-series/documents/sps-siot-hih6000-datasheet-009073-7-en-ciid-147070.pdf) | - I2C data interface<br><br>- Has temperature output<br><br>- Affordable cost | - Lowest relative humidity accuracy<br><br>- Non-condensing
![hum3](./assets/images/hum3.jpg)<br>[HIH6131-000-001](https://www.digikey.com/en/products/detail/honeywell-sensing-and-productivity-solutions/HIH6131-000-001/5253024)<br>$18.09/each<br>[datasheet](https://prod-edam.honeywell.com/content/dam/honeywell-edam/sps/siot/en-us/products/sensors/humidity-with-temperature-sensors/honeywell-humidicon-hih6100-series/documents/sps-siot-humidicon-hih6100-series-product-sheet-009059-6-en-ciid-142165.pdf) | - SPI data interface<br><br>- Has temperature output<br><br>- Protected from condensation | - Does not support I2C<br><br>- Very expensive option

Selected Component: Option 2 - HIH6030-021-001  
Rational: This option has the lowest accuracy; however, its larger package is easier to solder and supports I2C communication. It also doubles as a temperature sensor which offsets the increased cost.

### Air Pressure Sensor

Option | Pros | Cons
---|---|---
![air1](./assets/images/air1.jpg)<br>[DPS368XTSA1](https://www.digikey.com/en/products/detail/infineon-technologies/DPS368XTSA1/10244079)<br>$2.51/each<br>[datasheet](https://www.infineon.com/dgdl/Infineon-DPS368-DS-v01_00-EN.pdf?fileId=5546d46269e1c019016a0c45105d4b40) | - Supports I2C & SPI communication<br><br>- Simpler footprint<br><br>- Measures temperature | - Vented guage <br><br>- Smaller pressure range<br><br>- Difficult soldering points
![air2](./assets/images/air2.jpg)<br>[ENS220S-BLGT](https://www.digikey.com/en/products/detail/sciosense/ENS220S-BLGT/21278457)<br>$2.70/each<br>[datasheet](https://www.sciosense.com/wp-content/uploads/2023/12/ENS220-Datasheet.pdf) | - Adequate pressure range<br><br>- Supports I2C & SPI communication<br><br>- Absolute pressure guage<br><br>- Measures temperature | - Very low operational voltage range<br><br>- Less suited for application<br><br>- Difficult soldering points
![air3](./assets/images/air3.jpg)<br>[LPS22HBTR](https://www.digikey.com/en/products/detail/stmicroelectronics/LPS22HBTR/5799910)<br>$2.81/each<br>[datasheet](https://www.st.com/content/ccc/resource/technical/document/datasheet/bf/c1/4f/23/61/17/44/8a/DM00140895.pdf/files/DM00140895.pdf/jcr:content/translations/en.DM00140895.pdf) | - Adequate pressure range<br><br>- Supports I2C & SPI communication<br><br>- Absolute pressure guage | - Difficult soldering points<br><br>- Most expensive option<br><br>- Doesn't return temperature

Selected Component: Option 3 - LPS22HBTR  
Rational: This sensor is an absolute pressure sensor that can operate with the 3.3V utilized in the subsystem. It also uses I2C to communicate data which is the chosen method for the subsystem. This option also has a higher maximum pressure and is temperature compensated.

### Comparator

Option | Pros | Cons
---|---|---
![comp1](./assets/images/comp1.jpg)<br>[LM2903DR](https://www.digikey.com/en/products/detail/texas-instruments/LM2903DR/276656)<br>$0.18/each<br>[datasheet](https://www.ti.com/lit/ds/symlink/lm193.pdf?ts=1640569642482) | - Power can be supplied rail-to-rail<br><br>- Very inexpensive<br><br>- Extremely fast operation<br><br>- Large differential voltage range | - Open collector design(harder to implement)<br><br>- Larger package<br><br>- More complex circuit & connections
![comp2](./assets/images/comp2.jfif)<br>[MCP6541RT-E/OT](https://www.digikey.com/en/products/detail/microchip-technology/MCP6541RT-E-OT/870211)<br>$0.39/each<br>[datasheet](https://ww1.microchip.com/downloads/en/DeviceDoc/MCP6541%20Output%20SubMicroamp%20Comparators%2020001696K.pdf) | - Power can be supplied rail-to-rail<br><br>- Push-pull design<br><br>- Can drive larger load | - Slower operation speed<br><br>- Smallest voltage supply range
![comp3](./assets/images/comp2.jfif)<br>[TLV7031QDBVRQ1](https://www.digikey.com/en/products/detail/texas-instruments/TLV7031QDBVRQ1/15222328)<br>$0.72/each<br>[datasheet](https://www.ti.com/lit/ds/symlink/tlv7031-q1.pdf) | - Power can be supplied rail-to-rail<br><br>- Push-pull design<br><br>- Decent voltage supply range | - Limited differential voltage<br><br>- Higher hysteresis<br><br>- Limited load driving capability

Selected Component: Option 2 - MCP6541RT-E/OT  
Rational: The push-pull configuration of this option allows for easy implementation. This option also has a lower hysteresis which gives a lower switching threshold for the application.
