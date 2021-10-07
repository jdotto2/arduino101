# Digital Input

To use the pin to read a digital input, we can set the pin into ``INPUT`` or ``INPUT_PULLUP`` via ``pinMode``

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
