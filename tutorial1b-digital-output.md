# Digital Input

To use the pin to read a digital input, we can set the pin into ``INPUT`` or ``INPUT_PULLUP`` via ``pinMode``

```
void setup() {
  pinMode(7, INPUT_PULLUP);
  pinMode(8, OUTPUT);
}

void loop() {
  int reading = digitalRead(7);
  digitalWrite(8, reading);

}
```
