# BasicArduino

## Table of Contents
* [Hello Arduino](#Hello_Arduino)

## Hello Arduino

### Description

In this assignment we were supposed to make an LED turn on, and to write a code that said "Hello World". We then switched to making the LED blink, and changed the code to make it say "Blink". On the physical Arduino, we connected a wire from pin 13 to the breadboard, which the connected to a resistor. The resistor led to the positive end of the LED, and then electricity flowed through the LED into the negative end, which was connected back to GND with a wire.

### Evidence

/* Hello Arduino
Evie Brantley-11/16
It blinks a light on and off! REMEMBER: The long end of the LED is the positive end!!
Don't let blue and green LEDs burn like poor red LED!! :( Connect GND (ground(negative)) to the breadboard,
then connect NEGATIVE(SHORT) end of led in same row, then put in positive in another row. In the + row,
add a resistor, then put the other end of resistor in another row, which you then connect with a wire to the pin you coded!
(In this case, pin 13)*/

void setup() {
  Serial.begin(9600);
  pinMode(13,OUTPUT); //makes pin 13 ready for output
}

void loop() {
 Serial.println("Blink"); 
 digitalWrite(13,HIGH); //controls amount of light
 delay(100);
 digitalWrite(13,LOW);
 delay(250);//this makes it blink off for half a second- a full second is considered 1000
}


### Image

### Reflection



