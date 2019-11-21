# Programming interface

Arduino uses C and C++ programming language, the compilers are board specific and supports a variety of features. Begin with a new sketch, you will see the workspace as shown below

![workspace](https://github.com/unl-robotic/arduino101/blob/master/images/arduino005.PNG "figure1")

At first glance, you will find `void setup()` and `void loop()`. In a nutshell, you will write whatever code to be run once inside `void setup()` and repeating code inside `void loop()`. To whoever familiar with C/C++, you will realize Arduino does not have the default `int main()` function, but you actually can write it in the standard style with `int main()`

# Pinout
![pinout](https://github.com/unl-robotic/arduino101/blob/master/images/arduino006.PNG "figure2" )

By looking the pins layout of Arduino UNO, starting from left, we first has the block of power pins, which you can draw 5V, 3.3V or ground (0V) for your circuitry. Analog inputs for reading analog voltage, pin 0 and 1 are serial transmit and receive pin for serial communication, pin 3 to 13 are general purpose digital I/O, and I2C bus pin at the end. We also have reset button so you can reinitialize your Arduino to restart its sequence.

# Digital I/O
Pin 3 to 13 on UNO are digital I/O, they can be set as either input or output mode. To do that, write `pinMode(PIN_NUMBER, MODE)` in `setup()` function block. 

In this example, we will use the on board LED which is internally connect to pin 13. You can check at the small LED next to pin 13.
```C
void setup(){
    pinMode(13, OUTPUT);
}

void loop(){
    digitalWrite(13, HIGH);
    delay(100);
    digitalWrite(13, LOW);
    delay(100);
}
```
Here we set pin 13 to output mode, which it can write to be `HIGH` (5 volt) or `LOW` (0 volt) by using `digitalWrite(PIN_NUMBER, STATE)`. The `delay()` function will pause the system to the given number of miliseconds. In this example, the LED will stay on for 100 ms and OFF for another 100 ms repeatedly.

The on board LED is a good way to troubleshoot your microcontroller if it is still working. 

## Connecting with External LED
LED is acronym for Light-Emitting-Diode, useful for low power and efficiency light source in small project. It is also a diode such that it has a anode and cathode, meaning it only light up in the correct polarity. The advantage of being a diode is that, while placed with reverse-polarity, you actually will not damage the LED , given the voltage is below its breakdown voltage. Because a diode behave like a insulator in the reverse bias mode.
![](https://cdn.sparkfun.com/assets/c/5/7/2/7/51f1c87ace395fea20000004.png)
It is important to add a so-call current limiting resistor to ensure the LED does not draw infinite amount of current. A common resistance is 330 Ohms. Sparkfun has a really [good tutorial](https://learn.sparkfun.com/tutorials/light-emitting-diodes-leds/all) for LED, check it out if you want to learn more.

## Breadboard
Breadboard is a very common tool for prototyping electronics and circuitries, you can just plug in your components with wires to complete and test out your circuits without needing to solder. Note how the breadboard are internally connected, the long edge has the power rails, usually for power and ground lines, and then at the middle the rails are running in perpendicular direction. Sparkfun has a [detail tutorial](https://learn.sparkfun.com/tutorials/how-to-use-a-breadboard/all) for breadboard, check it out if you are interested.
![](http://wiring.org.co/learning/tutorials/breadboard/imgs/breadboard-03.jpg)

To wire your external LED, follow the circuit below. Just connect the digital output pin in series with LED, resistor, and goes back to ground pin of your Arduino.
![](https://cdn.instructables.com/F60/IZJJ/I8ZQZMO9/F60IZJJI8ZQZMO9.LARGE.jpg?auto=webp&&frame=1&fit=bounds) 
