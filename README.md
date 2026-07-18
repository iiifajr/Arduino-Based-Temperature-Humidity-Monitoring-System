# 🌡️ Arduino-Based Temperature & Humidity Monitoring System

A physical embedded system prototype designed to measure and display ambient environmental temperature and relative humidity metrics in real-time. The system features an ATmega328P-based Arduino Uno microcontroller interfaced with a DHT11 digital sensor, outputting high-precision parameters onto a 16x2 character LCD screen.

---

## 🔗 Project Resources & Live Demo

You can access the full project repository and documentation files via the link below:

https://drive.google.com/drive/folders/1h4XUBORqX9rTnv4yuvm11DMNYmOQBmAT

---

## 📊 System Architecture & High-Level Block Diagram

The system architecture is structured into four primary operational blocks to ensure reliable end-to-end data processing and display:

1. **Power Supply Block:** Delivers stable 5V DC power via a Type-B USB connection to host the platform.
2. **DHT11 Sensing Block:** Samples ambient temperature and relative humidity values externally.
3. **Arduino Uno Processing Core:** Decodes the incoming single-wire serial stream, evaluates the checksum bytes, and handles floating-point data conversion.
4. **LCD Output Block (HMI):** A Human-Machine Interface designed for clear, direct user readability under various ambient environmental scales.

<img width="1280" height="753" alt="IMG_5376" src="https://github.com/user-attachments/assets/d6385846-e0e8-4690-8c08-b279ae330341" />


---

## 🔌 Circuit Schematic & Interfacing Specifications

The prototype was constructed on an 830-tie-point solderless breadboard using optimized, color-coded wiring. Critical interface connections are organized as follows:

- **DHT11 Sensor:** Connected via a single-wire bidirectional serial interface to Arduino **Digital Pin 2**, stabilized with a 10 kΩ pull-up resistor.
- **16x2 Character LCD:** Operated in an efficient **4-bit mode** utilizing data lines **D4–D7** mapped directly to Arduino **Digital Pins 5, 4, 3, and 2**.
- **Human-Machine Interface (HMI) Calibration:** Features a 10 kΩ linear potentiometer connected to the **V0** pin to adjust display contrast and guarantee optimum visibility.

<img width="1149" height="693" alt="IMG_5375" src="https://github.com/user-attachments/assets/007e398e-6c6d-4938-bf85-edc405728ef6" />


---

## 💻 Firmware Design & Key Implementations

The system's firmware was developed in C++ within the Arduino IDE workspace, relying on open-source hardware abstraction libraries (DHT and LiquidCrystal) to minimize code complexity and enhance measurement stability.

### Key Logic Flow:

- **`setup()` State:** Runs once during device boot sequence to initialize the 16x2 screen, print a welcoming logo for 2 seconds, and activate the DHT11 serial communication channel.
- **`loop()` Routine:** Executes an infinite loop every 2 seconds (the minimum sampling interval for DHT11 calibration), reading sensory data as floating-point metrics, checking for "NaN" transmission faults, and programmatically updating both LCD character lines.

---

## 📈 Specifications & Environmental Scope

| Metric Parameters | Operational Range | Accuracy Tolerance |
| :--- | :--- | :--- |
| **Ambient Temperature** | $0^\circ\text{C}$ to $50^\circ\text{C}$ | $\pm2^\circ\text{C}$ |
| **Relative Humidity (RH)** | 20% to 90% | $\pm5\%$ |
| **Refresh & Sampling Rate** | Every 2,000 ms (2s) | Real-time continuous stream |

---

## 👥 Project Team & Affiliation

* **Eng. Fajr Aldajani**
  * 🔗 [GitHub Profile](https://github.com/iiifajr)

* **Eng. Noura Abbad Al-Qathami**
  * 🔗 [GitHub Profile](https://github.com/alotibin212-glitch)

* **Eng. Batool Falah Alguthami**
  * 🔗 [GitHub Profile](https://github.com/batoolotb90-png)

* **Eng. Asayel Hussain Al-Nufaiey**
  * 🔗 [GitHub Profile](https://github.com/user)

---
* **Affiliation:** Taif University
* **Project Status:** Completed Successfully! 🚀
