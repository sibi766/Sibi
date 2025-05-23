# Sibi
PIR Motion Sensor with ESP32 and LED This project demonstrates how to interface a PIR (Passive Infrared) motion sensor with an ESP32 microcontroller to detect motion and control an LED accordingly.

📋 Table of Contents Project Overview

Hardware Requirements

Circuit Diagram

Installation

Usage

Code Explanation

Enhancements

License

📖 Project Overview The goal of this project is to detect motion using a PIR sensor and respond by turning an LED on or off. When motion is detected, the LED lights up, and a message is printed to the serial monitor. This setup is ideal for basic motion detection applications, such as security systems or automated lighting.

🛠 Hardware Requirements ESP32 Development Board

HC-SR501 PIR Motion Sensor

LED

220Ω Resistor

Breadboard and Jumper Wires GitHub +14 GitHub Docs +14 Coding Boot Camp +14

🔌 Circuit Diagram Connect the components as follows: Ministry of Testing

PIR Sensor VCC to ESP32 3.3V

PIR Sensor GND to ESP32 GND

PIR Sensor OUT to ESP32 GPIO13

LED Anode (+) to ESP32 GPIO2 through a 220Ω resistor

LED Cathode (-) to ESP32 GND

🧰 Installation Set Up Arduino IDE for ESP32

Install the latest version of the Arduino IDE.

Add the ESP32 board to the Arduino IDE by following the instructions on the ESP32 Arduino GitHub repository.

Connect the ESP32 to Your Computer

Use a USB cable to connect the ESP32 board to your computer.

Select the Correct Board and Port

In the Arduino IDE, go to Tools > Board and select your ESP32 board model.

Go to Tools > Port and select the port to which your ESP32 is connected.

Upload the Code

Copy the provided code into the Arduino IDE.

Click the Upload button to compile and upload the code to the ESP32.

▶ Usage Once the code is uploaded:

Open the Serial Monitor (Tools > Serial Monitor) and set the baud rate to 115200.

When the PIR sensor detects motion, the LED will turn on, and "Motion detected!" will be printed to the Serial Monitor.

If no motion is detected, the LED will remain off, and "No motion." will be printed. PIR_PIN is set to GPIO13, which reads the output from the PIR sensor.

LED_PIN is set to GPIO2, which controls the LED.

In the setup() function, the PIR sensor pin is configured as an input, and the LED pin as an output. Serial communication is initialized for monitoring.

The loop() function continuously reads the state of the PIR sensor. If motion is detected (pirState == HIGH), the LED is turned on, and a message is printed. Otherwise, the LED is turned off, and a different message is printed. A short delay is added to prevent rapid state changes.

🚀 Enhancements For improved performance and efficiency, consider the following enhancements:

Implement Interrupts: Instead of continuously polling the PIR sensor, use interrupts to detect motion, which can be more efficient.

Adjust PIR Sensor Settings: Most PIR sensors have potentiometers to adjust sensitivity and delay time. Fine-tuning these can help reduce false positives.

Add a Warm-Up Delay: PIR sensors typically require a warm-up period after powering up to stabilize. Adding a delay in the setup() function can accommodate this.

Use External Libraries: Utilize libraries like ESPAsyncWebServer to create a web interface for monitoring motion detection remotely
