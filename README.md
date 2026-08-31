# Dashboard-Design-Using-CAN-Protocol

## 📑 Table of Contents

📌 Project Introduction

🎯 Project Objectives

❗ Problem Statement

🔧 Hardware Components

💻 Software Tools & Technologies

🖼️ System Block Diagram

🏗️ Project Workflow

📂 Project Directory Structure

🖥️ LCD Display Output

▶️ Compilation & Build Instructions

🚀 Key Features 

📈 Future Scope

👩‍💻 Author 

## 📌 Project Introduction

**Dashboard Design Using CAN Bus** is an automotive embedded system project that demonstrates the use of **CAN communication** for exchanging vehicle-related information between multiple microcontroller nodes. The system is built around the **LPC2129 ARM7 microcontroller** and is designed to represent the basic functionality of an electronic vehicle dashboard.

The dashboard monitors key parameters including **engine temperature, fuel level, and turn-indicator status**. Sensor data is processed by dedicated nodes and transferred through the CAN network, while the Main Node presents the required information on an LCD.

The system is organized into three functional units:

* **Main Node** – Monitors the engine temperature using the DS18B20 sensor, receives fuel-level data through CAN, and presents the information on the LCD. It also handles the indicator switches and communicates the corresponding commands to the Indicator Node.

* **Fuel Node** – Measures the fuel level through the microcontroller’s built-in ADC and converts the sensor reading into fuel-percentage information. The processed data is then transmitted to the Main Node over the CAN bus.

* **Indicator Node** – Monitors CAN messages received from the Main Node and operates the appropriate LED indicators for left and right turn signals.

## 🎯 Project Objectives

🚗 Develop an automotive dashboard using the LPC2129 ARM7 microcontroller.

🌡️ Monitor engine temperature using the DS18B20 sensor and display the value on an LCD.

⛽ Measure fuel level through the on-chip ADC and represent it as a fuel percentage.

📡 Implement CAN Bus communication for reliable data exchange between multiple nodes.

🔄 Control left and right indicators based on switch inputs and CAN commands.

🧩 Design a multi-node architecture consisting of Main, Fuel, and Indicator Nodes.

## ❗ Problem Statement

In conventional vehicle dashboards, different parameters such as engine temperature, fuel level, and indicator status need to be monitored and communicated efficiently between electronic control units. A system is required to collect these parameters, process the information, display important data to the driver, and control vehicle indicators through reliable communication between multiple embedded nodes.

This project addresses the problem by developing a CAN Bus-based automotive dashboard system using multiple LPC2129 ARM7 microcontroller nodes. The system enables the Main Node to monitor engine temperature, receive fuel-level information from the Fuel Node, and send indicator commands to the Indicator Node through the CAN network, providing a practical demonstration of distributed automotive communication.

## 🔧 Hardware Components

| Component | Purpose |
|---|---|
| 🧠 **LPC2129 ARM7 Microcontroller** | Main processing and control unit for the nodes |
| 📡 **MCP2551 CAN Transceiver** | Provides the physical interface for CAN communication |
| 🌡️ **DS18B20 Temperature Sensor** | Measures engine temperature |
| ⛽ **Fuel Gauge / Fuel Sensor** | Provides fuel-level information |
| 🖥️ **16×2 LCD Display** | Displays temperature, fuel percentage, and indicator status |
| 🔘 **Left Indicator Switch** | Activates the left indicator input |
| 🔘 **Right Indicator Switch** | Activates the right indicator input |
| 💡 **LED Indicators** | Represents left and right turn indicators |
| 🔌 **USB-to-UART Converter** | Provides serial communication with the PC |
| 🎚️ **Potentiometer** | Provides variable voltage for ADC testing |
| 🔗 **CANH & CANL Lines** | Carry CAN communication between nodes |
| ⚡ **CAN Termination Resistors** | Provide proper CAN bus termination |

## 💻Software Tools and Technologies

| 🛠️ Software / Technology             | 🎯 Purpose                                                |
| ------------------------------------- | --------------------------------------------------------- |
| **Embedded C**                        | Firmware development and control logic                    |
| **Keil C Compiler**                   | Compiling and building the Embedded C program             |
| **Flash Magic**                       | Programming/flashing the firmware into the LPC2129        |
| **CAN Protocol**                      | Communication between Main, Fuel, and Indicator Nodes     |
| **LPC2129 ARM7 Architecture**         | Microcontroller platform for implementing the system      |
| **ADC**                               | Converting the fuel-gauge analog signal into digital data |
| **External Interrupts (EINT0/EINT1)** | Detecting left and right indicator switch inputs          |
| **CAN Interface**                     | Sending and receiving data between nodes                  |

## 🖼️System Block Diagram

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/d22889bc-804a-412c-a6d5-df63f6df2585" />

## ⚙️Project Workflow

1. Initialize the system — The LPC2129 nodes, LCD, ADC, CAN interface, and required inputs are initialized.

2. Measure engine temperature — The Main Node continuously reads the temperature from the DS18B20 sensor.

3. Measure fuel level — The Fuel Node reads the fuel-gauge signal through the LPC2129's on-chip ADC and obtains the fuel percentage.

4. Transmit fuel information — The Fuel Node sends the fuel data to the Main Node through the CAN network.

5. Display dashboard data — The Main Node displays the engine temperature and fuel percentage on the LCD.

6. Detect indicator input — Left and right indicator switches generate the corresponding external interrupts at the Main Node.

7. Send indicator command — The Main Node transmits the indicator command through CAN to the Indicator Node.

8. Control indicators — The Indicator Node receives the CAN message and activates the appropriate left or right LED indicators

## Project Directory Structure
```
📁 Project
│
├── 📁 Main Node
│   ├── 📄 Main_LCD.c
│   ├── 📄 can.c
│   ├── 📄 can.h
│   ├── 📄 can_defines.h
│   ├── 📄 defines.h
│   ├── 📄 delay.c
│   ├── 📄 delay.h
│   ├── 📄 ds18b20.c
│   ├── 📄 ds18b20.h
│   ├── 📄 headers.h
│   ├── 📄 lcd.c
│   ├── 📄 lcd.h
│   ├── 📄 main_node.c
│   ├── 📄 pin_function_defines.h
│   ├── 📄 types.h
│   └── 📄 README.md
│
├── 📁 Fuel Gauge
│   ├── 📄 adc.c
│   ├── 📄 adc.h
│   ├── 📄 adc_defines.h
│   ├── 📄 can.c
│   ├── 📄 can.h
│   ├── 📄 can_defines.h
│   ├── 📄 defines.h
│   ├── 📄 delay.c
│   ├── 📄 delay.h
│   ├── 📄 fuel_node.c
│   ├── 📄 headers.h
│   ├── 📄 main.c
│   ├── 📄 types.h
│   ├── 📄 uart0.c
│   └── 📄 uart0.h
│
└── 📁 Indicator Node
    ├── 📄 can.c
    ├── 📄 can.h
    ├── 📄 can_defines.h
    ├── 📄 defines.h
    ├── 📄 headers.h
    ├── 📄 indicator_node.c
    ├── 📄 pin_function_defines.h
    ├── 📄 types.h
    ├── 📄 uart0.c
    └── 📄 uart0.h
   ```

## LCD Display Output

<img width="1412" height="1114" alt="image" src="https://github.com/user-attachments/assets/417055e2-07bd-4612-b24f-f13b05539c66" />

## ▶️ Compilation & Build Instructions

1. Open the project in Keil µVision.
2. Select the LPC2129 ARM7 microcontroller.
3. Build and compile the project.
4. Generate the required HEX file.
5. Flash the LPC2129 using Flash Magic.
6. Connect the Main, Fuel, and Indicator Nodes through the CAN Bus.
7. Connect the required sensors, switches, LCD, and LEDs.
8. Power ON the complete system.
9. Verify CAN communication between all nodes.
10. Observe the temperature, fuel percentage, and indicator status on the LCD.

## 🚀 Features

1. CAN-based communication is established between the Main, Fuel, and Indicator Nodes.

2. The LPC2129 ARM7 microcontroller serves as the core platform for embedded firmware development.

3. Engine temperature is continuously acquired through the DS18B20 sensor.

4. Fuel-level information is obtained through the built-in ADC of the LPC2129.

5. Dashboard parameters such as temperature, fuel percentage, and indicator status are presented on a 16×2 LCD.

6. MCP2551 CAN transceivers are used for communication across the CAN network.

7. Left and right turn signals are managed using CAN messages and external interrupts.

8. Dedicated LED outputs represent the left and right indicator signals.

9. The system follows a distributed three-node architecture for different dashboard functions.

10. Firmware is implemented in Embedded C for the LPC2129 platform.

## 📈 Future Scope

📱 Integration of a mobile application for remote dashboard monitoring.

🌐 Addition of IoT connectivity for cloud-based vehicle data monitoring.

🛰️ Integration of GPS for real-time vehicle location tracking.

📊 Addition of speed and RPM monitoring for a more complete dashboard.

🚨 Implementation of over-temperature and low-fuel warning alerts.

🔋 Addition of battery voltage and battery health monitoring.

🛞 Integration of tyre pressure monitoring (TPMS).

🧭 Addition of digital speedometer and odometer functionality.

🖥️ Upgrade from a 16×2 LCD to a TFT/graphical display for enhanced visualization.

🔐 Addition of vehicle security and RFID-based access control.

## 👩‍💻 Author

Vaishnavi Nimmakanti

🎓 B.Tech — Electronics & Communication Engineering

💻 Embedded Systems Enthusiast

🔧 Skills: Embedded C, C++, ARM7, LPC2129, CAN, UART, SPI, I2C

📡 Interested in Embedded Systems, Firmware Development & Automotive Electronics
