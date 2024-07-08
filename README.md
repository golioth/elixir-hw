# Elixir
The Elixir is part of Golioth's "Aludel" platform, a family of devices that makes it easier to connect hardware to the internet using [Golioth's Firmware SDK](https://github.com/golioth/golioth-firmware-sdk) and [cloud platform](https://console.golioth.io). The Aludel family of devices are widely used in [Golioth's Reference Designs](https://projects.golioth.io), which are end-to-end demonstrations of IoT devices targeted at different vertical applications. There is a custom hardware component--often made up of Aludel boards--as well as a Follow-Along Hardware component, which makes it easier for 

Prominently featured on Aludel boards, including this one, are Click Bus headers. This is a pinout/standard from Mikroelectronika and supported by their wide range of plug-in sensor boards. We chose this standard for maximum hardware swappability, enabling our users to change to a different targeted sensor or industry vertical by replacing one or two click boards. 

This is released as Revision C of the Elixir. Revisions A and B were internal-only and the naming will be maintained for continuity.

## On the board
* nRF9160 - Cat M1 / NB-IOT / GPS chip with dual core Cortex M33 processing
* ESP32-C3 - Running ESP-AT firmware, interfaced to the nRF9160 over UART
* BME280 - Weather sensor from Bosch, common to many Golioth designs
* Power
  * Low quiescent buck circuit, inherited from Feather Board
  * 5V boost to service the 5V output on the ClickBus
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

## Purchase

The Elixir board is not available to purchase. Please contact [devrel@golioth.io](mailto:devrel@golioth.io) if you would like to arrange help with your manufacturing. 

## Usage with Reference Designs

[The Elixir is supported natively in the Reference Design Template](https://github.com/golioth/reference-design-template?tab=readme-ov-file#golioth-aludel-elixir). To use it in a build run the command:

`west build -p -b aludel_elixir_ns app`

## Hardware Lineage and License

This design was derived from [Jared Wolff's open source nRF9160 Feather board](https://github.com/circuitdojo/nrf9160-feather) and extended to fit the Aludel platform size. Additional items were added and some features removed or modified to fit the needs of Golioth Reference Designs

This board is released under the [CERN OHL-P (v2) license](https://opensource.org/license/cern-ohl-p). See license.txt for more info.
