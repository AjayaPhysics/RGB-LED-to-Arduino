# RGB-LED-to-Arduino
# RGB LED to Arduino

## Overview
This project demonstrates how to control an RGB LED (common cathode) using an Arduino. By varying the intensity of the Red, Green, and Blue pins using PWM (Pulse Width Modulation), you can create various colors.

---

## Components
| **Component**          | **Quantity** | **Description**                              |
|-------------------------|--------------|----------------------------------------------|
| Arduino Uno             | 1            | Microcontroller board                        |
| RGB LED (Common Cathode)| 1            | Combines red, green, and blue LEDs           |
| Resistors (220Ω)        | 3            | Current-limiting resistors for each color pin|
| Breadboard              | 1            | For organizing connections                   |
| Jumper Wires            | Several      | For connecting components                    |

---

## Connections
| **RGB LED Pin**    | **Description**     | **Arduino Pin**      |
|---------------------|---------------------|-----------------------|
| Common Cathode      | GND (Ground)       | GND                  |
| Red                 | Controls Red color | Digital Pin 9        |
| Green               | Controls Green color | Digital Pin 10      |
| Blue                | Controls Blue color | Digital Pin 11       |

---

## Arduino Code

Here is the Arduino code to control the RGB LED:

```cpp
// Define pins for RGB LED
#define RED_PIN 9
#define GREEN_PIN 10
#define BLUE_PIN 11

void setup() {
  // Set pins as outputs
  pinMode(RED_PIN, OUTPUT);
  pinMode(GREEN_PIN, OUTPUT);
  pinMode(BLUE_PIN, OUTPUT);
}

void loop() {
  // Red color
  analogWrite(RED_PIN, 255);   // Maximum brightness
  analogWrite(GREEN_PIN, 0);   // Turn off
  analogWrite(BLUE_PIN, 0);    // Turn off
  delay(1000);

  // Green color
  analogWrite(RED_PIN, 0);     // Turn off
  analogWrite(GREEN_PIN, 255); // Maximum brightness
  analogWrite(BLUE_PIN, 0);    // Turn off
  delay(1000);

  // Blue color
  analogWrite(RED_PIN, 0);     // Turn off
  analogWrite(GREEN_PIN, 0);   // Turn off
  analogWrite(BLUE_PIN, 255);  // Maximum brightness
  delay(1000);

  // Cyan color (Green + Blue)
  analogWrite(RED_PIN, 0);     
  analogWrite(GREEN_PIN, 255);
  analogWrite(BLUE_PIN, 255);
  delay(1000);

  // Magenta color (Red + Blue)
  analogWrite(RED_PIN, 255);
  analogWrite(GREEN_PIN, 0);
  analogWrite(BLUE_PIN, 255);
  delay(1000);

  // Yellow color (Red + Green)
  analogWrite(RED_PIN, 255);
  analogWrite(GREEN_PIN, 255);
  analogWrite(BLUE_PIN, 0);
  delay(1000);

  // White color (Red + Green + Blue)
  analogWrite(RED_PIN, 255);
  analogWrite(GREEN_PIN, 255);
  analogWrite(BLUE_PIN, 255);
  delay(1000);

  // Turn off all colors
  analogWrite(RED_PIN, 0);
  analogWrite(GREEN_PIN, 0);
  analogWrite(BLUE_PIN, 0);
  delay(1000);
}

Here’s a simple code to control an RGB LED (common cathode) using Arduino. Each color in an RGB LED is controlled by a separate pin, and we can mix colors by changing the intensity of each pin using PWM (Pulse Width Modulation).
RGB LED to Arduino
Connect the common cathode (ground) pin of the RGB LED to the GND pin on the Arduino.
Connect the Red pin of the RGB LED to digital pin 9 on the Arduino (with a current-limiting resistor, typically 220 ohms).
Connect the Green pin to digital pin 10.
Connect the Blue pin to digital pin 11.
