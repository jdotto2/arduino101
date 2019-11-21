# Programming interface

Arduino uses C and C++ programming language, the compilers are board specific and supports a variety of features. Begin with a new sketch, you will see the workspace as shown below

![workspace](https://github.com/unl-robotic/arduino101/blob/master/images/arduino005.PNG | width=100 "figure1" )

At first glance, you will find `void setup()` and `void loop()`. In a nutshell, you will write whatever code to be run once inside `void setup()` and repeating code inside `void loop()`. To whoever familiar with C/C++, you will realize Arduino does not have the default `int main()` function, but you actually can write it in the standard style with `int main()`

# Pinout
![pinout](https://github.com/unl-robotic/arduino101/blob/master/images/arduino006.PNG "figure2" )

By looking the pins layout of Arduino UNO, starting from left, we first has the block of power pins, which you can draw 5V, 3.3V or ground (0V) for your circuitry. Analog inputs for reading analog voltage, pin 0 and 1 are serial transmit and receive pin for serial communication, pin 3 to 13 are general purpose digital I/O, and I2C bus pin at the end. We also have reset button so you can reinitialize your Arduino to restart its sequence.

# Digital I/O
Pin 3 to 13 on UNO are digital I/O, they can be set as either input or output mode. To do that, write `pinMode(PIN_NUMBER, MODE)` in `setup()` function block. 

In this example, we will use the on board LED which is internally connect to pin 13.
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
Here we set pin 13 to output mode, which it can write to be `HIGH` (5V) or `LOW` (0V) by using `digitalWrite(PIN_NUMBER, STATE)`. The `delay()` function will pause the system to the given number of miliseconds. In this example, the LED will stay on for 100 ms and OFF for another 100 ms repeatedly.
