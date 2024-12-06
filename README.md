# Waste Wise - Intelligent Waste Segregation System  

Waste Wise is an automated waste management solution that leverages Arduino and sensor technology to classify and sort waste into wet and dry categories.  

## Features  
- Automatic classification of wet and dry waste using a moisture sensor.  
- Ultrasonic sensor for waste detection and proximity measurement.  
- Servo motor-driven sorting mechanism for directing waste into designated bins.  
- Real-time data visualization for debugging and testing.  

## Components  
- **Arduino Uno:** The microcontroller for managing all operations.  
- **Ultrasonic Sensor (HC-SR04):** Detects the distance of waste items.  
- **Moisture Sensor (HW-390):** Measures the moisture content to classify waste.  
- **Servo Motor (SG90):** Mechanism for physically sorting the waste.  
- **Miscellaneous:** Jumper wires, breadboard, and a power supply.  

## Circuit Diagram  
[Include a diagram here if available, or describe the connections:](https://fritzing.org/)  
- Connect the Ultrasonic sensor: `TrigPin` to Pin 12, `EchoPin` to Pin 11.  
- Connect the Moisture sensor to Analog Pin A0.  
- Connect the Servo Motor to Pin 8.  

## Arduino Code  
Below is the core Arduino code used in the project:  
```cpp
#include <Servo.h>
Servo servo1;
const int trigPin = 12;
const int echoPin = 11;
long duration;
int distance = 0;
int potPin = A0;  // Analog pin connected to HW-390 moisture sensor
int soil = 0;
int fsoil;
int maxDryValue = 595;  // Threshold value for classifying dry and wet waste
int Ultra_Distance = 15;  // Distance threshold in cm between ultrasonic sensor and moisture sensor

void setup() 
{
  Serial.begin(9600);
  pinMode(trigPin, OUTPUT); 
  pinMode(echoPin, INPUT); 
  servo1.attach(8);
  Serial.println("Soil Sensor     Ultrasonic          Servo");
}

void loop() 
{
  distance = 0;  // Reset distance at the start of each loop
  for (int i = 0; i < 2; i++)
  {
    digitalWrite(trigPin, LOW);
    delayMicroseconds(7);
    digitalWrite(trigPin, HIGH);
    // Complete the rest of the loop logic here...
  }
}
