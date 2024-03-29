 # Data Logger (and using cool sensors!)
 
 A lab report by Ankur Kapoor.
 
## Part A. Writing to the Serial Monitor
### a. Based on the readings from the serial monitor, what is the range of the analog values being read?

 The range of the analog values is 0 - 1023.

### b. How many bits of resolution does the analog to digital converter (ADC) on the Arduino have?

10 Bits 


## Part B. RGB LED

Using the FSR to control the color of the RGB LED depending on how hard you press the FSR

[RGB LED Video 1](https://www.youtube.com/watch?v=RVE8Z4Zoz2w) 

 

## Part C. Voltage Varying Sensors
### 1. FSR, Flex Sensor, Photo cell, Softpot
### a. What voltage values do you see from your force sensor?

Values between 0 (Not touched) - 990 (when max pressure is applied) 


### b. What kind of relationship does the voltage have as a function of the force applied? (e.g., linear?)

It appears logarithmic such that the higher voltage values are more difficult to increment, whereas it is much easier to increase the voltage values at lower pressures

### c. Can you change the LED fading code values so that you get the full range of output voltages from the LED when using your FSR?
Yes, the LED fading code values can be changed to get the full range of output voltage from the LED when using FSR. This can be done using map function. 

 x = analogRead(A0); 

 y = map(x,0,1023,0,255); 

setColor(y,0,0);

### d. What resistance do you need to have in series to get a reasonable range of voltages from each sensor?

 photo cell: 10k 
 
 softspot: 10k

### e. What kind of relationship does the resistance have as a function of stimulus? (e.g., linear?)
For the Flex sensor it is linear relationship

For softpot it is linear relationship

For photocell it is a Logarithmic relationship.

### 2. Accelerometer
### a. Include your accelerometer read-out code in your write-up.

[Code](https://github.com/ak2552/Ankur_Kapoor_IDD/blob/master/accelerometer.ino)

# Graphic Display

Take a picture of your screen working insert it here!

Reading A0 value

[Code](https://github.com/ak2552/Ankur_Kapoor_IDD/blob/master/graphic_lab3.ino)

![Soldered](https://github.com/ak2552/Ankur_Kapoor_IDD/blob/master/IMG_2162.JPG)

## Part D. Logging values to the EEPROM and reading them back


## 1. Reading and writing values to the Arduino EEPROM
### a. Does it matter what actions are assigned to which state? Why?

Yes, the order matters in this case. For example in Write->Clear->Read state as clear state is in the middle then it won't be possible to read after we have written since we have a clear function in the middle. 

### b. Why is the code here all in the setup() functions and not in the loop() functions?

The code in setup() function occurs only once whereas in the loop() function the code executes more than once. Therefore if Read/write/clear process is in loop() function than the loop will start the Read/write/clear process again and again without finishing. 

### c. How many byte-sized data samples can you store on the Atmega328?

  1024 byte-sized data samples on  Atmega328

### d. How would you get analog data from the Arduino analog pins to be byte-sized? How about analog data from the I2C devices?

An analog reading is between 0-1023 but a byte sized data is in the range of 0-255. For this conversion we will use map() function. 

For I2C devices, we will need to find out the variation of range for reading values and then convert to 0-255 using map function. 

### e. Alternately, how would we store the data if it were bigger than a byte? (hint: take a look at the EEPROMPut example)

 We can make use of  EEPROM.put() function. This function allows to write data of primitive types. If the data is bigger this will store in consecutive addresses.
 
 
### Upload your modified code that takes in analog values from your sensors and prints them back out to the Arduino Serial Monitor.

```ruby

#include <EEPROM.h>

 

int FSRPin = 0;    // select the input pin for the potentiometer
 

void setup() {
  // initialize serial communication:
  Serial.begin(9600);  
 
}

void loop() {
 

  Serial.println(analogRead(FSRPin));
  delay(100);
 
}

```

## 2. Design your logger
### a. Insert here a copy of your final state diagram.

![Diagram](https://github.com/ak2552/Ankur_Kapoor_IDD/blob/master/IMG_2531.JPG)



## 3. Create your data logger!
### a. Record and upload a short demo video of your logger in action.

[Video](https://www.youtube.com/watch?v=S2lkwY-jIOI)

