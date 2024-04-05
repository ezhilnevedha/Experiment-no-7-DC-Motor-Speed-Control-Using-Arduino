###  DATE: 05-04-2024
###  NAME: EZHIL NEVEDHA.K
###  ROLL NO :212223230055
###  DEPARTMENT:AI &DS

# Experiment-no-6-DC-Motor-Speed-Control-Using-Arduino

### AIM : To control the speed and the direction of a DC motor using L293D driver ic( H- bridge)

### Components Required:
•	Arduino UNO board
•	L293D driver
•	12V DC motor
•	10K ohm potentiometer
•	Pushbutton
•	12V source
•	Breadboard
•	Jumper wires
### THEORY 
The L293D quadruple half-H drivers chip allows us to drive 2 motors in both directions, with two PWM outputs from the Arduino we can easily control the speed as well as the direction of rotation of one DC motor. (PWM: Pulse Width Modulation).
Arduino DC motor control circuit:
Project circuit schematic diagram is the one below.

![image](https://user-images.githubusercontent.com/36288975/167763051-b230c183-afc5-46f2-ba95-0f95e10dd6c9.png)
FIGURE-01 H BRIDGE CIRUCIT INTERFACE 
 
The speed of the DC motor (both directions) is controlled with the 10k potentiometer which is connected to analog channel 0 (A0) and the direction of rotation is controlled with the push button which is connected to pin 8 of the Arduino UNO board. If the button is pressed the motor will change its direction directly.
The L293D driver has 2 VCCs: VCC1 is +5V and VCC2 is +12V (same as motor nominal voltage). Pins IN1 and IN2 are the control pins where:
![image](https://user-images.githubusercontent.com/36288975/167763120-1421c2c5-8381-49eb-b376-03f6e1113b7a.png)
TABLE-01 EXITATION TABLE FOR H BRIDGE 

As shown in the circuit diagram we need only 3 Arduino terminal pins, pin 8 is for the push button which toggles the motor direction of rotation. Pins 9 and 10 are PWM signal outputs, at any time there is only 1 active PWM, this allows us to control the direction as well as the speed by varying the duty cycle of the PWM signal. The active PWM pin decides the motor direction of rotation (one at a time, the other output is logic 0).

### PROGRAM :
```
int input1=5;
int input2=6;
int en=3;
void setup()
{
  pinMode(input1, OUTPUT);
  pinMode(input2,OUTPUT);
  pinMode(en,OUTPUT);
}

void loop()
{
  analogWrite(en,220);
  
   digitalWrite(input1, LOW);
   digitalWrite(input2, HIGH);
  delay(500);
}
```

### OUTPUT:
![image](https://github.com/ezhilnevedha/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/140057992/ac2d2e93-35a4-48d0-9d70-a61da25aca64)

![image](https://github.com/ezhilnevedha/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/140057992/dffc9fe4-600c-4792-a3ac-700735b1509e)

### GRAPH AND TABULATION 
![image](https://github.com/ezhilnevedha/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/140057992/95ceb561-12db-4b30-8a14-6f7049fffb1e)

![image](https://github.com/ezhilnevedha/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/140057992/d48c4f3d-dfa3-4b46-ad75-cc14e574da49)



### RESULTS AND DISCUSSION :
Thus , the speed and direction of DC motor has been controlled by L293D driver.

