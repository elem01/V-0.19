The installation of the motor temperature sensor is optional. The advantage of installing the motor temperature sensor is to avoid permanent damage/loss of torque of TSDZ2 motor -- please read more here: [[TSDZ2 motor demagnetized due to overheating]].

The firmware shows on LCD3 the motor temperature (this is optional) and can also reduce linearly the motor current while the motor temperature increases (this is optional).

NOTE: to use this motor temperature sensor you will loose the possibility to use the throttle. (If you can't/won't install the sensor then a useful diagnostic is the [non-reversible temperature label](https://nz.rs-online.com/web/p/temperature-sensitive-labels/7799772/) This permanently changes showing the maximum temperature)

The sensor used is the [LM35](http://www.ti.com/lit/ds/symlink/lm35.pdf) that is very popular and easy buy online like on Ebay. It is also very simple to interface with the TSDZ2 motor controller, where just 3 wires need to be connected (please see the information bellow).

The LM35 outputs a linear voltage, 10mV/K, over the temperature range, i.e 2.98V @25C , 3.58V@85C. Because the only free header connector available on the TSDZ2 motor controller that reads an analog voltage signal is the one used for the throttle, the sensor is connected to that header and the throttle can not be connected and used.

There are two types of controller 8 wire with throttle and 6 wire with no-throttle. 

* 8 wire: You will cut the wires and connect sensor to them
* 6 wire: You will pick the encapsulant away from the pcb and solder to the pcb


I connected LM35 to a connector so is possible to remove it when I need, for instance when I want to remove the motor:

[[https://github.com/OpenSource-EBike-firmware/TSDZ2_wiki/blob/master/motor_temperature_sensor-02.jpg]]

[[https://github.com/OpenSource-EBike-firmware/TSDZ2_wiki/blob/master/motor_temperature_sensor-01.jpg]]

## 8 Wire Throttle type. 

I wired the wires to the existing motor controllers wires for throttle. I decided to no cut the throttle wires but leave them in place in the case in future I still want to use them and not the temperature sensor:

[[https://github.com/OpenSource-EBike-firmware/TSDZ2_wiki/blob/master/motor_temperature_sensor-04.jpg]]

I first glued one face of LM35 to a metal face off the motor (the part of the motor that get's hot first) with a tape and them start to put silicone (high temperature version of silicone) and let it dry up to put the final amount and make sure the LM35 face is in close connection to the motor metal part:

[[https://github.com/OpenSource-EBike-firmware/TSDZ2_wiki/blob/master/motor_temperature_sensor-03.jpg]]

## 6 WIre type:

The connection points are clear in the [JBalat Install Video for 6 Wire](https://www.youtube.com/watch?v=Wb8Omk6e7GI)

![6 wire motor control](https://github.com/OpenSource-EBike-firmware/TSDZ2_wiki/blob/master/TSDZ2_motor_controller_without_throttle_wires.jpeg)