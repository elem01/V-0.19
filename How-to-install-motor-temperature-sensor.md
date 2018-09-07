The installation of the motor temperature sensor is optional. The advantage of installing the motor temperature sensor is to avoid permanent damage/loss of torque of TSDZ2 motor -- please read more here: [[TSDZ2 motor demagnetized due to overheating]].

The firmware shows on LCD3 the motor temperature (this is optional) and can also reduce linearly the motor current while the motor temperature increases (this is optional).

NOTE: to use this motor temperature sensor you will loose the possibility to use the throttle.

The sensor used is the LM35 that is very popular and easy buy online like on Ebay. It is also very simple to interface with the TSDZ2 motor controller, where just 3 wires need to be connected (please see the information bellow).

The LM35 outputs a linear voltage over the temperature change. Because the only free header connector available on the TSDZ2 motor controller that reads an analog voltage signal is the one used for the throttle, the sensor is connected to that header and the throttle can not be connected and used.

I connected LM35 to a connector so is possible to remove it when I need, for instance when I want to remove the motor.
[[https://github.com/OpenSource-EBike-firmware/TSDZ2_wiki/blob/master/motor_temperature_sensor-02.jpg]]

[[https://github.com/OpenSource-EBike-firmware/TSDZ2_wiki/blob/master/motor_temperature_sensor-01.jpg]]

[[https://github.com/OpenSource-EBike-firmware/TSDZ2_wiki/blob/master/motor_temperature_sensor-04.jpg]]

[[https://github.com/OpenSource-EBike-firmware/TSDZ2_wiki/blob/master/motor_temperature_sensor-03.jpg]]