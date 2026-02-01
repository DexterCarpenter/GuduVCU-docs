* Control the HV relays and Pre-charge conditions
* Car has 4 states (Drive, Charge, Standby, and Abort)
* Get temps from PDM and Inverter and control water pump to cool them based on load.
* Drive and Reverse states, read the pedal inputs and translate that to power to the motor. 
* Park state has the car on but no power to the motor but the car is on. This the default state when the car turns on.  
* Charge state happens when the charge port is connected to power. This monitors the charging and allows the user to limit the charge to 80%. Is responsible for keeping the PDM cool while charging (water pump control).
* Standby state is used when the car is powered off, it allows for the car to cool when parked.
* Abort state is there in the case of a critical failure.

### Battery Connecting Procedure
Every time the battery enables HV to the terminals you need to follow a specific procedure.

1. Connect the negative terminal relay
2. Connect the pre-charge resistor relay
3. Wait for the HV lines to come up
4. Disconnect the pre-charge resistor Relay
5. Connect the positive terminal relay

Then the battery is connected to the PDM and ready for driving or charging.

### Water Pump Considerations
When the vehicle is in operation the VCU needs to get the temperatures from the PDM, Inverter, and Motor and adjust the pump speed accordingly. When the vehicle is charging the water pump will also need to active to keep the PDM temps under control.

Something we will need to test is if the control boards can communicate VIA CAN bus when the HV is disconnected. We would want to make sure the cars temperatures are under control before completely turning off the car. If the control boards are able to communicate with the HV disconnected then we can just run it before going into standby. Otherwise we may need to come up with another way to ensure that the car is managing thermals even if the car is turned off.

### Gudu's Implementation
The main thing to keep in mind is that I want to keep the car as mechanical as possible. Giving the electronics control to the VCU for motor and battery control. Keeping the brakes, lights, and fans isolated from the VCU in their original form. Most EVs have states for park and reverse. Because the car is keeping the manual transmission I don't need reverse, I will just shift. On the other side is park, which might be useful but I can just put the car in neutral. I would prefer that if the car is on it is ready to drive. 

## Functions/ Features

When the controller turns on it will have some checks to do then enter standby.

Every time the controller connects the battery to the PDM it **NEEDS** to go through a Precharge cycle. The states the require this are entering drive and when charging. 

When the vehicle is in Drive mode, signaled by the cars ignition being on it first needs to Precharge. 
In the loop it needs to...
* Get data from the PDM and Inverter for their temperatures and adjust the water pump (PWM) accordingly
* Read the throttle position from the two throttle sensors and send CAN messages to the inverter with the throttle amount
* Monitor battery charge levels from the BMS over CAN and display 

The vehicle has a charge mode, this is triggered by .... after connecting the J1772 to the PDM. If the car is able to charge it turns on the M/C switch (Motor Cutoff) which immobilizes the motor and enables the battery controller. The precharge routine needs to run to connect the battery to the PDM. With the car in this state the inverter should not be able to run, even if the ignition is turned on. 
* Get the current state of charge of the battery and stop the battery from charging at %80 when the juice switch is flipped.