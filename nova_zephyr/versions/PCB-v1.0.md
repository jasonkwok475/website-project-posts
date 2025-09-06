---
tag: PCB
version: v1.0
date: 2025-08-17
title: Initial PCB Design
description: First iteration of schematic and PCB design
---

## Changelog Details

New Features:
- Individual motor speed controller circuits
- Power circuit to isolate motor and microcontroller power lines
- Custom ESP32 footprint


## Gallery

![Modified motor cicuit with gate and gate-source resistors[caption]](../assets/v1.0_Modified_Motor_Circuit.png "Modified motor cicuit with gate and gate-source resistors")
![Full motor speed controller circuit - v1.0[caption]](../assets/v1.0_Final_Motor_Circuit.png "Full motor speed controller circuit - v1.0")
![Board power circuit - v1.0[caption]](../assets/v1.0_Power_Circuit.png "Board power circuit - v1.0")
![Custom ESP32 Symbol in KiCad[caption]](../assets/ESP32_Custom_Symbol.png "Custom ESP32 Symbol in KiCad")
![Custom ESP32 Footprint in KiCad[caption]](../assets/ESP32_Custom_Footprint.png "Custom ESP32 Footprint in KiCad")
![ESP32 Connection Schematic - v1.0[caption]](../assets/v1.0_ESP32_Connection_Schematic.png "ESP32 Connection Schematic - v1.0")



## BOM

| Part #                                                                                                                                                              | Name                              | Designator                           | Qty. |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------- | ------------------------------------ | ---- |
| [MPZ1608S101ATAH0](https://www.digikey.ca/en/products/detail/tdk-corporation/MPZ1608S101ATAH0/571871)                                                               | Ferrite Bead                      | L2, L3                               | 2    |
| [GCJ188R71C104MA01J](https://www.digikey.ca/en/products/detail/murata-electronics/gcj188r71c104ma01j/10697171)                                                      | Ceramic Capacitor 0.1uF           | C1                                   | 1    |
| [GRM188Z71A106MA73J](https://www.digikey.ca/en/products/detail/murata-electronics/GRM188Z71A106MA73J/17854471?s=N4IgTCBcDaIOICUCyBGAHGgWgdhQQRQAYA2JPbAZgCkQBdAXyA) | Ceramic Capacitor 10uF            | C2, C3, C5, C6, C7, C8, C9, C10, C11 | 9    |
| [UCD0J102MNL1GS](https://www.digikey.ca/en/products/detail/nichicon/ucd0j102mnl1gs/2549609)                                                                         | Electrolytic Capacitor 1000uF     | C4                                   | 1    |
| [SS34](https://www.digikey.ca/en/products/detail/shenzhen-slkormicro-semicon-co-ltd/ss34/21853055)                                                                  | Schottky Diode                    | D1, D2, D3, D4                       | 4    |
| [SMAJ5.0A](https://www.digikey.ca/en/products/detail/good-ark-semiconductor/smaj5-0a/18649116)                                                                      | TVR Diode                         | D5                                   | 1    |
| [AO3400A](https://www.digikey.ca/en/products/detail/alpha-omega-semiconductor-inc/ao3400a/1855772)                                                                  | N-Type MOSFET                     | Q1, Q2, Q3, Q4                       | 4    |
| [RC0603JR-0722RL](https://www.digikey.ca/en/products/detail/yageo/RC0603JR-0722RL/726743)                                                                           | Resistor 22Ohm                    | R1, R3, R5, R7                       | 4    |
| [CR0603-JW-104ELF](https://www.digikey.ca/en/products/detail/bourns-inc/CR0603-JW-104ELF/2345098)                                                                   | Resistor 100kOhm                  | R2, R4, R6, R8                       | 4    |
| [RC0603JR-13100RL](https://www.digikey.ca/en/products/detail/yageo/RC0603JR-13100RL/13694093)                                                                       | Resistor 100Ohm                   | R9                                   | 1    |
| [VLS3012HBX-2R2M](https://www.digikey.ca/en/products/detail/tdk-corporation/VLS3012HBX-2R2M/7387441)                                                                | Inductor 2.2uH                    | L1                                   | 1    |
| [0530480210](https://www.digikey.ca/en/products/detail/molex/0530480210/242864)                                                                                     | Molex 2Pos 1.25mm Connector       | M1, M2, M3, M4                       | 4    |
| [TPS63001DRCR](https://www.digikey.ca/en/products/detail/texas-instruments/TPS63001DRCR/1016512)                                                                    | 3.3V Buck-Boost Voltage Regulator | U1                                   | 1    |


## Electrical


### Flight Controller
---

**Type:** ESP32<br>
**Link:** [Freenove ESP32-WROOM Board (2 Pack)](https://www.amazon.ca/Freenove-ESP32-WROOM-Compatible-Wireless-Detailed/dp/B0C9THDPXP?th=1)<br>
**Datasheet:** [esp32-wroom-32e_esp32-wroom-32ue_datasheet_en.pdf](https://www.espressif.com/sites/default/files/documentation/esp32-wroom-32e_esp32-wroom-32ue_datasheet_en.pdf)

**Memory:** 4MB<br>
**CPU Speed:** 240 MHz

**Operating voltage:** 3.0-3.6V<br>
**Minimum current supply:** 0.5A

![[Pasted image 20250818150404.png]]


### Accelerometer
---

**Type:** MPU6050<br>
**Link (Maybe):** [Wishiot 5pcs MPU-6050 Acceleration Sensor](https://www.amazon.ca/Acceleration-Sensors-Accelerometer-Three-Axis-Quadcopter/dp/B07V67DQ5N/ref=sr_1_5?crid=V52SERP9P75S&dib=eyJ2IjoiMSJ9.J9hkdZQOlrel1XyPKlHtc-IOM9G3Zv57k6ISrxonR7I1nOohfb5Jf3f4E15bBS1yEfBr06-vTi_9CZUEsgu8_35u4KQ0yL_OVNJ8-pAYY_wCXTidCBb8UVkboJkGWTaGXMPFU3liIDVU2ET0BL3Hn5C9NssJ1O241hiOFwa6_D9qCpVoHk4NubLRZiMxaw-3kvnj5Y2K9s91uATGO8YGch0uvcJtQ_m9hjIMP15KUgMtl96TpbmKmr7YgS95J9bzIv3UUlbfb58gxiBhhHGwydv_dFHN3ZqEp7W1QUSUeKg.259dzy5EwJBDa0jbM6wKNUPmpVk4G2M-BbG3ZAHh4fc&dib_tag=se&keywords=mpu6050&qid=1755554178&sprefix=mpu%2Caps%2C932&sr=8-5&th=1)

#### Gyroscope:
- **Standby:** 5uA<br>
- **Operating:** 3.6mA

#### Accelerometer:
- **Operating:** 500uA

**Total:** 3.9mA<br>
**VDD supply:** 2.375-3.46V


### Motors
---

**Type:** CFMX143 4 x DIY DC 3.7V 50000RPM 716 motor<br>
**Link:** [4 x DIY DC 3.7V 50000RPM 716 Hollow Cup Coreless High-speed Motor](https://www.aliexpress.com/item/1005006256671599.html?spm=a2g0o.order_list.order_list_main.15.f2671802BMLM1I)

**Voltage:** 3.7V<br>
**Speed**: 50000RPM<br>
**No-load:** 0.08A<br>
**Stall:** 1.8A<br>
**Avg. Running:** - TO BE TESTED

**Size:** 7x16mm<br>
**Output shaft:** 0.8mm<br>
**Output shaft length:** 7mm



### Motor Speed Control
---

#### Diode

**Type** SS34<br>
**Datasheet:** [SS32-S310 Schottky Rectifier](https://www.farnell.com/datasheets/2303855.pdf)

**Forward Current:** 3A<br>
**Max. Reverse Voltage:** 40V


#### MOSFET

**Type:** AO3400A<br>
**Datasheet:** [AO3400A_Rev3_RoHS](https://mm.digikey.com/Volume0/opasdata/d220001/medias/docus/1133/AO3400A_ds.pdf)

**Drain-Source Voltage:** 30V Max<br>
**Gate-Source Voltage:** +-12V Max.<br>
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

**Expected flight time:** 20mins<br>
**Raw:** 274.63mAh<br>
**80% usage:** 343.292mAh<br>
**Margin:** 400-500mAh

**Peak current rating:** $C=I / Ah$<br>
**Rating:** C = 19.25 = 20 (400mAh)



### Power Control
---

#### TVR Diode

**Type:** SMAJ5.0A<br>
**Datasheet:** [SMAJx](https://goodarksemi.com/docs/datasheets/transient_voltage_suppressors/SMAJx.pdf) 

**Breakdown voltage:** 6.4-7.07V<br>
**Clamping voltage:** 9.2V


#### Voltage Regulator IC

**Type:** TPS63001<br>
**Datasheet:** [TPS63001 data sheet, product information and support | TI.com](https://www.ti.com/product/TPS63001)

**Absolute maximum V_in:** 7V<br>
**Rated current:** 1.8A<br>
**Fixed output:** 3.3V