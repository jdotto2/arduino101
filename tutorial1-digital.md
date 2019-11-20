# Programming interface

Arduino uses C and C++ programming language, the compilers are board specific and supports a variety of features. Begin with a new sketch, you will see the workspace as shown below

![workspace](https://github.com/unl-robotic/arduino101/blob/master/images/arduino005.PNG "figure1")

At first glance, you will find `void setup()`{:.language-c} and `void loop()`. In a nutshell, you will write whatever code to be run once inside `void setup()` and repeating code inside `void loop()`. To whoever familiar with C/C++, you will realize Arduino does not have the default `int main()` function, but you actually can write it in the standard style with `int main()`
