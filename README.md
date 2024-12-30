# IoT Object Detection and Data Logging System

This project implements an IoT-based object detection system using an **ESP8266 microcontroller**, an **IR sensor**, and a **buzzer**. The system monitors objects using the IR sensor, triggers a buzzer when an object is detected, and logs the detection data to **ThingSpeak**, a cloud-based platform for data visualization.
## Project Workflow
1. **IR Sensor**: Detects object presence (HIGH = object detected).
2. **Buzzer**: Provides immediate sound alerts.
3. **ESP8266**: 
   - Reads the sensor value.
   - Sends the data to ThingSpeak via an HTTP GET request.
4. **ThingSpeak**: Logs and visualizes the data for remote monitoring.
## Features
- **Object Detection**: Detects the presence of objects using an IR sensor.
- **Alert System**: Activates a buzzer when an object is detected.
- **Cloud Integration**: Sends detection data to ThingSpeak for remote monitoring and visualization.
- **Wi-Fi Connectivity**: Connects to a Wi-Fi network for IoT functionality.
## Hardware Requirements
1. **ESP8266** (e.g., NodeMCU)
2. **IR Sensor**
3. **Buzzer**
4. Breadboard and jumper wires
5. Wi-Fi-enabled network
## Software Requirements
- Arduino IDE (configured for ESP8266 development)
- Required Libraries:
  - `ESP8266WiFi.h`
  - `ESP8266HTTPClient.h`
## Pin Configuration
| Component      | GPIO Pin | NodeMCU Pin |
|----------------|----------|-------------|
| IR Sensor      | GPIO2    | D4          |
| Buzzer         | GPIO3    | D3          |
## Circuit Diagram
1. **IR Sensor**: Connect the signal pin to GPIO2 (D4).
2. **Buzzer**: Connect the positive terminal to GPIO3 (D3) and the negative terminal to GND.
3. Connect the ESP8266 to power (e.g., via USB).
## Installation
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-username/your-repo-name.git
   ```
2. **Configure Arduino IDE**:
   - Install the **ESP8266 board package** in the Arduino IDE.
   - Install the required libraries via the Library Manager.
3. **Modify the Code**:
   - Update the following placeholders in the code:
     - `SSID`: Your Wi-Fi network name.
     - `PASSWORD`: Your Wi-Fi password.
     - `SERVER`: ThingSpeak server URL (e.g., `http://api.thingspeak.com`).
     - `API KEY`: Your ThingSpeak channel API key.
4. **Upload the Code**:
   - Connect the ESP8266 to your computer.
   - Select the appropriate board and port in Arduino IDE.
   - Upload the code to the ESP8266.
## Usage
1. Power on the ESP8266.
2. The device connects to the specified Wi-Fi network.
3. When the IR sensor detects an object:
   - The buzzer activates.
   - The detection status is sent to ThingSpeak for logging and visualization.
4. Monitor the data on your ThingSpeak channel.
## ThingSpeak Configuration
1. Create a ThingSpeak account and a new channel.
2. Note the **API key** of the channel.
3. Configure the channel to display the `field1` data sent by the ESP8266.
