---
title: Bill of Materials
tags:
- tag1
- tag2
---

## Overview
This is the Bill of Materials section of the Motor subsystem. The main components are the motor, the H-bridge, the potentiometer, the 8-pin connector, and the microchip. The additional components are the resistors, the capacitors, the LEDs, test points, the barrel jack, LM7805, and fuses.

## Bill of Materials Example (as Table)

*Table ##: An example of one approach to adding your BOM table to this section.*

| **Part Name/Description** | **Qty** | **Unit Cost** | **Total Cost** | **Manufacture** | **Manufacturer #** | **Vendor Link** |**Datasheet Link** | **Schematic Reference Designators** |
|:--------------------|:----|:---------------|:-----|:--------|:-----|:-----|:----|:-----|
|12V Motor| 1 |25.39|$25.39$|E-S Motor|5840WG-555PM-590 12V|https://www.robotshop.com/products/e-s-motor-high-torque-12v-dc-worm-gear-motor-15-rpm?qd=3081407f1db71f0fec5903ffe304727d|https://cdn.robotshop.com/rbm/a00a7635-653b-4220-aac9-b0c23c5c5e2c/8/8dfd4a0b-e136-4eb4-92df-334ddc4db4db/d8100fa8_5840wg-555pm-worm-gear-motor.pdf| Motor_IRS1 |
|H-Bridge| 1 |1.50|$1.50|Adafruit|4489|https://www.adafruit.com/product/4489|:----| H-Bridge_IRS1 |
|Potentiometer| 1 | 1.65 | $1.65 | Bourns Inc. | PTA3043-2010CIB104 | https://www.digikey.com/en/products/detail/bourns-inc/PTA3043-2010CIB104/3781186?gclsrc=aw.ds&gad_source=1&gad_campaignid=20243136172&gbraid=0AAAAADrbLliFVtbptKHwxHXZOLTZ9Dngt&gclid=CjwKCAjw0sfHBhB6EiwAQtv5qdDayR3wUdt1PhP_Zrn28sFLcQJGq9LoqSQneqg9s4Sqr2sY-hUGlRoC1iQQAvD_BwE | https://www.bourns.com/docs/Product-Datasheets/pta.pdf | Slide_100k_Potentiometer_IRS1 |
|8-pin Connector| 3 |:---------------|:-----|:--------|:-----|:-----|:----| U4, U5, U15 |
|LM7805| 1 | 0.50 | 0.50 | STMicroelectronics | L7805CV |https://www.digikey.com/en/products/detail/stmicroelectronics/L7805CV/585964|https://www.st.com/content/ccc/resource/technical/document/datasheet/41/4f/b3/b0/12/d4/47/88/CD00000444.pdf/files/CD00000444.pdf/jcr:content/translations/en.CD00000444.pdf| U13 |
|Microchip| 1 | 9.99 | $9.99 |Microchip|DM164150|https://www.microchipdirect.com/dev-tools/DM164150?productLoaded=true&allDevTools=true|https://ww1.microchip.com/downloads/aemDocuments/documents/MCU08/ProductDocuments/UserGuides/PIC18F57Q43-Curiosity-Nano-HW-UserGuide-DS40002186B.pdf| PIC18F57Q43_CURIOSITY_NANO_IRS1 |
|Resistors| 3 |12.99|$12.99|WWZMDiB Store|n/a|PRLTA 109 |n/a | R1, R2, R3 |
|0.1 µF Ceramic Capacitor, +/-10%, X7R, 50V, 0805 package |10 | 0.2750 | $2.75 | KEMET | C0805F104K5RACTU | PRLTA 109 |n/a | C2, C4, C6, C7, C8, C9, C10, C11, C12, C16|
|Green LED| 1 |12.99|$12.99|WWZMDiB Store|n/a|PRLTA 109 |n/a | D1 |
|Red LED| 1 |12.99|$12.99|WWZMDiB Store|n/a|PRLTA 109 |n/a | D2 |
|Test Points| 5 |12.99|$12.99|WWZMDiB Store|n/a|PRLTA 109 |n/a |U1, U2, U3, U12, U14 |
|Barrel Jack| 1 |0.76| $0.76|Same Sky (Formerly CUI Devices)|PJ-102AH|https://www.digikey.com/en/products/detail/cui-devices/PJ-102AH/408448|https://www.sameskydevices.com/product/resource/pj-102ah.pdf| J1 |
|Fuses| 2 |0.56| $1.12 | Littelfuse Inc. | 0235003.MXP |https://www.digikey.com/en/products/detail/littelfuse-inc/0235003-MXP/778152|https://www.littelfuse.com/assetdocs/littelfuse_fuse_235_datasheet.pdf?assetguid=79b16c87-8337-4c9c-96d1-6ac09ce4e440| F1, F2 |




