# Digital Input

To use the pin to read a digital input, we can set the pin into ``INPUT`` or ``INPUT_PULLUP`` via ``pinMode``. While at ``INPUT`` mode, the pin will be at high impedence mode, meaning that it will retain whatever voltage it is at as much as possible and not conducting current. ``INPUT_PULLUP`` means it will activate its internal pull up resistor, and the pin itself will stay at 5V unless connecting to ground. Typically, we call this an active-low circuit, meaning the circuit is activated when pulled low. Arduino only supports internal pull down, manual implementation will be needed for an active-high (pull-down) circuit.

In most cases, you would want to use a ``INPUT_PULLUP`` mode instead of ``INPUT`` mode, that is because the nondeterministic behavior of ``INPUT``, or we often call the input is floating. Remember that I said the pin will try to retain whatever voltage it is at as much as possible? When the input pin is not connecting to anything, the pin will be *floating* and we will not know when the pin will read ``HIGH`` or ``LOW``.

An ``INPUT`` mode would be used for two cases, one is if the pin is connected to an external circuitry which contains its pull-up or pull-down resistor, in such cases ``INPUT_PULLUP`` will interference with the external circuitry and may cause issues. Another cases is that you are reading an analog voltage.

## Example

In this example, we are using pin 7 as an input by connecting it to a button, and connecting a LED to pin 8 as an output.

```C
void setup() {
  pinMode(7, INPUT_PULLUP);
  pinMode(8, OUTPUT);
}

void loop() {
  int reading = digitalRead(7);
  digitalWrite(8, reading);

}
```
