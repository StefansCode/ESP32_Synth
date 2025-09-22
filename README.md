# ESP32_Synth

This project will be a digital synthesizer that uses the ESP32.
It should be an upgrade to my [Arduino_Nano_Synth](https://github.com/StefansCode/Arduino_Nano_Synth). Since then, I have learned more about programming microchips and writing good code.

## Hardware
I will use an ESP32 S3, which has a 128-bit Vector Unit. It might be useful for editing wavetables or for using the CORDIC algorithm. I will also use an I2S DAC, which allows for higher quality audio output. Other components I want to use include a small I2C OLED screen, a SPI SD card reader, one or two rotary encoders, some buttons, and maybe some LEDs.

The hardware layout will be highly inspired by a Teenage Engineering Pocket Operator, although I'll use fewer buttons and the functionality will be different.


## Software

For the non-synth parts like the SD card reader or the screen, I will use libraries, but for the synth parts themselves I want to work as close to the hardware as possible. I also want to keep the synth part separate so that it can be used in other projects or even be made into a library.

## Features

#### Oscillator
The [Arduino_Nano_Synth](https://github.com/StefansCode/Arduino_Nano_Synth) uses one timer to change the output value to the next value from a wavetable. By changing the reset value of the timer, one can change the frequency of the sound.
This method allows for only one frequency to be played at a time.

In this project, I want to have a fixed sample rate and keep the upcoming samples in a buffer.

#### A(DS)R envelope

I want to expand the AR envelope to an ADSR envelope and use it for parameters other than amplitude. The [Arduino_Nano_Synth](https://github.com/StefansCode/Arduino_Nano_Synth) can only double or halve the attack and release values. I would like to make it "continuous".

#### Pan and LFO

I'm quite happy with the pan and the LFO so far.

#### Filter

One thing I really want to add is digital filters (high-pass, low-pass, band-pass, comb filter, etc.).

#### Modulation

Another idea is to add frequency or pulse width modulation.