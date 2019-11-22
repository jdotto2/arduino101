# Programming interface

Arduino uses C and C++ programming language, the compilers are board specific and supports a variety of features. Begin with a new sketch, you will see the workspace as shown below

![workspace](https://github.com/unl-robotic/arduino101/blob/master/images/arduino005.PNG "figure1")

At first glance, you will find `void setup()` and `void loop()`. In a nutshell, you will write whatever code to be run once inside `void setup()` and repeating code inside `void loop()`. To whoever familiar with C/C++, you will realize Arduino does not have the default `int main()` function, but you actually can write it in the standard style with `int main()`

# Pinout
![pinout](https://github.com/unl-robotic/arduino101/blob/master/images/arduino006.PNG "figure2" )

By looking the pins layout of Arduino UNO, starting from left, we first has the block of power pins, which you can draw 5V, 3.3V or ground (0V) for your circuitry. Analog inputs for reading analog voltage, pin 0 and 1 are serial transmit and receive pin for serial communication, pin 3 to 13 are general purpose digital I/O, and I2C bus pin at the end. We also have reset button so you can reinitialize your Arduino to restart its sequence.
