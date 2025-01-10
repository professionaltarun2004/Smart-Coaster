# Smart Coaster

The Smart Coaster is an innovative project aimed at automating the heating process of beverages. It leverages the ESP-32 microcontroller, a Peltier heater, and Blynk IoT platform for real-time control and monitoring.

## Features
- **Automated Heating**: Uses a Peltier heater controlled by temperature readings.
- **Blynk Integration**: Remotely monitor and control the coaster using the Blynk IoT platform.
- **Temperature Sensing**: Accurate temperature readings via a Dallas Temperature sensor.
- **User-Controlled Slider**: Adjust heating thresholds in real-time using the Blynk app.

---

## Hardware Requirements
- ESP-32 Microcontroller
- Peltier Heater
- Dallas Temperature Sensor (DS18B20)
- External LED
- Wi-Fi Connection

---

## Software Requirements
- Arduino IDE
- Blynk Library
- Dallas Temperature Sensor Library
- OneWire Library

---

## Circuit Connections
- **Temperature Sensor**: Connect the data pin to GPIO 4.
- **External LED**: Connect the LED to GPIO 5.
- **Internal LED**: Use the built-in LED on GPIO 2.

---

## Setup Instructions
1. **Install Dependencies**: Ensure the required libraries (Blynk, DallasTemperature, and OneWire) are installed in Arduino IDE.
2. **Configure Wi-Fi and Blynk Credentials**:
   - Replace `YOUR TOKEN` with your Blynk Authentication Token.
   - Replace `WIFI_SSID` and `WIFI_PASSWORD` with your Wi-Fi credentials.
3. **Upload Code**: Compile and upload the code to the ESP-32 using Arduino IDE.
4. **Blynk App Setup**:
   - Create a new Blynk project and configure Virtual Pins V0, V2, and V3.
   - Link your Blynk account to the ESP-32.

---

## How It Works
1. **Initialization**: The ESP-32 connects to the Wi-Fi network and Blynk server.
2. **Temperature Monitoring**:
   - The Dallas Temperature sensor reads the current beverage temperature.
   - The temperature value is sent to the Blynk app (Virtual Pin V3).
3. **User Control**:
   - The user sets a desired threshold temperature using a slider in the Blynk app (Virtual Pin V0).
   - The threshold value is compared with the current temperature.
4. **Automated Heating**:
   - If the threshold temperature is higher than the current temperature, and the internal LED is on, the external LED (representing the heater) turns on.
   - Otherwise, the heater is turned off.

---

## Code Highlights
- **Generalized Sensitive Data**:
  - `BLYNK_AUTH_TOKEN`, `WIFI_SSID`, and `WIFI_PASSWORD` are placeholders for your credentials.
- **Key Functions**:
  - `BLYNK_WRITE(V0)`: Reads slider values and updates the temperature threshold.
  - `checkConditions()`: Controls the heating mechanism based on user input and current temperature.

---

## Potential Enhancements
- Add additional safety features such as overheat protection.
- Expand functionality to include cooling using the Peltier module.
- Integrate voice control for more user-friendly operation.

---

## Troubleshooting
- **Wi-Fi Connection Issues**:
  - Verify Wi-Fi credentials.
  - Check the network status in the Serial Monitor.
- **Temperature Readings Incorrect**:
  - Ensure the Dallas Temperature sensor is correctly wired.
  - Check for loose connections.
- **Heater Not Turning On**:
  - Verify the slider value is greater than the current temperature.
  - Check the external LED wiring and GPIO 5 configuration.

---

## License
This project is open-source and available for personal and educational use. Please acknowledge the author for any derivative works.

---

For any issues or suggestions, feel free to open an issue in this repository.

