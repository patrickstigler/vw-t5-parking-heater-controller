# Automatic Preheater Tool

A compact DIY solution to automatically reactivate a vehicle preheater (e.g. VW T5) during cold conditions.

[![Ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/W7W51C9X4H)

---

## Overview

This project is a simple proof-of-concept (PoC) designed to automate the activation of a vehicle’s preheater remote.

Instead of modifying the vehicle or the heating system itself, this setup physically presses the remote button using a servo motor — triggered based on ambient temperature.

The system operates fully offline and is built with inexpensive, widely available components.

---

## How It Works

- The preheater remote is configured to run for **120 minutes**
- The system checks the ambient temperature every **2 minutes**
- If the temperature drops below **19°C**, a servo motor presses the remote button
- This restarts the heating cycle
- The process repeats indefinitely

---

## Features

- Fully autonomous operation  
- No modification of vehicle electronics required  
- Low-cost and easy to replicate  
- Modular and extendable design  

---

## Hardware

### Bill of Materials (BOM)

- Arduino Nano  
- Servo Motor (e.g. HS-303)  
- DHT11 Temperature Sensor  
- 3× M5x20 screws  
- Wires  
- Solder + soldering iron  
- PLA filament for 3D printing  

---

## Wiring

### Servo Motor

| Wire   | Connection        |
|--------|------------------|
| Red    | Arduino 5V       |
| Black  | Arduino GND      |
| Yellow | Arduino D9       |

### DHT11 Sensor

| Pin    | Connection        |
|--------|------------------|
| VCC    | Arduino 3.3V      |
| GND    | Arduino GND       |
| Signal | Arduino D4        |

---

## 3D Printed Housing

The enclosure is designed for standard FDM 3D printing.

**Material:** PLA  
**Estimated print time:** ~4 hours  

### Recommended Print Settings

- **Infill:**  
  - 20% for all parts  
  - 100% for `Mid_ButtonTrigger`  

- **Layer Height:**  
  - 0.3 mm  

- **Supports:**  
  - Not required  

---

## Software

The control logic is intentionally simple:

1. Wait for the current heating cycle to complete (120 minutes)
2. Check temperature every 2 minutes
3. If temperature < 19°C → trigger servo → press button
4. Repeat loop

---

## License

This project is licensed under the  
**Creative Commons Attribution 4.0 International (CC BY 4.0)** License.

You are free to:

- Use  
- Modify  
- Distribute  

As long as proper credit is given.

Full license text: https://creativecommons.org/licenses/by/4.0/

---

## Disclaimer

This project is a proof-of-concept and provided "as is".

- No guarantee of reliability or safety  
- Use at your own risk  
- Not intended for critical or safety-relevant systems  
