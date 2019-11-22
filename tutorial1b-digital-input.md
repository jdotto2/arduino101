# Digital Input

We can change the digital pin into input mode by setting `pinMode` to either `INPUT` or `INPUT_PULLUP`. `INPUT` mode is high impedence mode that the given pin can change to whatever voltage with very little amount of energy or current, where as `INPUT_PULLUP` mode connect an internal pull-up resistor that the given pin will be passively high when there is no input, this is useful as it prevents the input pin from floating and 
susceptible to noise.

