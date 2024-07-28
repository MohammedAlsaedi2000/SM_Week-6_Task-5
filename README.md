# Controlling motors' direction using H-Bridge

## Description
Some simple robots have two wheels used for moving around.
In this project I designed or simulated two motors and H-Bridge (Motor Driver) to control the direction of the motors. Controlling the direction is important becuae the robot can move in every direction, for example:
two motors together rotate in the clockwise direction, the resultant moving direction will be FORWARD and vice versa.

If one motor rotates Clockwise and the second motor rotates in the Counter Clockwise direction, the resultant moving direction will be either right or left depending on your perspective.


## Circuit Diagram

In the following figure you can see that there are four Push Buttons for different directions

![motor](https://github.com/user-attachments/assets/65c6aaa3-470f-4b9e-8a66-fb3a30b7280f)


## TinkerCAD Project Link

https://www.tinkercad.com/things/f424zjp1I6M-motor-automatic-direction


## Arduino Code



int left_motorCCW = 9;
int left_motorCW = 10;

int right_motorCCW = 11;
int right_motorCW = 12;


int Button1 = 3;
int Button2 = 4;
int Button3 = 5;
int Button4 = 6;

void setup() {

  pinMode(left_motorCCW, OUTPUT);
  pinMode(left_motorCW, OUTPUT);
  pinMode(right_motorCCW, OUTPUT);
  pinMode(right_motorCW, OUTPUT);  
  
  pinMode(Button1, INPUT);
  pinMode(Button2, INPUT);
  pinMode(Button3, INPUT);
  pinMode(Button4, INPUT);
  

}

void loop() {

  int Backward = digitalRead(Button1);
  int Forward = digitalRead(Button2);
  int Left = digitalRead(Button3);
  int Right = digitalRead(Button4);  

  if (Backward == HIGH) {
    digitalWrite(left_motorCCW, LOW);
    digitalWrite(left_motorCW, LOW);
    digitalWrite(right_motorCCW, LOW);
    digitalWrite(right_motorCW, LOW);
  }
  else if (Backward == LOW) {
    digitalWrite(left_motorCCW, HIGH);
    digitalWrite(left_motorCW, LOW);
    digitalWrite(right_motorCCW, HIGH);
    digitalWrite(right_motorCW, LOW);   
  }

    if (Forward == HIGH) {
    digitalWrite(left_motorCCW, LOW);
    digitalWrite(left_motorCW, LOW);
    digitalWrite(right_motorCCW, LOW);
    digitalWrite(right_motorCW, LOW);
  }
  else if (Forward == LOW) {
    digitalWrite(left_motorCCW, LOW);
    digitalWrite(left_motorCW, HIGH);
    digitalWrite(right_motorCCW, LOW);
    digitalWrite(right_motorCW, HIGH);   
  }
  

      if (Right == HIGH) {
    digitalWrite(left_motorCCW, LOW);
    digitalWrite(left_motorCW, LOW);
    digitalWrite(right_motorCCW, LOW);
    digitalWrite(right_motorCW, LOW);
  }
  else if (Right == LOW) {
    digitalWrite(left_motorCCW, LOW);
    digitalWrite(left_motorCW, HIGH);
    digitalWrite(right_motorCCW, HIGH);
    digitalWrite(right_motorCW, LOW);   
  }

  


      if (Left == HIGH) {
    digitalWrite(left_motorCCW, LOW);
    digitalWrite(left_motorCW, LOW);
    digitalWrite(right_motorCCW, LOW);
    digitalWrite(right_motorCW, LOW);
  }
  else if (Left == LOW) {
    digitalWrite(left_motorCCW, HIGH);
    digitalWrite(left_motorCW, LOW);
    digitalWrite(right_motorCCW, LOW);
    digitalWrite(right_motorCW, HIGH);   
  }


    
}
