# Elixir
The Elixir is part of Golioth's "Aludel" platform, a family of devices that makes it easier to connect hardware to the internet using [Golioth's Firmware SDK](https://github.com/golioth/golioth-firmware-sdk) and [cloud platform](https://console.golioth.io). The Aludel family of devices are widely used in [Golioth's Reference Designs](https://projects.golioth.io), which are end-to-end demonstrations of IoT devices targeted at different vertical applications. 

This board primarily targets cellular connectivity but also has the ability to connect to/interact with WiFi networks; it can also be used for supplemental features such as [Wi-Fi locationing](https://blog.golioth.io/a-2-geofence-wi-fi-location-here-com-esp32-c3-golioth-pipelines-and-n8n/). An on-board power management unit facilitates a large array of power options, including LiPo via the onaboard connector and charging capabilities, but also up to 48V input for industrial applications. There are are array of sensors and other other commonly used support ICs. Prominently featured on Aludel boards, including this one, are [headers that conform to the MikroBus standard](https://www.mikroe.com/mikrobus). This is a pinout from Mikroelectronika and supported by their [wide range of plug-in sensor boards](https://www.mikroe.com/click). We chose this standard for maximum hardware swappability, enabling our users to change to a different targeted sensor or industry vertical by replacing one or two click boards. 

This is released as Revision C of the Elixir. Revisions A and B were internal-only and the naming will be maintained for continuity.

## On the board
* nRF9160 - Cat M1 / NB-IOT / GPS chip with dual core Cortex M33 processing
* ESP32-C3 - Running ESP-AT firmware, interfaced to the nRF9160 over UART
* BME280 - Weather sensor from Bosch, common to many Golioth designs
* Power
  * Low quiescent buck circuit, inherited from Feather Board
  * 5V boost to service the 5V output on the MikroBus
  * Battery charging
  * Fuel gauge
  * High voltage input (5.5V to 48V) for powering from things like OBD-II and industrial supplies
* LIS2DH - Accelerometer, inherited from Feather board
* PWM Buzzer - Allow audible indication [similar to the Thingy91](https://github.com/golioth/thingy91-golioth)
* Real Time Clock
* Secure Element
* Power Switching - Power switch of 3V3 for sensor nodes to shut down in low power situations
* QWIIC / STEMMA Headers - External sensors and peripherals including the [Aludel Ostentus](https://github.com/golioth/ostentus-hw)
* ClickBus headers
* USB C interface and power
* External SIM connector
* Multiple programming interfaces
  * 10 pin SWD (02x05 .127mm pitch), accessible from outside the case
  * 10 pin SWD Tag Connect (accessible from the top side of the board)
  * USB using the serail bootloader / MCUBoot

## The Aludel form factor

The Aludel form factor (Originally the "Aludel Mini" form factor) is based around the [Bud Boxes CU-1937-MB](https://www.budind.com/product/general-use-boxes/utilibox-style-l-series-utility-boxes-2/cu-1937-mb). This was further customized with a milled alternative ordered custom from Digikey, [described in more detail in this blog post](https://blog.golioth.io/low-volume-high-mix-mechanical-enclosures-for-iot-projects/). There are inserts that are 3D printed to target specific applications/Click boards, and a custom PCB front panel called [the Aludel Ostentus](https://github.com/golioth/ostentus-hw), which also is OSHW.

### Rev B Photos
![Aludel_Elixir_RevB_Top](https://github.com/golioth/elixir-hw/assets/1212045/c5b71876-6642-4acf-9caf-4de4d8658dae)
![Aludel_Elixir_RevB_Bottom](https://github.com/golioth/elixir-hw/assets/1212045/73ac59ee-7b25-4bd9-8c28-39c761961298)

## Purchase

The Elixir board is not available to purchase. Please contact [devrel@golioth.io](mailto:devrel@golioth.io) if you would like to arrange help with your manufacturing. 

## Usage with Reference Designs

[The Elixir is supported natively in the Reference Design Template](https://github.com/golioth/reference-design-template?tab=readme-ov-file#golioth-aludel-elixir). To use it in a build run the command:

`west build -p -b aludel_elixir/nrf9160/ns --sysbuild app`

## Hardware Lineage and License

This design was derived from [Jared Wolff's open source nRF9160 Feather board](https://github.com/circuitdojo/nrf9160-feather) and extended to fit the Aludel platform size. Additional items were added and some features removed or modified to fit the needs of Golioth Reference Designs

This board is released under the [CERN OHL-P (v2) license](https://opensource.org/license/cern-ohl-p). See [LICENSE](https://github.com/golioth/elixir-hw/blob/main/LICENSE) for more info.

Any replication or modification of this design must remove references to Golioth and The Golioth Logo, which is a trademark of Golioth, Inc.
