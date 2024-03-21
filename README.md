# Automatic Light Controller using LDR and Arduino UNO controller.

##  AIM:

To design and simulate automatic light controller using LDR and Arduino UNO controller in proteus.

## Software required:
Arduino IDE </br>
Proteous

## PROCEDURE:
### Arduino IDE
Step1:Open the Arduino IDE </br>
Step2: Go to file and select new file option </br>
Step3:Type the program </br>
Step4:Go to file and select save option to save the program </br>
Step5:Go to sketch and select verify or compile options </br>
Step6:If no error Hex file will be generated in the temporary folder </br>

### Proteus
Step7:Open the Proteus software </br>
Step8:Go to file select new design and click ok button </br>
Step9:Select component mode and click pick devices from the library </br>
Step10:Type the component name in the keyword to select the components and click ok button </br>
Step11:Design the circuit as per the diagram </br>
Step12:Double click the Arduino controller and upload the hex file generated by Arduino IDE </br>
Step13:Click start button and check the output

## THEORY:
Light sensor and street light control using Arduino is designed to measure the intensity of light or the amount of light.
It automatically controls street lights based on the light intensity detected. 
In this experiment, we utilize the Arduino UNO R3 for implementation. A light-dependent resistor is used for light detection. 
To provide isolation between the Arduino and the 220V AC street light, a relay is incorporated.

### Light dependent resistor (LDR)
Light Dependent Resistor (LDR) is used to detect changes in light intensity or as a light sensor. An LDR is essentially a variable resistor that changes its resistance with the intensity of light. When the light intensity is high, the LDR has low resistance, and when the light intensity decreases, the LDR offers high resistance. Therefore, there is an inverse relationship between the intensity of light and the resistance of the LDR
To measure the resistance of an LDR and calculate the intensity of light, we can use the Arduino UNO R3 board, which has six analog-to-digital converter channels. However, these channels can only measure voltage and cannot measure resistance directly. To overcome this, we use signal conditioning by connecting a 10K ohm resistor in series with the LDR and a 5-volt source. This circuit converts the resistance into voltage form, which can then be measured using the analog-to-digital converter of the Arduino. The measured voltage across the LDR can be converted back into resistance using the voltage division formula.

### Relay
In this experiment a relay is used to provide isolation between low-voltage circuitry and high-voltage circuitry. Arduino is also used to provide a control signal to the relay whenever the intensity of light falls below a certain level. The control signal is generated from pin 13 of Arduino, which is used as an output pin
### Light Sensor with Arduino
The circuit diagram shown in the image represents a light sensor and street light control system using Arduino. Let’s break down the components and their functions:
1.	Arduino UNO R3: The Arduino UNO R3 board serves as the main microcontroller in this project. It receives input from the light sensor and controls the street lights based on the detected light intensity.
2.	Light Dependent Resistor (LDR): The LDR is a sensor that detects changes in the intensity of light. It is connected in series with a 10K ohm resistor and a 5-volt power supply. The resistance of the LDR varies with the intensity of light falling upon it.
3.	Analog-to-Digital Converter (ADC): The Arduino UNO R3 board has six ADC channels that can measure voltage. In this project, the measured voltage across the LDR is converted into a corresponding resistance value using a voltage divider circuit. This resistance value is then converted into a digital value by the ADC for further processing.
4.	Relay: The relay is used to provide isolation between the low-voltage circuitry (Arduino) and the high-voltage circuitry (street lights). It acts as a switch that is controlled by the Arduino. When the light intensity falls below a certain level, the Arduino sends a control signal to the relay, which then switches on or off the street lights accordingly.

 ![image](https://github.com/anishkumar-Embedded/Automatic-Light-control-using-Arduino-Controller/assets/71547910/9cc7f0aa-0cfc-46a2-87ff-de5d31221c0a)


Overall, this circuit diagram showcases how the Arduino, LDR, ADC, relay, and transistor are interconnected to create a light sensor and street light control system. The Arduino reads the resistance value of the LDR, converts it into a digital value, and based on that, controls the street lights using the relay.








LDR Features of LDR are as follows: 

1. High reliability. 2. Light weight. 3. Wide spectral response. 4. Wide ambient temperature range.


## PROGRAM:
```
int sensorPin = A0; 
int sensorValue = 0; 
void setup() 
{
Serial.begin(9600); 
pinMode(13, OUTPUT);
}
void loop() 
{
  sensorValue = analogRead(sensorPin);
  Serial.print("OUTPUT:");
  Serial.println(sensorValue); 
  delay(500);
  if(sensorValue<=400)
  {
  digitalWrite(13, HIGH);  
  delay(500);
  }
  else
  {
  digitalWrite(13, LOW);  
  delay(500);
  }
}
```

## CIRCUIT DIAGRAM:
![image](https://github.com/Prasannalakshmiganesan/Automatic-Light-control-using-Arduino-Controller/assets/118610231/d78b1e55-3106-400c-a6aa-809c3d1eabe3)

## OUTPUT:
![image](https://github.com/Prasannalakshmiganesan/Automatic-Light-control-using-Arduino-Controller/assets/118610231/d9d0a12e-03d6-443f-b717-438040fee600)

## RESULT:
Thus the automatic light controller was designed and simulated using LDR and Arduino UNO controller.
