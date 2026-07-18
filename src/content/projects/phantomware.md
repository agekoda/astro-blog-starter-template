---
title: "Phantomware"
tagline: "A fully custom Flipper Zero alternative built around the ESP32-S3"
description: "A fully custom multi-tool device based on the ESP32-S3, designed for wireless analysis, signal interaction, and hardware experimentation."
category: "RF & Wireless"
status: "Complete"
order: 1
heroImage: "/images/projects/phantomware/hero.jpg"
gallery:
  - "/images/projects/phantomware/1.jpg"
  - "/images/projects/phantomware/2.jpg"
  - "/images/projects/phantomware/3.jpg"
---

A fully custom-built multi-tool device based on the ESP32-S3, designed for wireless analysis, signal interaction, and hardware experimentation — my take on a Flipper Zero, built from scratch.

## Hardware

- ESP32-S3 + custom PCBA
- 320×240 ST7789 TFT display
- 3000mAh battery (USB-C charging via TP4056)
- SD card storage
- 3× IR LEDs + IR receiver
- NRF24L01 expansion (GPIO-based module board)
- Temperature sensor + battery gauge
- Buzzer + 5-way navigation buttons

## Capabilities

- GPIO toolkit: PWM generator, oscilloscope, frequency analyser, voltmeter, UART bridge
- WiFi tools: scanning, monitoring, deauth (educational), beacon spam, evil portal, AP hosting
- Bluetooth tools: scanning, advertisement spoofing, device spam (Apple/Samsung/Windows)
- BadUSB / BadBT functionality
- ESP-NOW & NRF chat systems
- Expandable modules: GPS, PN532 NFC

## Software

- Modular UI with multiple menu styles
- File uploads over WiFi (SPIFFS)
- Fully extensible tool framework
