I want to acknowledge the fact that a single speed gearbox for an EV is perfect. Low moving parts, easy to maintain. But this is not your moms Tesla, this is a 1980's sports car. I want to properly consider the driving experience. The main two reasons I want to consider the original transmission is that it allows the car to go faster and it maintains the feel of the car. The 2013 Leaf motor and gearbox maxing out at 90 mph. Not that I am thinking I will ever get over 90 mph but I could never get over 90 mph. This car is a drivers car, no power steering, ass 3 inches off the ground with every interaction directly interacting with the car and the road. It is a joy to drive and I worry that losing the manual transmission will remove some of that joy. It will still be the same planted chassis, same direct steering, but you wont have the same control over the power.

I am going to start with all the info about the two options and how they interact with the transmissions. To start there is a chart of the Nissan leaf's 80kW motor output. This is going to be critical to keep in mind as I document each transmission and the RPMs needed for driving.

![[EM57_EfficencyTorqueRPM.PNG]]

I have 185/60R14 tires on the car currently.

### **CRX 5 Speed Manual Transmission:**

Using the existing transmission would require me to mount the output shaft of the leaf motor to the flywheel from the CRX motor and mount it to the transmission such that the flywheel, clutch, and plates are in the same position as the D15 we are removing. I would need to make a motor mount/ mounts to support the electric motor but I could continue to use the existing transmission mounts and CV axles.

Big downside is the torque steering. I would need to limit torque in software to prevent the large difference in half axles from pulling the car to the right when you put your foot down. With one axle being over a foot longer than the other. The other negative factor is weight. The original transmission weighs ~68lbs, I cant get the exact weight of the Nissan gearbox but I would guess it weighs 35-40lbs and the added weight of the flywheel and adapter hardware would weigh 30-45lbs. Because of this I am guessing that using the original transmission would weigh 60-100lbs more than the Nissan gearbox.

Ratios: 2.92/1.764/1.181/.846/.714 F/D 4.428

![[CRX Speed.png]]
### **Leaf Single speed Transmission:**

This gearbox was designed by Nissan for this motor. The biggest pro is simplicity, maintaining the transmission is super easy and there is no risk of burning out the clutch or incorrectly shifting. The other big pro is weight saving up to 100lbs by using this transmission. 

Big down side of this choice would be that I would need to make custom CV axles from the Nissan half axle output to the CRX wheel hubs. I would also need to fabricate custom motor mounts and possibly mounting locations on the chassis. 

Ratio: 8.193

![[Leaf Speed.png]]

**Decision Matrix:**

Comparing the transmission of CRX to the Leaf shows that the 2nd gear of the manual transmission is very close to the fixed gear of the Leaf. Shifting would be optional for those times when you want to go faster or have more control. It could be a nice middle ground, a little bit of the best of both worlds. 

