 
 # Lab2: Digital Timer
## Part A. Solder your LCD panel
![Soldered](https://github.com/ak2552/Ankur_Kapoor_IDD/blob/master/IMG_2067.JPG)

## Part B. Writing to the LCD

### a. What voltage level do you need to power your display?

 + 5V 

### b. What voltage level do you need to power the display backlight?

The backlight is powered by +3.3V for this lab.
It is possible to use +5V to power the LCD 
 

### c. What was one mistake you made when wiring up the display? How did you fix it?

I made No mistakes  

### d. What line of code do you need to change to make it flash your name instead of "Hello World"?

 Below is the line of the code required. 

lcd.print("Hello World"); to lcd.print("Ankur Kapoor");

### e. Include a copy of your Lowly Multimeter code in your lab write-up.

[Code](https://github.com/ak2552/Ankur_Kapoor_IDD/blob/master/multimeter_code.io)

## Part C. Using a time-based digital sensor

[Rotatory Video](https://www.youtube.com/watch?v=kz87V_5-MDw)

## Part D. Make your Arduino sing!
### a. How would you change the code to make the song play twice as fast?

+ Simply change noteDuration to less than a 1000, e.g. noteDuration = 500

+ Can also change the pauseBetweenNotes to half the value to make it play twice as fast

### b. What song is playing?
   
   Star Wars theme
