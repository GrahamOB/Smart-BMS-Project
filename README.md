# Smart-BMS-Project
Project to implement home made powerwall based on 6 battery packs each with 7S 9P configuration.

Components:

  378 18650 lithium Ion cells
  
  6  * Chinese BMS models based on the Texas Instruments BQ76930 chip with a UART interface.
  
  54 * 7S PCBS from the Jehu Garcia design manuafactuered at JLPCB
  
  6  * BMS PCB's designed for the above BMS designed by me (Based on Justin Kenny's original 3 BMS design) and manuafactuered at JLPCB
  
Data from the 6 BMS modules is captured to an InfluxDB store and surfaced in Grafana.

Code is Arduino based C++ currently running on an ESP8266 based Wemod D1 mini Pro, but will probably be ported to ESP32 for more GPIO pins. MCU will need an external antenna connector to get the range to connect back to InfluxDB data store.

Basic testing of the BMS module is now complete, and the board design performs to Texas Instruments BQ 76930 specification.
Tests performed include:

  Cell Over Volatage
  
  Cell Under Volatage
  
  Cell Charge Balancing (Individual Cell MOSFET Switching) 
  
  Pack Over Volatage (Charge MOSFET Switching)
  
  Pack Under Voltage (Discharge MOSFET Switching)
  
  https://www.aliexpress.com/item/7S-24V-20A-30A-40A-60A-18650-Lithium-battery-smart-protection-board-balance-bms-pcm-W/32961106224.html?spm=a2g0s.9042311.0.0.5e6f4c4dKq4Cua

Acknowlegements:

bres55 (github) For the orginal code and doing all the heavy lifting for the UART register calls. This was a huge piece of work, and saved me many hours as all my previous designs were over the BQ76930 I2C bus.

Jehu Garcia for the original concept for a PCB approach to building powerwalls. Using PCB,s may seem to some as massive overkill, but the maintenance of indiviudual cells is so easy with this approach. And it the packs look awesome when built.

Justin Kenny for the battery PCB gerbers and layout design
