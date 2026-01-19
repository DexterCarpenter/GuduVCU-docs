* Control the HV relays and Pre-charge conditions
* Car has 5 states (Park, Drive, Reverse, Charge, Abort)
* Get temps from PDM and Inverter and control water pump to cool them based on load.
* Drive and Reverse states, read the pedal inputs and translate that to power to the motor. 
* Park state has the car on but no power to the motor but the car is on. This the default state when the car turns on.  
* Charge state happens when the charge port is connected to power. This monitors the charging and allows the user to limit the charge to 80%. Is responsible for keeping the PDM cool while charging (water pump control).
* Abort state is there in the case of a critical failure.

