# Analog Input
UNO has 6 analog input pins, `A0`, `A1`, `A2`, `A3`, `A4`, `A5`. we use `analogRead` to read in voltage level on the given pin. The function `analogRead` takes in the pin number and then return readings. However, it does not return the actual voltage reading. In reality, microcontroller has these components called Analog-to-Digital Convertor or ADC. It partitions the reference voltage (5 volts on UNO and MEGA) into 1024 levels because of its 10-bit ADC, which has 2^10 possible levels. For example, a 5 volt input will return `1023` and 2.5 volt will return `511`. We call this ADC having a 10-bit resolution. 

## Reading Potentiometer
<img src="http://www.toptechboy.com/wp-content/uploads/2014/07/arduino-schematic_bb-1024x787.jpg" height="400" />
In this example, we will use a rotary potentiometer to adjust LED brightness. A potentiometer is a variable voltage divider, essentially it uses the resistance ratio to divide an incoming voltage. Rotary potentiometer has a knob that when you turns the knob, it varies the resistance linearly. We will apply 5 volt and ground across the potentiometer and probe the middle pin to our analog input.
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/31/Impedance_voltage_divider.svg/1200px-Impedance_voltage_divider.svg.png" height="200" />


```C
void setup(){
    pinMode(10, OUTPUT);
}

int reading;
void loop(){
    reading = analogRead(A0);
    analogWrite(10, reading/4);
    delay(15);
}
```
In this example, we read in the analog input, which comes in the range of `0-1023`, and write to analog output, which has a range of `0-255`, so we divide it by 4 to fit the mapping. Notice that we do not need to set pin mode, all the pins are implicitly in high-impedence mode or input mode. However, if you used the same pin for an output, you will need to set it to output mode manually using ``pinMode``. 
