SmartGateSonic

🚧 Automated Barrier System with Ultrasonic Sensor

SmartGateSonic is an Arduino-based project that automates a gate or barrier system using an ultrasonic sensor (HC-SR04) to detect approaching objects, such as vehicles or people. When an object is within 50 cm, the system activates a servo motor to open the barrier, lights up a blue LED, and triggers a short buzzer beep. Once the object moves away, the barrier closes after a 5-second delay, and a red LED turns on. This project is perfect for home automation enthusiasts and IoT hobbyists looking to build a smart, hands-free gate system.

🛠️ Hardware Components





Arduino Uno (or compatible microcontroller)



HC-SR04 Ultrasonic Distance Sensor



SG90 Servo Motor



Red LED (with anode/cathode configuration)



Blue LED (with anode/cathode configuration)



Buzzer (active or passive)



Jumper Wires



Breadboard (optional for prototyping)



Resistors (220–330Ω for LEDs, if needed to limit current)

⚙️ Pin Configuration







Component



Arduino Pin





Ultrasonic Trigger



D2





Ultrasonic Echo



D3





Red LED Anode



D4





Red LED Cathode



D8





Blue LED Anode



D5





Blue LED Cathode



D7





Servo Motor



D6





Buzzer



D12

🚦 Functional Description





Idle State:





Barrier is closed (servo at 0°).



Red LED is ON, blue LED is OFF.



Buzzer is OFF.



Object Detected (within 50 cm):





Barrier opens (servo rotates to 90°).



Red LED turns OFF, blue LED turns ON.



Buzzer emits a 100ms beep.



Object Leaves:





After 5 seconds of no detection, the barrier closes.



Red LED turns ON, blue LED turns OFF.

🧠 Code Behavior

The Arduino code (SmartGateSonic.ino) manages the system with the following logic:





getDistance(): Measures distance using the HC-SR04 ultrasonic sensor by sending a pulse and calculating the echo time.



loop(): Continuously monitors the distance, controlling the servo, LEDs, and buzzer based on object proximity and timing.

Key Variables





thresholdDistance: 50 cm (detection range).



closedAngle: 0° (servo position when closed).



openAngle: 90° (servo position when open).



closeDelay: 5000 ms (delay before closing after no detection).

📝 Customization





Detection Range: Adjust thresholdDistance in the code to change the detection sensitivity (e.g., 30 cm for closer objects).



Servo Angles: Modify openAngle and closedAngle to match your barrier’s mechanical requirements.



Delay Before Closing: Change closeDelay (in milliseconds) to adjust how long the barrier stays open after the object leaves.



Buzzer Behavior: Alter the delay(100) in the buzzer activation code to change the beep duration.

🔐 Safety Notes





Power Supply: Ensure your Arduino and servo motor are powered by a stable source (e.g., 5V USB or external supply). Overloading the Arduino’s 5V pin can cause damage.



Servo Load: Verify that the servo can handle the barrier’s mechanical load. Use an external power source for the servo if necessary.



LED Current: Include appropriate resistors (220–330Ω) for LEDs to prevent overcurrent, especially if not using cathode pins as ground.



Ultrasonic Sensor: Mount the HC-SR04 securely to avoid false readings from vibrations or obstructions.

🛠️ Setup Instructions





Connect the Hardware:





Wire the components according to the pin configuration table.



Ensure proper grounding (e.g., red/blue LED cathode pins D8/D7 set to LOW).



Upload the Code:





Open SmartGateSonic.ino in the Arduino IDE.



Install the Servo library via the Arduino Library Manager.



Upload the code to your Arduino Uno.



Test the System:





Power the Arduino and place an object within 50 cm of the ultrasonic sensor.



Verify that the barrier opens, blue LED lights up, and buzzer beeps.



Move the object away and confirm the barrier closes after 5 seconds with the red LED on.

📂 Repository Contents





SmartGateSonic.ino: Main Arduino sketch for the automated barrier system.



README.md: This file, containing project details and setup instructions.



(Optional) Add a wiring_diagram.png or Fritzing schematic for visual setup guidance (to be added later).

🚀 Future Enhancements





Add an LCD display to show distance or system status.



Implement a manual override button for opening/closing the barrier.



Integrate Wi-Fi (e.g., ESP8266) for remote control via a smartphone app.

📜 License

This project is licensed under the MIT License. See the LICENSE file for details.



Built with 💡 by [Your Name/Team Name]. Contributions and feedback are welcome!