# BasicArduino

## Table of Contents
* [Hello Arduino](##Hello-Arduino)
* [Finite LED Blinker](##Finite-LED-Blinker) 
* [Variable LED Blinker](##Variable-LED-Blinker)
* [Button-Activated LED](##Button-Activated-LED)

## Hello Arduino

### Description

In this assignment we were supposed to make an LED turn on, and to write a code that said "Hello World". We then switched to making the LED blink, and changed the code to make it say "Blink". On the physical Arduino, we connected a wire from pin 13 to the breadboard, which the connected to a resistor. The resistor led to the positive end of the LED, and then electricity flowed through the LED into the negative end, which was connected back to GND with a wire.

### Evidence

```/* Hello Arduino
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
```

### Image

![Basic Arduino](/images/helloworld.png)

### Reflection

This was a very fun assignment! It was nice to be able to do some hands-on work instead of just using the computer. Unfortunately, not all of my supplies survived my first attempt with the breadboard, and my poor red LED met an untimely demise. On the bright side, I now know the consequences of connecting GND to the positive end of the LED. Another issue I had was that I didn't realize that you can push the wires into the breadboard. I was sitting at my desk for like 20 minutes just trying to balance all of the wires carefully on the very top of the breadboard and getting really frustrated when they kept falling. But, I eventually figured it out so it's all good now. I was surprised by how simple working with the breadboard was! Seeing all the numbers and letters made it seem pretty complicated, so it was a pleasant surprise when I found out that they don't really matter!

---

## Finite LED Blinker

### Description

In this assignment, we were supposed to make a LED blink on and off a set number of times, then turn off. We got to learn about variables and conditional statements! The wiring on the physical Arduino was the same as last time.

### Evidence

```
/* Evie Brantley 11/24/20
Code blinks an LED 5 times, then stops.
*/
int counter = 0;//the variables always go before the setup
void setup() {
  Serial.begin(9600);
  pinMode (13, OUTPUT);
}

void loop() {
  counter=counter+1;//This is how the variable adds one every loop! Could also be written as: x = x++
  if (counter >= 5) { //this code is used if the counter is greater than or equal to five
    Serial.println("Off");
    digitalWrite(13, LOW);//turns LED off
  }
  else {//since I only had two options, I use "if,else". If I had more I would use "if, else if, else"
    Serial.println("On");//
    digitalWrite(13, HIGH) ;//turns LED on
    delay(1000);//1 second delay
    digitalWrite(13, LOW);//turns LED off
    delay(1000);
     }
}

```

### Image

![Finite LED Blinker](/images/finiteLED.gif)

### Reflection

This assignment went smoothly for the most part! I was able to make the *if...then* code and variable without much trouble (thank you hour of code!), but then I was stumped by how to get the variable number to increase! I got some good practice with googling, and then when I couldn't find anything I went into office hours with Mr. Dierolf and he explained it. I needed to add *counter=counter+1* in the loop function for *else*, which, in retrospect, seems obvious. So, I know how to do that now!

---

## Variable LED Blinker

### Description

In this assignment, we were supposed to make a LED blink faster and faster by increments of 0.2 seconds. Once it reached 0.2 second blinks, it stopped decreasing.

### Evidence

```
/*
Evie Brantley 11/24/20
This code blinks an LED for intervals decreasing by .2 seconds, then once it reaches.2 seconds, 
stops decreasing and switches to a different LED.
*/
int ledPin = 8;
int delayVar = 2000;
void setup() {
  pinMode(ledPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  if (delayVar > 200) {//This causes the code to run only if delayVar is greater than 200.
    Serial.println(delayVar);//This prints the delay time.
    digitalWrite(ledPin, HIGH);
    delay(delayVar);
    digitalWrite(ledPin, LOW);
    delay(delayVar);
    delayVar = delayVar - 200; //This is what causes the decreasing delay time.
  }
  else {//This code blinks a light on and off for 0.2 seconds.
    Serial.println("I did it!");
    digitalWrite(7, HIGH);
    delay(delayVar);
    digitalWrite(7, HIGH);
    delay(delayVar);
  }

}

```

### Image

![Variable LED Blinker](/images/variableLED.gif)

### Reflection

This assignment was fun! I liked coding with less instruction. I got to practice using the variable function, which I had some trouble with on the last assignment. I think that it is definitely more solidified in my head now. I also liked that the assignment let me change it up a little bit. I added in a second LED which started to blink once the delay stopped decreasing, and changed the text from the delayVar to "I did it!".

---

## Button-Activated LED

### Description

In this assignment, we were using a button to control whether or not an LED blinked. On the Arduino, we wired up an LED as usual, then added a button. I picked a pin and wired it to the breadboard, on the same row as one of the button's prongs. The button streched across the ravine, and then I connected one prong to 5V and one to a resistor. 

### Evidence

```
int ledPin = 2;
int buttonPin = 12;
int buttonState = 0;
int button# = 0;

void setup() {
  pinMode(ledPin, OUTPUT);
  pinMode(buttonPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  buttonState = digitalRead(buttonPin);//this checks if the button is pressed or not
  if (buttonState == HIGH) {
    digitalWrite(ledPin, HIGH);
    delay(200);
    digitalWrite(ledPin, LOW);
    delay(200);
    Serial.println("Button ON");
  }
  else {
    digitalWrite(ledPin, LOW);
    Serial.println("Button OFF");

  }
}

```
### Image
 
![Button Activated LED](/images/baled.gif) 

### Reflection

This assignment was a little bit confusing for me. I understood most of the coding involved, but I have no idea what I was doing with the button! I get why pressing the button activates the LED, but why is there a resistor on one end? And why does it connect to both a 5V and a pin? Shouldn't it connect to ground? My best guess is that the resistor is serving as the GND somehow, or maybe since it isn't drawing power from the computer, it doesn't need to connect to a negative on the Arduino. When I was coding for this assignment, it wasn't that difficult, so I attempted the challenge of making the button toggle the LED on and off, but I was completely mystified! I think that I would have to make it count whenever the button was pressed, then somehow check if that number was odd or even and make an if...then statement about it. Maybe I will try again next week! It might be easier if I can ask Mr. Dierolf about it during class.

---

## Two Buttons Two LEDs

### Description

This assignment was the exact same thing as the last assignment, except with two buttons and two LEDs. The only difference in the wiring is that one of the buttons was connected to 3.3V instead of 5V because there is only one 5V on the Arduino, but it still worked fine.

### Evidence

```
/*
  Evie Brantley 12/07/20
  This code has two buttons which control two LEDs. When you pres one, it makes its corresponding
  LED blink on and off.

*/
int ledPinBlue = 4;
int ledPinGreen = 2;
/*my LED pins*/
int greenButtonPin = 12;
int blueButtonPin = 8;
/*my button pins*/
int blueButtonState = 0;
int greenButtonState = 0;
/*measures if button is pressed*/

void setup() {
  pinMode(ledPinBlue, OUTPUT);
  pinMode(ledPinGreen, OUTPUT);
  pinMode(greenButtonPin, OUTPUT);
  pinMode(blueButtonPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  blueButtonState = digitalRead(blueButtonPin);
  greenButtonState = digitalRead(greenButtonPin);
  if (blueButtonState == HIGH) { //if blue button is pushed
    digitalWrite(ledPinBlue, HIGH);
    delay(200);
    digitalWrite(ledPinBlue, LOW);
    delay(200);
  }
  if (greenButtonState == HIGH) { //if green button is pushed
    digitalWrite(ledPinGreen, HIGH);
    delay(200);
    digitalWrite(ledPinGreen, LOW);
    delay(200);
  }
}

```
### Image

![Two Buttons Two LEDs](/images/twobuttontwoled.gif) 

### Reflection

This assignment was really simple because it was just a doubling of the last assignment. I did find out that I was missing a wire, which was a minor setback, but once I picked it up from CHS, everything went pretty smoothly. I did have one problem with a button which was not activating its light. At first I thought it was because it was plugged into 3.3V, but I eventually figured out that the button base was not fully pushed in. Something I gained from this assignment was I figured out how to switch the top of the buttons so that I can color code them with my LEDs.
