# Dashboard-Design-Using-CAN-Protocol

## 📑 Table of Contents

📌 Project Introduction
🎯 Project Objectives
💡 Key Highlights
🖼️ System Block Diagram
🏗️ System Architecture & Workflow
🔧 Hardware Components
💻 Software Tools & Technologies
📂 Project Directory Structure
🚀 Key Features & Functionalities
⚡ Working Principle
🔌 Pin Configuration & Connections
🖥️ LCD Display Output
📸 Project Demonstration Gallery
▶️ Compilation & Build Instructions
🧪 Testing & Debugging
📊 Results & Performance
🛠️ Challenges & Solutions
📈 Future Enhancements
🌐 Real-World Applications
📚 Learning Outcomes
👩‍💻 Author & Contact

## 📌 Project Introduction

**Dashboard Design Using CAN Bus** is an automotive embedded system project that demonstrates the use of **CAN communication** for exchanging vehicle-related information between multiple microcontroller nodes. The system is built around the **LPC2129 ARM7 microcontroller** and is designed to represent the basic functionality of an electronic vehicle dashboard.

The dashboard monitors key parameters including **engine temperature, fuel level, and turn-indicator status**. Sensor data is processed by dedicated nodes and transferred through the CAN network, while the Main Node presents the required information on an LCD.

The system is organized into three functional units:

* **Main Node** – Monitors the engine temperature using the DS18B20 sensor, receives fuel-level data through CAN, and presents the information on the LCD. It also handles the indicator switches and communicates the corresponding commands to the Indicator Node.

* **Fuel Node** – Measures the fuel level through the microcontroller’s built-in ADC and converts the sensor reading into fuel-percentage information. The processed data is then transmitted to the Main Node over the CAN bus.

* **Indicator Node** – Monitors CAN messages received from the Main Node and operates the appropriate LED indicators for left and right turn signals.

