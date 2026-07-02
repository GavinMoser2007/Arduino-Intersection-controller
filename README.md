# Arduino-Intersection-controller
## Purpose of Project Design:
  In my local town, I have always found it confusing why the light always turned green at night when my car pulled up to one specific intersection. After years of wondering, I thought that it had to do with a pressure plate, a camera, or a sensor. In fact, it can often be any of these reasons. For this specific intersection in my town, the sensors would only be turned on after 9:00 to 10:00 pm, depending on the season. This saves time and unnecessary stops for drivers coming through on the main road. To accomplish this, the main road seemed to always be kept on a green light unless the intersection sensor detected a car entering from the back road. I decided to implement and design an example traffic controller using an Elegoo Uno R3. Once a car is detected, the controller safely cycles through the traffic light sequence before returning the main road to green. The goal of this project was to better understand how sensor-based traffic light systems work while recreating a real-world scenario using an Arduino-based controller. 
### Important Addition:
  Furthermore, I had decided to add to this project by using an IR receiver module. Laws have begun to take place that limit police chases. Also, heavy traffic often makes it difficult for emergency vehicles to reach people in need. To combat these issues, I decided to find a way to control and set the intersection lights to red at any time. Currently, intersections often have IR sensors that take in pulsating frequencies to determine if emergency vehicles are approaching, or they hold sound sensors, or networks use GPS tracking to allow for the traffic controller to communicate with vehicle locations. However, I decided to use a remote that sends signals to an IR receiver module.

## Component List:
- Elegoo Uno R3
- KY-022 IR Receiver
- HC-SR04 Ultrasonic Sensor
- 2x Green LED
- 2x Yellow LED
- 2x Red LED
- Elegoo IR Remote
- 6x 330 Ohm Resistors
- 31x Jumper Wires
- Breadboard

### Demonstration of Sensor:
https://github.com/user-attachments/assets/4f7a207f-c489-4b24-b5e6-5a1e746965b4

### Demonstration of Remote + IR Receiver:
https://github.com/user-attachments/assets/bb890c34-431f-4a53-b80a-ccc8376cf144

### Schematic within KiCad:
<img width="523" height="353" alt="Screenshot 2026-06-29 230305" src="https://github.com/user-attachments/assets/cb252446-077b-4b6f-ac91-d2e85f070e83" />

## What have I learned?
  After this project, I have begun to understand better how the Pulse Width Modulation (PWM) pins apply to different uses. For my specific project, I learned that they were not necessary, but I have found that they act the same way as simple digital pins with binary HIGH and LOW states. The main difference, however, is that these pins can adjust their duty cycle to have differing high pulse widths. This allows for a simulated analog voltage, in which devices that operate at input energy levels do not notice the rapid transitions between HIGH and LOW states.
  Within the realm of IR devices, specifically the IR remote and the IR receiver module, I was able to further understand how the process communicates. Within the coding process, I had to test the play/pause button within the Serial Monitor and determine what Hex code is picked up by the IR receiver. I researched further that this shortened result is converted into binary within the processor to be understood. These digital codes come from specific pulse widths, which the IR receiver picks up through its blinking characteristic that tends to "ignore" or limit external light from interfering with the signal. Specifically, with the KY-022 IR receiver, the blinking frequency, also known as the carrier detection frequency, has a characteristic of 38 kHz.
  As for the ultrasonic sensor, I’ve learned that it can do a lot more than just detect whether something is there. Using basic kinematic ideas, you can estimate an object’s speed by looking at how its measured distance changes over a short time window. That opens the door for different applications, and in a traffic‑control setup, the sensor could basically double as a simple speed detector for cars passing through. For the HC‑SR04 specifically, the distance readings come in at around 40 Hz, while typical traffic sensors can reach closer to 100 Hz. Higher reading frequencies usually mean more accurate speed measurements because the time gap between samples is smaller. And similar to how the IR receiver works, the ultrasonic sensor sends out pulses and measures the reflected waves to figure out what’s happening in front of it.

# Potential Code For Measuring Speed:
> long readDistance() {
    > digitalWrite(trigPin, LOW);
    > delayMicroseconds(2);
    > digitalWrite(trigPin, HIGH);
    > delayMicroseconds(10);
    > digitalWrite(trigPin, LOW);

    > long duration = pulseIn(echoPin, HIGH);
    > long distance = duration * 0.034 / 2;  // cm
    > return distance;
> }

> float measureSpeed() {
    > long d1 = readDistance();  
    > delay(25);                 
    > long d2 = readDistance();  
    > long deltaD = d1 - d2;   
    > float deltaT = 0.025;  
    > float speed = deltaD / deltaT; // cm/s
    > return speed;
> }


