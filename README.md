# eTextile-Laser

## Notes

### GRBL

#### Building the firmware

##### Clone GRBL source repository

````shell
git clone https://github.com/gnea/grbl.git
````

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

#### Configuring the firmware

These settings commands should be sent to the GRBL firmware only once after (re)flashing, they are saved in EEPROM.

##### Invert port directions for X & Y axis

```
$3=3
```

##### Enable hard limits

```
$21=1
```

##### Enable homing cycle

```
$22=1
```

##### Invert homing directions for X & Y axis

```
$23=3
```

##### Increase homing seek rate

```
$25=2000
```

##### Enable laser mode

```
$32=1
```

##### Set steps/mm for X axis

```
$100=64
```

##### Set steps/mm for Y axis

```
$101=154
```

##### Increase max rate for X axis

```
$110=2500
```

##### Increase max rate for Y axis

```
$111=2500
```

##### Increase acceleration for X axis

```
$121=15
```

##### Increase acceleration for Y axis

```
$122=15
```

##### Set max travel for X axis

```
$131=1000
```

##### Set max travel for Y axis

```
$132=500
```

## Links

##### GRBL

https://github.com/gnea/grbl

https://github.com/gnea/grbl/wiki/Grbl-v1.1-Configuration

https://github.com/gnea/grbl/wiki/Grbl-v1.1-Laser-Mode

https://github.com/gnea/grbl/wiki/Two-Axis-System-Considerations

https://github.com/gnea/grbl/wiki/Wiring-Limit-Switches

##### Misc

[LinuxCNC "G-Code" Quick Reference](http://linuxcnc.org/docs/2.5/html/gcode.html)
