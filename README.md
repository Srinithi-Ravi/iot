##Smart Stick for Visually Impaired
#Project Overview
This project is an IoT-based smart stick designed to assist visually impaired individuals by enhancing their mobility and awareness of their surroundings. The smart stick integrates multiple sensors to provide real-time feedback about the environment, including obstacle detection, activity monitoring, and location tracking. This significantly improves upon traditional canes by offering a more comprehensive and interactive navigation aid.[1][2]
The core of the device is an ESP32 microcontroller, which processes data from an ultrasonic sensor for obstacle detection, a 3-axis accelerometer for step counting, and a GPS module for geolocation.[1] The user is alerted to obstacles through an audible buzzer.
Features
Real-Time Obstacle Detection: An HC-SR04 ultrasonic sensor detects obstacles within a 40 cm range.[3]
Audible Alerts: A buzzer provides immediate auditory feedback when an obstacle is detected.[1][4]
Activity Monitoring: An ADXL345 accelerometer tracks the user's steps.
Geolocation Tracking: A NEO-6M GPS module provides real-time latitude and longitude data.
IoT Integration: The ESP32 microcontroller allows for potential future enhancements like sending emergency alerts or connecting to a smartphone application.[5]
Hardware Requirements
Core Processing:
ESP32 Microcontroller Development Board
Sensors (Inputs):
HC-SR04 Ultrasonic Sensor (Obstacle Detection)
ADXL345 3-Axis Accelerometer (Step Counting)
NEO-6M GPS Module (Location Tracking)
Actuators (Outputs):
Active Buzzer (Auditory Feedback)
Power & Miscellaneous:
Portable Power Supply (e.g., 5V Power Bank or Li-Ion Battery)
Jumper Wires
Breadboard (for prototyping)
Circuit Connections
Here are the connections between the ESP32 and the various components:
HC-SR04 Ultrasonic Sensor
VCC to 5V on ESP32
GND to GND on ESP32
Trig to GPIO 23 on ESP32
Echo to GPIO 19 on ESP32
ADXL345 Accelerometer
VCC to 3.3V on ESP32
GND to GND on ESP32
SCL to GPIO 22 (SCL) on ESP32
SDA to GPIO 21 (SDA) on ESP32
NEO-6M GPS Module
VCC to 3.3V on ESP32
GND to GND on ESP32
TX to GPIO 16 (RX2) on ESP32
RX to GPIO 17 (TX2) on ESP32
Active Buzzer
Positive (+) to GPIO 18 on ESP32
Negative (-) to GND on ESP32
Procedure
1. Setting up the Arduino IDE
Install the Arduino IDE: Download and install the latest version from the official Arduino website.[6]
Install the ESP32 Board Manager:
Open the Arduino IDE.
Go to File > Preferences.
In the "Additional Board Manager URLs" field, add the following URL: https://espressif.github.io/arduino-esp32/package_esp32_dev_index.json
Go to Tools > Board > Boards Manager.
Search for "esp32" and install the package by Espressif Systems.[7][8]
Install Necessary Libraries:
Go to Sketch > Include Library > Manage Libraries.
Install the following libraries:
Adafruit Unified Sensor by Adafruit
Adafruit ADXL345 by Adafruit
TinyGPS++ by Mikal Hart
2. Assembling the Hardware
Connect all the components to the ESP32 microcontroller according to the "Circuit Connections" section above. It is recommended to use a breadboard for initial prototyping to ensure all connections are secure.
3. Uploading the Code
Connect the ESP32 to your computer using a USB cable.
Open the provided source code in the Arduino IDE.
Select the correct board and port:
Go to Tools > Board and select "ESP32 Dev Module" or the specific ESP32 board you are using.
Go to Tools > Port and select the COM port your ESP32 is connected to.[9]
Upload the code by clicking the "Upload" button. If you encounter issues during upload, you may need to press and hold the "BOOT" button on your ESP32 board when the IDE displays "Connecting...".
4. Testing the Smart Stick
Power the ESP32 using a portable power source.
Open the Serial Monitor in the Arduino IDE (Tools > Serial Monitor) and set the baud rate to 115200.
You should see the following data being printed:
Distance: The distance to the nearest obstacle in centimeters.
Steps: The number of steps taken.
GPS Data: Latitude, longitude, altitude, speed, and the number of satellites detected. (Note: The GPS module may take some time to get an initial fix, especially indoors).
Test the obstacle detection by placing an object in front of the ultrasonic sensor. The buzzer should sound when the object is within the 40 cm threshold.

Test the step counter by walking with the stick. The step count should increase.
