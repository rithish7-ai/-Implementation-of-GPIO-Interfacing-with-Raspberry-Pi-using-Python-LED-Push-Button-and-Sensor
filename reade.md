# EXP 2(E) GPIO INTERFACING WITH RASPBERRY PI PICO USING MICROPYTHON – LED, PUSH BUTTON, AND SENSOR

## Aim

To interface an LED, push button, and digital sensor with the GPIO pins of a Raspberry Pi Pico and control and monitor the connected devices using MicroPython in the Wokwi simulation environment.

---

# Hardware / Software Tools Required

* Raspberry Pi Pico
* LED
* 220Ω / 330Ω Resistor
* Push Button
* Digital Sensor such as PIR / IR Sensor
* Breadboard
* Jumper Wires
* Wokwi Online Simulator
* MicroPython

---

# Circuit Diagram

---

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/57082b36-7da7-4308-a0f5-63bd17287491" />


---

# GPIO Connections

| Component                  | Raspberry Pi Pico Pin      | GPIO    |
| -------------------------- | -------------------------- | ------- |
| LED Anode                  | GP15 through 220Ω resistor | GPIO 15 |
| LED Cathode                | GND                        | —       |
| Push Button                | GP14                       | GPIO 14 |
| Push Button other terminal | GND                        | —       |
| Sensor VCC                 | 3.3V                       | —       |
| Sensor GND                 | GND                        | —       |
| Sensor OUT                 | GP13                       | GPIO 13 |

> **Note:** The GPIO pin numbers can be changed according to the Wokwi circuit configuration.

---

# Procedure

## Step 1: Create the Wokwi Project

1. Open the **Wokwi online simulator**.
2. Create a new project using **Raspberry Pi Pico**.
3. Select **MicroPython** as the programming environment.
4. Add the following components:

   * Raspberry Pi Pico
   * LED
   * Resistor
   * Push Button
   * Digital Sensor
5. Place the components on the virtual breadboard.

## Step 2: Connect the LED

1. Connect GPIO 15 (GP15) of the Raspberry Pi Pico to a 220Ω resistor.
2. Connect the resistor to the anode of the LED.
3. Connect the cathode of the LED to GND.
4. The LED will be controlled through GPIO 15.

## Step 3: Connect the Push Button

1. Connect one terminal of the push button to GPIO 14 (GP14).
2. Connect the other terminal of the push button to GND.
3. Configure GPIO 14 as an input with an internal pull-up resistor.
4. When the button is pressed, the input will read LOW.

## Step 4: Connect the Sensor

1. Connect the sensor VCC to the appropriate supply voltage.
2. Connect the sensor GND to GND.
3. Connect the sensor OUT pin to GPIO 13 (GP13).
4. Configure GPIO 13 as a digital input.
5. The sensor output will be read by the Raspberry Pi Pico.

> **Note:** The sensor used in the experiment should provide a compatible digital output. If an analog sensor is used, an external ADC is required for analog-to-digital conversion.

## Step 5: Write the MicroPython Program

1. Open the MicroPython editor in Wokwi.
2. Import the required `Pin` and `time` modules.
3. Define the GPIO pins for the LED, push button, and sensor.
4. Configure the LED as an output.
5. Configure the push button and sensor as inputs.
6. Read the state of the push button and sensor continuously.
7. Turn ON the LED when the push button is pressed or the sensor detects an object.
8. Turn OFF the LED when neither condition is active.
9. Display the input and output states in the Wokwi Serial Monitor.

## Step 6: Run the Simulation

1. Start the Wokwi simulation.
2. Observe the initial state of the LED.
3. Press the virtual push button.
4. Observe that the LED turns ON.
5. Release the push button.
6. Activate the sensor.
7. Observe that the LED turns ON when the sensor detects an object.
8. Deactivate the sensor.
9. Observe that the LED turns OFF when both inputs are inactive.
10. Check the Serial Monitor for the GPIO states.

## Step 7: Verify the Output

1. Verify that the Raspberry Pi Pico starts the MicroPython program successfully.
2. Verify the push button input.
3. Verify the sensor input.
4. Verify that the LED responds to the input conditions.
5. Check the corresponding messages displayed in the Serial Monitor.
6. Record the observed input and output states.

---

# Program
```
from machine import Pin
from utime import sleep

sleep(0.01)  # Wait for USB to connect
print("Hello, Pi Pico!")

led = Pin(5, Pin.OUT)

while True:
    led.toggle()
    sleep(0.5)
```
# Observation

<img width="1906" height="871" alt="image" src="https://github.com/user-attachments/assets/c3edfe91-d9df-425b-b539-1b2d3959c5ac" />




# Result

The **GPIO interfacing of an LED, push button, and digital sensor with the Raspberry Pi Pico was successfully implemented using MicroPython in the Wokwi simulation environment**. The experiment demonstrated the configuration of GPIO pins as digital inputs and outputs, reading input signals from the push button and sensor, and controlling the LED based on the input conditions.
