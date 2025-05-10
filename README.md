🚪 Ultrasonic Door with LED & Buzzer Feedback
This Arduino project uses an ultrasonic sensor to detect proximity. When someone approaches, it:

Opens a servo-controlled door

Switches from a red LED to a blue LED

Plays a “bump... bump... bump” buzzer sound while the door is open

When the person moves away, it:

Closes the door after a delay

Turns the red LED back on

Stops the buzzer

🔧 Components Used
Component	Quantity
Arduino Uno/Nano	1
Ultrasonic Sensor (HC-SR04)	1
Servo Motor	1
Red LED	1
Blue LED	1
Buzzer	1
Resistors (220Ω)	2
Breadboard & Jumper Wires	As needed

🧠 How It Works
Ultrasonic sensor detects an object closer than 20 cm.

Door (servo motor) opens if it’s not already open.

Blue LED turns on and red LED turns off.

While the blue LED is ON, the buzzer plays intermittent “bump bump” sounds.

If no object is detected for 2 seconds, the servo closes the door, the red LED turns on, and the buzzer stops.

🔌 Pin Connections
Component	Arduino Pin
Ultrasonic Trigger	D2
Ultrasonic Echo	D3
Red LED Anode	D4
Red LED Cathode	D8
Blue LED Cathode	D7
Blue LED Anode	D5
Servo Signal	D6
Buzzer	D12

Both red and blue LEDs have their cathodes grounded via D8 and D7 respectively. Anodes are connected through 220Ω resistors.

📦 How to Use
Upload the Arduino sketch to your board.

Wire the components according to the table above.

Power the Arduino using USB or external power.

Walk in front of the ultrasonic sensor (within 20 cm).

Watch the door open, blue LED light up, and buzzer go “bump… bump…”

Step away to trigger the door to close and reset.

⚙️ Customization
You can tweak behavior by changing these constants in the code:

cpp
Copy
Edit
const float thresholdDistance = 20.0;      // Detection range in cm
const unsigned long closeDelay = 2000;     // Delay before closing (ms)
const unsigned long bumpOnTime = 100;      // Buzzer on duration (ms)
const unsigned long bumpOffTime = 800;     // Time between bumps (ms)
🛠️ Requirements
Arduino IDE

USB cable

Basic understanding of wiring

🧪 Troubleshooting
Buzzer not working? Check pin 12 and your transistor setup if you're using one.

Servo jittering? Make sure it's powered properly (sometimes needs more current).

Distance detection failing? Verify ultrasonic wiring and ensure it’s not blocked.
