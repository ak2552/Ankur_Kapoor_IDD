### Paper Puppets
A lab report by Ankur

In this Report
To submit your lab, clone this repository. You'll need to describe your design, include a video of your paper display in operation, and upload any code you wrote to make it move.

## Part A. Actuating DC motors
Video of my Vibration motor: 

## Part B. Actuating Servo motors
# Part 1. Connect the Servo to your breadboard
a. Which color wires correspond to power, ground and signal?
Brown Wire = Ground
Red Wire = Power
Orange Wire = Signal

# Part 2. Connect the Servo to your Arduino

a. Which Arduino pin should the signal line of the servo be attached to?

Digital Pin 9

b. What aspects of the Servo code control angle or speed?

The for loops inside the main loop function is used to change the value of the pos variable. The pos variable is used to tell the servo to whitch position to move. This line of code tells the servo motor to move to the position stored in pos myservo.write(pos); . The delay controls the time between the servo moving thus delaying the movement between positions that is controlled in this line delay(15); . The delay also gives the servo time to do the move you have instructed it so even for maximum speed a delay is necesarry and there will need to be experimented to find the minimum value for delay but delay can be incresed to slow down the movement as the motor will move at the same speed but will wait longer between moving.

Part C. Integrating input and output
Video of my Servo Motor in action:  
Part D. Paper puppet
Video of my Paper puppet:  

Part E. Make it your own
a. Make a video of your final design.

 
Video of my Paper puppet that I made my own:  
