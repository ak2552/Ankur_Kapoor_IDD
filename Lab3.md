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
