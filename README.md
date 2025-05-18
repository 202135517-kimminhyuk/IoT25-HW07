# BLE-based Distance Estimation System using ESP32

## Overview

This project implements a Bluetooth Low Energy (BLE) distance estimation system using two ESP32 boards.
The system estimates the distance between a BLE server and client based on the Received Signal Strength Indicator (RSSI).
A linear regression model was built from real-world data collected via the ESP32 client and tested against a known distance.

## Components

- **Hardware**: 2 x ESP32 Dev Boards, LED
- **Environment**: Arduino IDE, Python (for data analysis and plotting)
- **Communication**: BLE advertising (server) and scanning (client)

## How It Works

1. The **ESP32 BLE server** broadcasts advertising packets continuously.
2. The **ESP32 BLE client** scans for the server’s packets and reads the RSSI value.
3. Distance and power data are printed in real-time on the client's serial monitor.
4. If the calculated distance is **less than or equal to 0.05 meters**, the LED connected to the client board turns ON. Otherwise, it stays OFF.
5. These measurements were manually recorded and used to build a linear regression model in Python.



## Test Data & Model

The test dataset consists of 10 RSSI readings taken at known distances from the server.
A linear regression was applied to estimate the relationship between **Distance (cm)-x** and **Power (dBm)-y**.

The resulting regression equation was:
<img width="772" alt="스크린샷 2025-05-18 오후 7 28 45" src="https://github.com/user-attachments/assets/6eb96b64-9fce-4e67-a609-002bbf46bf64" />

