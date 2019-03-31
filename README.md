# Smart-BMS-Project
Project to implement home made powerwall based on 6 battery packs each with 7S 9P configuration.
Components
  378 18650 lithium Ion cells
  
  6  * Chinese BMS models based on the Texas Instruments BQ76930 chip with a UART interface.
  
  54 * 7S PCBS from the Jehu Garcia design manuafactuered at JLPCB
  
  6  * BMS PCB's designed for the above BMS designed by me (Based on Justin Kenny's original 3 BMS design) and manuafactuered at JLPCB
  
Data from the 6 BMS modules is captured to an InfluxDB store and surfaced in Grafana.

Code is Arduino based C++ currently running on an ESP8266 based Wemod D1 mini Pro, but will probably be ported to ESP32 for more GPIO pins. MCU will need an external antenna connector to get the range to connect back to InfluxDB data store.

THE BMS module is now fully tested, and the board design performs to Texas Instruments BQ 76930 specification.
Tests performed include:
  Cell Over Volatage
  Cell Under Volatage
  Cell Charge Balancing (Individual Cell MOSFET Switching) 
  Pack Over Volatage (Charge MOSFET Switching)
  Pack Under Voltage (Discharge MOSFET Switching)
  

