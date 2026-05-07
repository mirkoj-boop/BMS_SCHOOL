# Battery Charger / BMS Research Notes

## Most Important Schematic
Reference AC/DC SMPS multi-output design from DigiKey:

- https://www.digikey.com/reference-designs/en/ac-dc-and-dc-dc-conversion/ac-dc-smps-multi-output/752

---

#BQ77905 Design Consideration:

 - https://www.ti.com/lit/an/slua793/slua793.pdf?ts=1778172323063&ref_url=https%253A%252F%252Fwww.ti.com%252Fproduct%252FBQ77905


# EMI / Input Protection

## Common Mode Choke
Suggested component:

- ACMS-Q3225E
  - 15 mA
  - 80 VDC
  - 10 MΩ

---

## EMI Filter Capacitor
KEMET safety capacitor documentation:

- https://content.kemet.com/datasheets/KEM_F3019_PZB300X2_2XY2_275.pdf

---

## Thermistors
Add thermistors on:
- AC input
- battery pack
- MOSFET area
- transformer area

Possible use cases:
- inrush current limiting
- temperature monitoring
- thermal shutdown

---

# Flyback Converter

## TI Flyback Controller
Main controller:

- UCC28742

Datasheet:
- https://www.ti.com/lit/ds/symlink/ucc28742.pdf

---

## LT Demonstration 12V Charger
STMicroelectronics charger reference:

- https://www.st.com/content/ccc/resource/technical/document/user_manual/02/3f/07/49/60/73/45/37/CD00282230.pdf/files/CD00282230.pdf/jcr:content/translations/en.CD00282230.pdf

---

# Battery Protection / BMS

## Simple Single Li-Ion Battery Protection

### Excellent BQ29700 Example
4.2V single-cell Li-Ion protection example:

- https://www.ti.com/lit/ug/sluuaz3/sluuaz3.pdf

### Single Battery PCB Example
- https://www.ti.com/tool/BQ29700EVM-610

---

## Multi-Cell Battery Protection

### BQ77904 / BQ77905
Example for 3-cell and 4-cell battery systems:

- https://www.ti.com/lit/ds/symlink/bq77905.pdf

---

## Selected Reference Design
Using the example:
- BQ77905
- 4-series LiCoO2 batteries
- Example schematic from page 32 of the datasheet

Reference:
- https://www.ti.com/lit/ds/symlink/bq77905.pdf

---

# MOSFET Implementation

Very useful explanation of:
- protection MOSFETs
- current paths
- body diodes
- charge/discharge control

Document:
- https://www.ti.com/lit/an/slua910/slua910.pdf

---

# Power Architecture Notes

## Input Stage Requirements
At AC input define:
- EMI filter
- common mode choke
- bridge rectifier
- flyback transformer
- flyback controller
- startup circuitry
- auxiliary supply
- LDO regulator

Potential rails:
- 12V
- 5V
- 3.3V

---

# Additional TI Complex Design

Complex Texas Instruments concept requiring:
- multiplexer (MUX)
- monitoring logic
- additional control circuitry

Reference:
- https://www.ti.com/lit/ug/tiduf32/tiduf32.pdf

---

# Manufacturing / Testing Notes

## Two Battery Example Discussion
Interesting discussion about manufacturing test procedures:

- https://e2e.ti.com/support/power-management-group/power-management/f/power-management-forum/564338/bq2970-testing-bq29700-during-manufacturing

---

# Additional PCB Example

Community PCB implementation:

- https://www.pcbway.com/project/shareproject/bq40z50_r2_BMS_4S_681f1491.html

---

# Quick Current Shutdown

Quick implementation of npn switch

 - https://www.ti.com/lit/an/slua826/slua826.pdf?ts=1778166672133

---

# Future Ideas

Possible additions:
- balancing circuitry
- isolated feedback
- USB-C PD input
- battery fuel gauge
- CAN/UART communication
- thermal shutdown logic
- charger status LEDs
- fuse protection
- reverse polarity protection
- current sensing with shunt resistor