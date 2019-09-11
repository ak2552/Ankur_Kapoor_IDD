 

# Part A. Set Up a Breadboard
 ![69840349_2362419283980619_34543116291670016_n](https://user-images.githubusercontent.com/54294244/64662594-fff31300-d416-11e9-9e3c-8e93ccfc8e6a.jpg)

# Part B. Manually Blink a LED
## a. What color stripes are on a 100 Ohm resistor?

1st Band: - Brown = 1 

2nd Band: - Black = 0 

3rd Band: - Brown = 10 (Multiplier)

4th Band Tolerance can be Gold/Silver/Nothing. 

## b. What do you have to do to light your LED?
We need to build the circuit as shown in the part A. Below are the steps: - 

•	Connect Push Button to 5V and to positive leg of the LED. 

•	Connect resistor to the negative leg of the LED  

•	Connect the negative rail of the bread board to the other leg of the resistor

•	Connect the positive rail of the bread board to the 5V pin of the Arduino. 

•	Connect the negative rail of the bread board to the ground pin of the board. 

•	Supply power to the board through USB.

•	Push the button the LED will be lit. 

# Part.C Blink LED with Arduino

## C.(a) What line(s) of code do you need to change to make the LED blink (like, at all)?
 
No change to the code is needed as the code used in example already detects and configured to the correct pin. 

## C.(b) What line(s) of code do you need to change to change the rate of blinking?
 
Change the values in the Delay() functions. The delay() function tells the device to wait for the value given in miliseconds. In the example, top delay function tells how long the LED stays on for in milliseconds and the bottom one specifies how long it is off for.

## C.(c) What circuit element would you want to add to protect the board and external LED?
 
Put a resistor in the circuit to protect the board and LED against the current surge.

## C.(d) Change the delay parameter to modify blink rate of your LED to make it blink faster. At what delay can you no longer perceive the LED blinking? (And how can you prove to yourself that it is, in fact, still blinking?

The LED is blinking at 20 ms but when it goes below 14-15ms it is no longer visible with the naked eye.

If we open phone camera and look at the LED thru it, we can clearly see it blinking still.

## C.(e) Modify the code to make your LED blink your way. Save your new blink code to your lab 1 repository, with a link on the README.md

void setup() {
  // initialize digital pin LED_BUILTIN as an output.
  pinMode(LED_BUILTIN, OUTPUT);
}


// the loop function runs over and over again forever
void loop() {
  digitalWrite(LED_BUILTIN, HIGH);   // turn the LED on (HIGH is the voltage level)
  delay(200);                       // wait for a second
  digitalWrite(LED_BUILTIN, LOW);    // turn the LED off by making the voltage LOW
  delay(200);                       // wait for a second
  digitalWrite(LED_BUILTIN, HIGH);   // turn the LED on (HIGH is the voltage level)
  delay(200);                       // wait for a second
  digitalWrite(LED_BUILTIN, LOW);    // turn the LED off by making the voltage LOW
  delay(200);                       // wait for a second
  digitalWrite(LED_BUILTIN, HIGH);   // turn the LED on (HIGH is the voltage level)
  delay(200);                       // wait for a second
  digitalWrite(LED_BUILTIN, LOW);    // turn the LED off by making the voltage LOW
  delay(200);                        // wait for a second
  digitalWrite(LED_BUILTIN, HIGH);   // turn the LED on (HIGH is the voltage level)
  delay(2000);                       // wait for a second
  digitalWrite(LED_BUILTIN, LOW);    // turn the LED off by making the voltage LOW
  delay(2000);                       // wait for a second
  digitalWrite(LED_BUILTIN, HIGH);   // turn the LED on (HIGH is the voltage level)
  delay(2000);                       // wait for a second
  digitalWrite(LED_BUILTIN, LOW);    // turn the LED off by making the voltage LOW
  delay(2000);                       // wait for a second
}


 # 2. Blink your LED
2.(a) Now modify the circuit and program so that you can blink an external LED on pin 9

Video
https://youtu.be/bbRhafcXYfM

# D. Manually Fade an LED
## D.1 Are you able to get the LED to glow the whole turning range of the potentiometer? Why or why not?

Yes. Because there is still some current (though small) in the circuit enough to make the LED give off a faint light.


# Part E. Fade an LED using Arduino

## a. What do you have to modify to make the code control the circuit you've built on your breadboard?

Changing the LED pin from 9 to 11

## b. What is analogWrite()? How is that different than digitalWrite()?

•	analogwrite() allows to fade the light across different brightness levels.  

•	digitalWrite() pin writes either High or Low to an output pin which is basically either 5V or GND. So the digitalwrite can be used to turn on and of an LED  


 
