---
tag: PCB
version: v1.1
date: 2025-08-25
title: Updated PCB Design
description: Second iteration of schematic and PCB design
---

## Gallery

![3D render of prototype board - v1.1[caption]](../assets/Board_3D_Proto_v1.1.png "3D render of prototype board - v1.1")
![PCB layout of prototype board - v1.1[caption]](../assets/Board_PCB_Proto_v1.1.png "PCB layout of prototype board - v1.1")
![Motor control board schematic - v1.1[caption]](../assets/Board_Motor_Schm_Proto_v1.1.png "Motor control board schematic - v1.1")
![Power board schematic - v1.1[caption]](../assets/Board_Power_Schm_Proto_v1.1.png "Power board schematic - v1.1")



## BOM


| Part #                                                                                                                                                              | Name                                       | Designator     | Qty. |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------ | -------------- | ---- |
| [MPZ1608S101ATAH0](https://www.digikey.ca/en/products/detail/tdk-corporation/MPZ1608S101ATAH0/571871)                                                               | Ferrite Bead                               | L2, L3         | 2    |
| [GRM188Z71A106MA73J](https://www.digikey.ca/en/products/detail/murata-electronics/GRM188Z71A106MA73J/17854471?s=N4IgTCBcDaIOICUCyBGAHGgWgdhQQRQAYA2JPbAZgCkQBdAXyA) | Ceramic Capacitor 10uF                     | C2-C11         | 10   |
| [UCD0J102MNL1GS](https://www.digikey.ca/en/products/detail/nichicon/ucd0j102mnl1gs/2549609)                                                                         | Electrolytic Capacitor 1000uF              | C1             | 1    |
| [SS34](https://www.digikey.ca/en/products/detail/shenzhen-slkormicro-semicon-co-ltd/ss34/21853055)                                                                  | Schottky Diode                             | D1, D2, D3, D4 | 4    |
| [SMAJ5.0A](https://www.digikey.ca/en/products/detail/good-ark-semiconductor/smaj5-0a/18649116)                                                                      | TVR Diode                                  | D5             | 1    |
| [AO3400A](https://www.digikey.ca/en/products/detail/alpha-omega-semiconductor-inc/ao3400a/1855772)                                                                  | N-Type MOSFET                              | Q1, Q2, Q3, Q4 | 4    |
| [RC0603JR-0722RL](https://www.digikey.ca/en/products/detail/yageo/RC0603JR-0722RL/726743)                                                                           | Resistor 22Ohm                             | R1, R3, R5, R7 | 4    |
| [CR0603-JW-104ELF](https://www.digikey.ca/en/products/detail/bourns-inc/CR0603-JW-104ELF/2345098)                                                                   | Resistor 100kOhm                           | R2, R4, R6, R8 | 4    |
| [0530480210](https://www.digikey.ca/en/products/detail/molex/0530480210/242864)                                                                                     | Molex 2Pos 1.25mm Connector                | M1, M2, M3, M4 | 4    |
| [AP2112R5-3.3TRG1](https://www.digikey.ca/en/products/detail/diodes-incorporated/AP2112R5-3-3TRG1/5305557)                                                          | 3.3V LDO Voltage Regulator                 | U1             | 1    |
| [S2B-PH-K-S JST](https://www.digikey.ca/en/products/detail/jst-sales-america-inc/S2B-PH-K-S/926626)                                                                 | JST 2Pos 2.0mm Horizontal Header Connector | BT1            | 1    |
|                                                                                                                                                                     | Male Vertical Header Pins                  |                | 48+  |


## Electrical


### Flight Controller
---

**Type:** ESP32
**Link:** [Freenove ESP32-WROOM Board (2 Pack), Dual-core 32-bit 240 MHz Microcontroller, Onboard Wireless, Python C Code, Example Projects Tutorial : Amazon.ca: Electronics](https://www.amazon.ca/Freenove-ESP32-WROOM-Compatible-Wireless-Detailed/dp/B0C9THDPXP?th=1)
**Datasheet:** [esp32-wroom-32e_esp32-wroom-32ue_datasheet_en.pdf](https://www.espressif.com/sites/default/files/documentation/esp32-wroom-32e_esp32-wroom-32ue_datasheet_en.pdf)

**Memory:** 4MB
**CPU Speed:** 240 MHz

**Operating voltage:** 3.0-3.6V
**Minimum current supply:** 0.5A

![[Pasted image 20250818150404.png]]


### Accelerometer
---

**Type:** MPU6050
**Link (Maybe):** [Wishiot 5pcs MPU-6050 Acceleration Sensor 6dof Three-Axis Accelerometer Gyro Sensor IMU with 1pc 40Pin Male Header and 1pc 40Pin Male to Female Dupont Cable for Arduino RC Quadcopter Drone : Amazon.ca: Industrial & Scientific](https://www.amazon.ca/Acceleration-Sensors-Accelerometer-Three-Axis-Quadcopter/dp/B07V67DQ5N/ref=sr_1_5?crid=V52SERP9P75S&dib=eyJ2IjoiMSJ9.J9hkdZQOlrel1XyPKlHtc-IOM9G3Zv57k6ISrxonR7I1nOohfb5Jf3f4E15bBS1yEfBr06-vTi_9CZUEsgu8_35u4KQ0yL_OVNJ8-pAYY_wCXTidCBb8UVkboJkGWTaGXMPFU3liIDVU2ET0BL3Hn5C9NssJ1O241hiOFwa6_D9qCpVoHk4NubLRZiMxaw-3kvnj5Y2K9s91uATGO8YGch0uvcJtQ_m9hjIMP15KUgMtl96TpbmKmr7YgS95J9bzIv3UUlbfb58gxiBhhHGwydv_dFHN3ZqEp7W1QUSUeKg.259dzy5EwJBDa0jbM6wKNUPmpVk4G2M-BbG3ZAHh4fc&dib_tag=se&keywords=mpu6050&qid=1755554178&sprefix=mpu%2Caps%2C932&sr=8-5&th=1)

**Gyroscope:**
- **Standby:** 5uA
- **Operating:** 3.6mA

**Accelerometer:**
- **Operating:** 500uA

**Total:** 3.9mA
**VDD supply:** 2.375-3.46V


### Motors
---

**Type:** CFMX143 4 x DIY DC 3.7V 50000RPM 716 motor
**Link:** [4 x DIY DC 3.7V 50000RPM 716 Hollow Cup Coreless High-speed Motor with 4 x 55MM Propeller Cw CCW for DIY Micro FPV Quadcopter - AliExpress 26](https://www.aliexpress.com/item/1005006256671599.html?spm=a2g0o.order_list.order_list_main.15.f2671802BMLM1I)

**Voltage:** 3.7V
**Speed**: 50000RPM
**No-load:** 0.08A
**Stall:** 1.8A
**Avg. Running:** - TO BE TESTED

**Size:** 7x16mm
**Output shaft:** 0.8mm
**Output shaft length:** 7mm



### Motor Speed Control
---

#### Diode

**Type** SS34
**Datasheet:** [SS32-S310 Schottky Rectifier](https://www.farnell.com/datasheets/2303855.pdf)

**Forward Current:** 3A
**Max. Reverse Voltage:** 40V


#### MOSFET

**Type:** AO3400A
**Datasheet:** [AO3400A_Rev3_RoHS](https://mm.digikey.com/Volume0/opasdata/d220001/medias/docus/1133/AO3400A_ds.pdf)

**Drain-Source Voltage:** 30V Max
**Gate-Source Voltage:** +-12V Max.
**Gate Threshold Voltage:** 0.65-1.45V, 1.05V Typ.


### Battery
---

**Total running current draw:** 0.8239A
- Flight controller: 0.5A
- Accelerometer: 3.9mA
- Motors: 0.08A * 4 = 0.32A 

**Total peak current draw:** 7.7039A
- Flight controller: 0.5A
- Accelerometer: 3.9mA
- Motors: 1.8A * 4 = 7.2A 

**Expected flight time:** 20mins
**Raw:** 274.63mAh
**80% usage:** 343.292mAh
**Margin:** 400-500mAh

**Peak current rating:** $C=I / Ah$
**Rating:** C = 19.25 = 20 (400mAh)



### Power Control
---

#### TVR Diode

**Type:** SMAJ5.0A
**Datasheet:** [SMAJx](https://goodarksemi.com/docs/datasheets/transient_voltage_suppressors/SMAJx.pdf) 

**Breakdown voltage:** 6.4-7.07V
**Clamping voltage:** 9.2V


#### Voltage Regulator IC

**Type:** AP2112R5-3.3TRG1
**Datasheet:** [AP2112R5-3.3TRG1 Diodes Incorporated | Integrated Circuits (ICs) | DigiKey](https://www.digikey.ca/en/products/detail/diodes-incorporated/AP2112R5-3-3TRG1/5305557)

**Absolute maximum V_in:** 6V
**Rated current:** 0.6A
**Fixed output:** 3.3V
**Dropout voltage:** 0.4V @ 600mA