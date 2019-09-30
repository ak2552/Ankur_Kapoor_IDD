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

Yes, the clear state needs to be on one of the sides with the reading and writing states next to each other. If the clear state was in the middle it would be impossible to read a value from EEPROM after storing it considering that it would be cleared first if you tried going from the write to rad state.

### b. Why is the code here all in the setup() functions and not in the loop() functions?

Because whenever we change the state, we only want the state’s main code to execute once and not repeatedly while the device remains in that state. For example, when entering the reading state, we only want to read the data stored once the same with the write state we only want to save once when we enter the state.

### c. How many byte-sized data samples can you store on the Atmega328?

The Atmega328P has 1024 bytes of EEPROM memory and thus you will be able to save up to 1024 byte-sized data samples on it.

### d. How would you get analog data from the Arduino analog pins to be byte-sized? How about analog data from the I2C devices?

For analog pins we get 10-bit data that needs to be converted to 8-bit data so that it can be saved in the EEPROM. We can accomplish this by mapping the 10-bit value 0-1023 to an 8-bit value 0-255. The new 8-bit value might not be precisely as accurate as the 10-bit value as some information is lost but it is the best possible way. The 8-bit value can later be recovered from memory and inflated to a number between 0-1023 again and will be within a few numbers of the correct original number. The other way is break up the 10-bit number and save it as 4, 8-bit values that can be summed together to create the original 10-bit number.

For I2C we do not have the format of the data we will receive. Because of the varying possible formats of data, we will receive each case will have to be evaluated individually. Then it will have to be decided if the received data can be saved as is or need to be converted to 8-bit data using the map function or if the received value will have to be stored across multiple 8-bit values.

### e. Alternately, how would we store the data if it were bigger than a byte? (hint: take a look at the EEPROMPut example)

By breaking the data up into byte sized data. For example, an int could be 2 or 4 bytes with long int being 8 bytes. Since we know this it is possible to break up an int into 2 or 4 bytes these can then be accurately stored in the EEPROM in 2 or 4 memory addresses.

Upload your modified code that takes in analog values from your sensors and prints them back out to the Arduino Serial Monitor.
