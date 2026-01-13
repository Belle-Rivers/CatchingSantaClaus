# 🎄 Catching Santa Claus – IoT & XML Web Services Project

## Project Synopsis

This project was developed as a **joint academic system** combining concepts from **Internet of Things (IoT)** and **XML & Web Services** courses. It presents a simulated smart security solution designed to respond to unexpected motion during predefined sleeping hours, integrating hardware-based sensing with web-based data management.

The system operates by synchronizing a web interface, XML-based data storage, and an IoT simulation environment. User-defined sleeping schedules and security parameters are stored using XML, while an ESP32-based setup continuously monitors motion and reacts in real time. When activity is detected during restricted hours, the system triggers physical responses (door locking and alarm activation) and simultaneously requests user confirmation through a web interface.

This project focuses on system-level integration, demonstrating how IoT hardware components, XML-based data exchange, and web services can be designed, synchronized, and validated together to simulate a realistic, safety-critical application.

## Project Goal

To design and simulate a connected security system that combines **motion sensing, actuator control, XML data exchange, and web-based user interaction** within a unified architecture.

## System Overview

The system is composed of two tightly coupled layers:

### 🔹 Web & XML Layer
- User inputs sleeping hours and a deactivation code
- Data is stored and updated in structured XML files
- User responses and system events are logged
- HTTP is used for continuous data exchange

### 🔹 IoT Layer
- Motion is detected using a PIR sensor
- A servo motor simulates door locking and unlocking
- A buzzer acts as an audible alarm
- ESP32 enables WiFi communication with hosted XML files

## How the System Works

### Step 1: User Configuration
The user defines:
- Sleeping start and end time (24-hour format)
- A 4-digit deactivation code

These values are stored in `sleeping_hours.xml`.

### Step 2: Motion Detection During Sleep
If motion is detected within sleeping hours:
- The servo rotates to lock the door
- The buzzer is activated
- A notification asks the user whether the movement was caused by them

### Step 3: User Response Handling
- **Yes** → System deactivates, door unlocks
- **No** → User is prompted to enter the deactivation code
  - Incorrect code → System remains locked
  - Correct code → System deactivates successfully

### Step 4: Special Scenarios
- Temporary door access using a physical button
- Ignoring motion outside sleeping hours
- Continuous XML polling to detect updated schedules

## XML Data Structure

### `sleeping_hours.xml`
Stores live system configuration:
- `start` / `end`
- `response`
- `deactivation`
- `deactivationcode`
- `codematch`

### `all_logs.xml`
Stores system history:
- Timestamped log entries
- Records of motion events and user responses

📸 *Example XML Structure* 

<img width="813" height="385" alt="Screenshot 2026-01-13 at 2 57 54 AM" src="https://github.com/user-attachments/assets/7201bfdb-1c03-4227-90a8-027df52addcc" />

## Hardware Components (IoT Simulation)

- **ESP32** – Enables WiFi communication and HTTP requests  
- **PIR Motion Sensor** – Detects human movement  
- **Servo Motor** – Simulates door locking mechanism  
- **Buzzer** – Alerts the user and surroundings  
- **Push Button** – Allows temporary door access  

📸 *IoT Simulation on Wokwi*  

<img width="521" height="347" alt="Screenshot 2026-01-13 at 2 59 10 AM" src="https://github.com/user-attachments/assets/a0b04621-5ce9-4317-bf33-1bff1f6749ef" />

## Technologies Used

![Python](https://img.shields.io/badge/Python-FFD43B?style=for-the-badge&logo=python&logoColor=blue)
![XML](https://img.shields.io/badge/XML-FF6600?style=for-the-badge)
![PHP](https://img.shields.io/badge/PHP-777BB4?style=for-the-badge&logo=php&logoColor=white)
![ESP32](https://img.shields.io/badge/ESP32-000000?style=for-the-badge)
![IoT](https://img.shields.io/badge/Internet_of_Things-0088CC?style=for-the-badge)

## Alternative Use Cases

Although designed for home security during sleep, the system can be adapted for:
- Offices and workplaces
- Shops and malls
- Restricted-access facilities
- Time-based monitoring environments

## Possible Improvements

### Security Enhancements
- Camera integration
- Live video streaming
- Keypad-based authentication
- IP-based user identification
- Detailed activation duration logs

### User Experience
- Mobile and smartwatch notifications
- Enhanced UI using Bootstrap or templates
- Adjustable alarm intensity

## Academic Context

This project was jointly prepared for:
- **CEN467 – XML & Web Services**
- **CEN479 – Internet of Things**

Each report emphasizes different technical aspects, while this repository represents their **combined system implementation**.

## Copyright & Usage Restrictions

**_Copyright (c) 2026 Rawan El Shenieky_**  
All rights reserved.

This repository is provided for viewing and evaluation purposes **only**.  
**No permission** is granted to copy, modify, or redistribute this code.
