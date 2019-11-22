# Analog Input
UNO has 6 analog input pins, `A0`, `A1`, `A2`, `A3`, `A4`, `A5`. we use `analogRead` to read in voltage level on the given pin. The function `analogRead` takes in the pin number and then return readings. However, it does not return the voltage reading. In actual, microcontroller has these components called Analog-to-Digital Counvertor or ADC. It partitions the reference voltage (5 volts on UNO and MEGA) into 1024 levels because of its 10-bit ADC, which has 2^10 possible levels. For example, a 5 volt input will return `1023` and 2.5 volt will return `511`. We also call this ADC having 10-bit resolution. 

## Reading Potentiometer
<img src="http://www.toptechboy.com/wp-content/uploads/2014/07/arduino-schematic_bb-1024x787.jpg" width="200" height="400" />
In this example, we will use a potentiometer to generate a variable voltage. A potentiometer is a variable voltage divider, essentially it uses the resistance ratio to divide an incoming voltage into a two parts.
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/31/Impedance_voltage_divider.svg/1200px-Impedance_voltage_divider.svg.png" width="200" height="400" />
