# GPIO Practice

## Objectives

*Get familiar using GPIO inputs and output on STM32F7*

### Workshop

#### 1. Bicycle Light

Connect at least 5 LEDs to your board (if it's more it's better)!
##### Basic usage

- First create a simple program which can light up all the LEDs (for example create a function for it).
- Then turn off the LEDs (again it is a good practice to do it in a function).
- When you have finished with these, it time to use a button:
  - If you press the button, the LEDs should light up!
  - If you press the button again, the light goes out!
  - You should loop it! So if the button is pressed again the LEDs light up...

##### Advanced usage

- Create an other function which can flash the lights. This function should be between the LEDs-ON and the LEDs-OFF status.
- Call this function multiple times, the only difference is the time between two flashes.
- These function should fill the gap between the ON and OFF status, and the program should still be looped!

#### 2. Chase Light

Use the connected LEDs form the previous exercise (again, if it's more it's better)!

##### a. Without Button
*You should implement the following functions one by one (there is no definition about how to change between them).*
- Create a one directional chase light!
  - The speed of the light should be alterable.
- Create a two directional chase light!
  - The speed of the light should be alterable.


##### b. With Button
- Use the functions from above. Create a simple program where you use a button to change between one directional and two directional chase light. *This time the speed of the light is constant.*
- Use the functions from above. Create a simple program where you use a button to increase the speed of the light. Find a solution to lower it! *This time we are using our button, so there is no option to change between one and two directional chase light.*

#### 3. Binary counter
[Createa a binry counter just like this](https://www.youtube.com/watch?v=UzZNyhspXmo) which can count up to 255.

## Individual Workshop Review
Please follow the styleguide: [Our C++ styleguide](../../styleguide/cpp.md)

 - Is the directory structure and the name of the files correct?
 - Are the includes placed on the top of the files?
 - Is the indentation good in each file?
 - Is there unnecessary code?
 - Can you find unnecessary code in comments?
 - Is there unnecessary code duplication?
 - Are there unnecessary empty blocks?
 - Can you spot unused variables?
 - Is the commit message meaningful?
 - Are the allocated resources deleted when necessary?
 - Is there any potential memory leak?
