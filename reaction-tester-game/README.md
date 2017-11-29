# LED matrix controller
*Create a reaction tester with STM32 board*

## Objectives
- Practice STM32 GPIO, systick, RNG usage

## Materials & Resources

| Material | Duration |
|:---------|---------:|
|[STM32 random number generator](https://st-onlinetraining.s3.amazonaws.com/STM32F7-Security_Random_Number_Generator/index.html)| 3:23 |
|[Systick timer](http://www.micromouseonline.com/2016/02/02/systick-configuration-made-easy-on-the-stm32/)| - |

## Material review
- RNG on STM32F7
- Systick, how to measure time

## Workshop
You need to the project:
- A working serial port terminal(for example Hercules)
- A random number between 1-10.
- A time trustworthy measured.
- A push button.
- A led.

## The flow of the game:
- The board says via Uart: "Let's play a game! Are you ready?" Flash the led in this stage, with 1 Hz frequency.
- If the user push the button, !!!immediately!!! start the game with turning the led off.
- Delay a random time between 1-10s timeframe. Use the random generator of the board to make this time.
- After the random time elapsed, turn on the led, and start measure the reaction time.
- You need to measure the time that is elapsed between the led turned on and the button pressed. Use the Systick for this.
- Print out the result for the user, and stars the game again.

## RNG
There is a random number generator in the MCU, which you find in the [reference manual](http://www.st.com/content/ccc/resource/technical/document/reference_manual/c5/cf/ef/52/c0/f1/4b/fa/DM00124865.pdf/files/DM00124865.pdf/jcr:content/translations/en.DM00124865.pdf), begin with 539 page. Read this chapter briefly for general understanding this unit, and it's registers.
There is only a few of them which you need to be write, so do in this way or look after in the HAL. Pro tip: Google is not that much help in this instance, but the cubeF7 examples...

## Cortex System Timer (SysTick)
Timer is a topic that will come up next week but the very basic is: This thing is increasing a 32bit register every 1ms exactly, so if you can read this register, you are done with the trustworthy measure the time problem. 
In this case the reference manual is not a big help, the google is good but the easiest way the HAL: Look inside the HAL_Delay(). Here you can figure out why this function blocks the program running, how you can access to the needed data register, and also can do delays without blocking the program running.


## Extra:
Measure how fast you are in a different way, how fast you can push the button?
Measure and average the time between the last 10 button pushes, and print out(continuously) the frequency you reached.
