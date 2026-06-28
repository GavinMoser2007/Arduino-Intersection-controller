# Arduino-Intersection-controller
## Purpose of Project Design:
  In my local town, I have always found it confusing why the light always turned green at night when my car pulled up to one specific intersection. After years of wondering, I thought that it had to do with a pressure plate, a camera, or a sensor. In fact, it can often be any of these reasons. For this specific intersection in my town, the sensors would only be turned on after 9:00 to 10:00 pm, depending on the season. This saves time and unnecessary stops for drivers coming through on the main road. To accomplish this, the main road seemed to always be kept on a green light unless the intersection sensor detected a car entering from the back road. I decided to implement and design an example traffic controller using an Elegoo Uno R3. Once a car is detected, the controller safely cycles through the traffic light sequence before returning the main road to green. The goal of this project was to better understand how sensor-based traffic light systems work while recreating a real-world scenario using an Arduino-based controller. 
### Important Addition:
  Furthermore, I had decided to add to this project by using an IR receiver module. Laws have begun to take place that limit police chases. Also, heavy traffic often makes it difficult for emergency vehicles to reach people in need. To combat these issues, I decided to find a way to control and set the intersection lights to red at any time. Currently, intersections often have IR sensors that take in pulsating frequencies to determine if emergency vehicles are approaching, or they hold sound sensors, or networks use GPS tracking to allow for the traffic controller to communicate with vehicle locations. However, I decided to use a remote that sends signals to an IR receiver module.
  
https://github.com/user-attachments/assets/4f7a207f-c489-4b24-b5e6-5a1e746965b4

https://github.com/user-attachments/assets/bb890c34-431f-4a53-b80a-ccc8376cf144

<img width="400" height="305" alt="Screenshot 2026-06-27 012339" src="https://github.com/user-attachments/assets/41cc54f3-9b79-4210-aa05-cef265640ca1" />

