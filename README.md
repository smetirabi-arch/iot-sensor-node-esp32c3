# iot-sensor-node-esp32c3
Custom open-source ESP32-C3-02 IoT sensor node PCB featuring integrated TP4056 Li-ion battery charging with protection, BME280 environmental sensing, ambient light/sound sensors, I2C OLED display, and microSD/flash storage. Includes full KiCad hardware design, ESP32 firmware, and documentation. MIT licensed. Ideal for IoT prototyping.

SmartNode — ESP32-C3 IoT Sensor Node with Integrated Li-ion Power Management

Custom open-source ESP32-C3-02 IoT sensor node PCB featuring integrated TP4056 Li-ion battery charging with protection, BME280 environmental sensing, ambient light/sound sensors, I2C OLED display, and microSD/flash storage. Includes full KiCad hardware design, ESP32 firmware, and documentation. MIT licensed. Ideal for IoT prototyping.


Table of Contents


Overview
Key Features
System Architecture
Hardware Details

Microcontroller
Power Management
Sensors & Storage
Display & Indicators



Design Highlights
Applications
Repository Structure
Getting Started
Documentation
License



Overview

SmartNode is a custom-designed PCB for compact, battery-powered IoT applications, built around the ESP32-C3-02 SoC. The board integrates a complete power management subsystem using the TP4056 Li-ion battery charger IC, enabling safe, efficient charging of a single-cell Li-ion battery while supporting a rich set of onboard sensors and peripherals for real-world environmental monitoring and data logging.

This repository provides everything needed to build, program, and deploy the board: schematics, PCB layout files, firmware source code, and full documentation.


Key Features


Microcontroller: ESP32-C3-02 SoC — Wi-Fi and Bluetooth Low Energy (BLE) connectivity
Power Management: TP4056 IC for single-cell Li-ion charging with thermal regulation
Battery Protection: Under-voltage lockout (UVLO) and trickle charging
Environmental Sensing: BME280 (temperature, humidity, pressure), ambient light sensor, sound sensor
Storage: MicroSD card reader + onboard flash memory
Display: I2C OLED for real-time data visualization
Power Inputs: USB-C (charging + data) and JST LiPo connector
Status Indicators: LEDs for charging and full-charge states



System Architecture

SmartNode is organized into four functional subsystems, coordinated by the ESP32-C3-02 over I2C and SPI:


Processing & Connectivity — ESP32-C3-02 SoC
Power Management — TP4056 charging circuit and voltage regulation
Sensing & Storage — Environmental sensors, OLED display, SD card, flash memory
User Feedback — Status LEDs and display output



Hardware Details

Microcontroller

The ESP32-C3-02 is a RISC-V-based SoC with integrated Wi-Fi and BLE. It was chosen for its low power consumption, sufficient I2C/SPI/UART peripheral support, native wireless stack, and small footprint — making it well suited for compact, battery-powered IoT devices.

Power Management


TP4056 charging IC — provides constant-current/constant-voltage (CC/CV) charging, thermal regulation, and programmable charge current (set via external resistor)
Automatic charge termination — prevents overcharging once the battery reaches full voltage
UVLO & trickle charging — protects against deep discharge and safely recovers depleted batteries
USB-C — powers the system and charges the battery; also used for firmware flashing/debugging
JST LiPo connector — direct single-cell Li-ion/LiPo battery connection
Regulated power delivery — ensures stable operation whether powered via USB or battery


Sensors & Storage

ComponentFunctionBME280Temperature, humidity, and barometric pressure sensingAmbient light sensorEnvironmental light-level detectionSound sensorAmbient noise/acoustic sensingMicroSD card readerLocal, expandable data storageOnboard flash memoryFast, non-removable storage for firmware/cached data

All sensors communicate over I2C (SD storage typically over SPI), keeping the architecture modular and easily expandable with additional I2C devices.

Display & Indicators


I2C OLED display — real-time visualization of live sensor readings, no external device required
LED indicators — signal charging status (charging vs. fully charged)



Design Highlights


Integrated Power Supply — USB-C and TP4056 work together to manage charging and system power seamlessly
Modular, Expandable Architecture — additional I2C sensors can be added with minimal hardware changes
Safe, Efficient Charging — programmable current and automatic termination protect battery health
Compact, Reliable PCB Layout — optimized traces to minimize power loss, with thermal management around the TP4056 and other heat-sensitive components



Applications


IoT edge devices for environmental monitoring
Battery-powered data logging systems
General-purpose prototyping platform for ESP32-based hardware projects



Repository Structure

├── hardware/         # KiCad schematic and PCB layout files
├── firmware/          # ESP32-C3-02 source code
├── docs/
│   ├── datasheets/    # Component datasheets (TP4056, sensors, etc.)
│   ├── assembly.md    # Step-by-step assembly instructions
│   └── testing.md     # Testing and validation procedures
├── LICENSE
└── README.md



Documentation

Detailed documentation is available in the docs/ folder, including:

Component datasheets
Assembly instructions
Testing and validation procedures
