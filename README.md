# Embedded Secure IoT Device

## Overview
This project implements a secure IoT sensor node using an ESP32 microcontroller. The node collects environmental data and transmits it securely to the cloud using TLS-encrypted MQTT/HTTPS. It supports over-the-air (OTA) firmware updates and secure key storage.

## Hardware Requirements
- ESP32 development board (e.g., ESP32-WROOM or ESP32-S3).
- Built-in or external sensors (e.g., temperature, humidity, accelerometer).
- USB-to-UART cable for flashing and serial debugging.

## Software Requirements
- ESP-IDF toolchain.
- MQTT broker or cloud IoT service (e.g., AWS IoT Core, Azure IoT Hub).
- Python (for cloud testing and local scripts).
- Optional: OTA update server infrastructure.

## Build & Flash Instructions
1. Install ESP-IDF and set up the environment.
2. Clone this repository and configure project settings in `sdkconfig`.
3. Set the Wi-Fi credentials and MQTT endpoint in `main/config.h`.
4. Build the firmware using `idf.py build`.
5. Flash the ESP32 using `idf.py -p /dev/ttyUSB0 flash monitor`.
6. Verify that the node publishes sensor data to the MQTT topic.

## Features
- Secure TLS connection (mTLS) to the MQTT/HTTPS endpoint.
- Periodic sensor sampling and JSON payload encoding.
- OTA firmware update support using HTTPS.
- Secure storage of certificates and private keys in flash.
- Configurable sampling interval and QoS.

## Demo
The demo shows the ESP32 publishing sensor readings to a cloud dashboard, with data encrypted end-to-end. A script demonstrates triggering an OTA update and verifying the new firmware version. (Screenshots/ video to be added.)

## Future Work
- Implement CoAP support.
- Add battery monitoring and low-power modes.
- Integrate hardware secure element for stronger key protection.
