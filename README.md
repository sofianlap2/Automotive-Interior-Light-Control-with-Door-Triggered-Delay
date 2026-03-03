# Automotive-Interior-Light-Control-with-Door-Triggered-Delay
Automotive Interior Light Control with Door-Triggered Delay


This project is a 12V automotive interior light controller designed to automatically turn on the cabin lamp when the door opens and gradually turn it off after a delay when the door closes.

The system was designed, built, and tested both in practical hardware implementation and circuit simulation.

<img width="1090" height="661" alt="image" src="https://github.com/user-attachments/assets/466e73f3-d13c-44c3-b866-3ffa55b6ec34" />
	System Specifications

Supply Voltage: 12V DC (Automotive battery)
Load: 12V Lamp
Lamp Current: 0.11A
Control Method: Discrete BJT transistor stages
Timing Element: RC delay network (100µF capacitor)


How It Works

1**RC Timing Network (Delay Control)
•	To increase the light turn-off delay time:
•	I used two 512kΩ resistors in parallel to create a higher effective resistance for controlled capacitor charging.
•	Another 512kΩ resistor pair is used:
•	One for controlled capacitor discharging.
•	One to reduce current consumption when the lamp is OFF.

This configuration optimizes:
	Delay timing
	Standby power consumption
	Stability of the trigger stage

2**Transistor Stages Operation

Q3 (Power Transistor Stage)
Responsible for allowing full lamp current (0.11A) at startup.

Q2 (Driver Stage)
Controls and supplies base current to Q3.
It ensures proper switching and isolates the timing stage from the load.

Q1 (Control Stage)
Works with the RC network.

When Q1 turns ON → it forces Q2 to switch state.
This action turns OFF Q3 after the delay time.

<img width="1090" height="1937" alt="image" src="https://github.com/user-attachments/assets/7bb0f5bd-a0da-4f89-a820-d1635aa7af50" />

The 100kΩ resistor ensures proper biasing and guarantees the lamp turns OFF completely after the delay.

