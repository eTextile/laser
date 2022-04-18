# eTextile-Laser

### Notes

#### GRBL

##### Clone GRBL source repository

```
git clone https://github.com/gnea/grbl.git
```

##### Enter GRBL source

````shell
cd grbl
````

##### Check out appropriate version & create a branch for it

````shell
git checkout -b extextile-laser v1.1h.20190825
````

##### Apply GRBL patch

````shell
git apply ../grbl-config.patch
````

##### Build GRBL firmwate

````shell
make
````

`avr-gcc` is needed for building the firmware

##### Flash GRBL firmware on an Arduino Uno R3

````shell
make flash PROGRAMMER="-c arduinon -p m328 -P /dev/ttyACM0"
````

`avrdude` is needed for flashing the firmware

## Links

https://github.com/gnea/grbl
https://github.com/gnea/grbl/wiki/Grbl-v1.1-Configuration
https://github.com/gnea/grbl/wiki/Grbl-v1.1-Laser-Mode
https://github.com/gnea/grbl/wiki/Two-Axis-System-Considerations
https://github.com/gnea/grbl/wiki/Wiring-Limit-Switches

