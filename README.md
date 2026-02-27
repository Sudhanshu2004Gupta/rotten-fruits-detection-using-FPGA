# 🍎 FPGA-Based Rotten Fruit Detection System

## 📌 Overview

The **FPGA-Based Rotten Fruit Detection System** is a real-time image processing project designed to automatically detect spoiled fruits using hardware-level analysis. The system captures live images using an OV7670 camera module and processes pixel data directly on an FPGA board such as **Basys 3** or **Artix-7**.

The FPGA analyzes RGB values of each pixel and calculates the percentage of dark/brown pixels in a frame. If the dark pixel percentage exceeds a predefined threshold (e.g., 30%), the fruit is classified as rotten. Upon detection, the system activates an LED and sends a UART signal to a WiFi module for mobile notification.

---

## 🎯 Features

* Real-time image processing on FPGA
* Dark pixel percentage-based spoilage detection
* UART communication
* LED status indication
* IoT-based mobile notification
* Scalable for industrial fruit sorting systems

---

## 🛠 Hardware Requirements

* FPGA Board (Basys 3 / Artix-7 or equivalent)
* OV7670 Camera Module
* ESP8266 WiFi Module
* Jumper wires
* Power supply

---

## 💻 Software Requirements

* Xilinx Vivado Design Suite
* Arduino IDE (for ESP8266 programming)
* Blynk IoT Platform

---

## ⚙ System Architecture

Camera → FPGA → Image Processing → Rotten Detection
↓
UART Transmission
↓
ESP8266 WiFi Module
↓
Mobile Notification

---

## 🧠 Detection Logic

1. Capture 640×480 frame.

2. Check each pixel:

   * If R, G, B < threshold → Count as dark pixel.

3. Compute:

   Dark Pixel % = (Dark Pixels / Total Pixels) × 100

4. If percentage > 30% → Rotten detected.

---

## 📡 Notification System

The FPGA sends a character (`'R'`) via UART when rotten fruit is detected.
The ESP8266 receives this signal and triggers a push notification using **Blynk**.

---

## 🚀 How to Run

1. Connect OV7670 camera to FPGA.
2. Upload Verilog code to FPGA using Vivado.
3. Connect FPGA TX to ESP8266 RX.
4. Upload Arduino code to ESP8266.
5. Open Blynk app and configure notification widget.
6. Place fruit in front of camera and test detection.

---

## 📊 Applications

* Food quality inspection
* Agricultural sorting automation
* Smart packaging industries
* Warehouse monitoring systems

---

## 🔮 Future Enhancements

* CNN-based classification on FPGA
* Cloud data logging
* LCD display for percentage output
* Multi-fruit classification

---

## 👨‍💻 Author

Sudhanshu Gupta
FPGA + Embedded Systems Enthusiast

---

If needed, this README can be converted into a properly formatted `.md` file for GitHub submission.
