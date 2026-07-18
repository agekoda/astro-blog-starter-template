---
title: "Home Dock Display"
tagline: "A smart home hub aggregating data from six-plus sensor nodes"
description: "A central interface for aggregating and displaying environmental data from distributed sensors."
category: "Smart Home"
status: "Complete"
order: 3
heroImage: "/images/projects/home-dock-display/hero.jpg"
gallery:
  - "/images/projects/home-dock-display/1.jpg"
  - "/images/projects/home-dock-display/2.jpg"
---

A central interface for aggregating and displaying environmental data from distributed sensors around the house.

## Hardware

- ESP32-C3 Supermini
- 2.9” tri-colour e-ink display
- BMP280 + AHT21 (pressure, temp, humidity)
- RTC + buzzer
- External antenna

## Functionality

- Receives ESP-NOW data from 6+ sensor nodes
- Parses JSON sensor data
- Publishes to Home Assistant via MQTT
- Acts as both display + data intermediary
