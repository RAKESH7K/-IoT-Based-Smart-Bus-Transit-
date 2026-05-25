# 🚌 IoT-Based Smart Transit Management System

> An embedded IoT system for automated bus fare collection, passenger management, and real-time fleet tracking — eliminating manual conductors through RFID, GPS, and Wi-Fi integration.

---

## 📹 Demo

https://youtu.be/13fwKv90lpw

---

## 📌 Overview

Traditional public bus systems rely heavily on manual fare collection, which is slow, error-prone, and costly. This project presents a fully automated smart transit system built on a dual-microcontroller architecture that handles:

- Contactless RFID-based fare collection
- Automated entry/exit door control via servo motors
- Real-time passenger count and GPS location pushed to a web server
- Station alerts for passengers via buzzer

The system removes the need for a conductor entirely and provides operators with live fleet visibility through a web dashboard.

---

## 🧱 System Architecture

> 📎 *(Attach your Block Diagram image here)*

```
[RFID Card] → [EM-18 Reader] → [Arduino Nano]
                                      |
                              [Balance Check + Deduction]
                                      |
                              [LCD Display] + [Servo Motor - Entry Door]
                                      |
                              [NodeMCU ESP8266]
                                      |
                    ┌─────────────────┴──────────────────┐
              [GPS Module]                        [Wi-Fi → Web Server]
         (Location Tracking)              (Live Passenger Count + Location)
                                      |
                              [EM-18 Reader - Exit]
                                      |
                              [RFID Tag Match Check]
                                      |
                              [Servo Motor - Exit Door]
```

---

## ⚙️ How It Works

> 📎 *(Attach your Flowchart image here)*

### Entry Flow
1. Passenger scans RFID card on **Entry EM-18 Reader**
2. **Arduino Nano** reads tag → verifies balance
3. Passenger selects destination via **keypad**
4. Fare is deducted → **LCD** displays balance and receipt
5. **Servo motor** opens entry door
6. Passenger count incremented → data pushed to **web server via NodeMCU**

### Exit Flow
1. Bus reaches destination → **GPS module** confirms station
2. **Buzzer** alerts passenger at their station
3. Passenger scans RFID card on **Exit EM-18 Reader**
4. Tag verified against web server data
5. **Servo motor** opens exit door
6. Exit count updated on web server in real-time

---

## 🔧 Hardware Components

| Component | Model | Function |
|---|---|---|
| Microcontroller 1 | Arduino Nano | RFID processing, fare logic, door control |
| Microcontroller 2 | NodeMCU ESP8266 | Wi-Fi connectivity, web server communication |
| RFID Reader (×2) | EM-18 Module | Entry and exit passenger authentication |
| GPS Module | NEO-6M | Real-time bus location tracking |
| Display | 16×2 LCD | Passenger info, balance, and receipt |
| Door Control (×2) | Servo Motor | Automated entry and exit door operation |
| Alert | Buzzer | Station arrival notification |
| Input | 4×4 Keypad | Destination selection |

---

## 🔌 Circuit Diagram

> 📎 *(Attach your Circuit Diagram image here)*

---

## ✨ Key Features

- ✅ **100% Cashless** — RFID card replaces cash, no conductor needed
- ✅ **Dual-door control** — Independent servo-controlled entry and exit
- ✅ **Real-time tracking** — GPS + Wi-Fi pushes live location and occupancy to web
- ✅ **Fraud prevention** — Exit door only opens on RFID tag match at correct station
- ✅ **Station alerts** — Buzzer notifies passengers at their destination
- ✅ **Scalable** — Web dashboard accessible remotely by operators

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Firmware | Embedded C (Arduino IDE) |
| Communication | UART (GPS), I2C (LCD), SPI (RFID) |
| Connectivity | Wi-Fi via NodeMCU ESP8266 |
| Backend | Web Server (NodeMCU hosted) |
| Hardware | Arduino Nano, NodeMCU ESP8266 |
| Protocols | RFID (125kHz), GPS NMEA sentences |

---

## 🚀 Future Scope

- [ ] Mobile app integration for balance top-up and trip history
- [ ] Cloud backend (Firebase / AWS IoT) for multi-bus fleet management
- [ ] QR code support alongside RFID for wider accessibility
- [ ] ML-based passenger demand prediction per route
- [ ] Integration with city transit APIs for dynamic routing

---

## 📄 Project Report

> 📎 *(Attach or link your full project report PDF here if available)*

---

## 👤 Author

**Rakesh K**
MSc Electronics | University of Calicut | 4th Rank Holder

[![LinkedIn](#)](your-linkedin-url) [![GitHub](#)](your-github-url)

---

> *Built as MSc Electronics final year project — demonstrating end-to-end embedded system design, hardware-software integration, and IoT connectivity.*
