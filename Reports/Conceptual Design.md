_Formula SAE Electric Vehicle Conceptual Design_

Evan Morse, Jesse Munoz, Zach Holt, Erlind Boraj, Graham Robinson  
Tennessee Technological University, ECE Department  
Tennessee Tech Motorsports  
Cookeville, TN, USA  
[emorse42@tntech.edu](mailto:emorse42@tntech.edu), [jdmunoz42@tntech.edu](mailto:jdmunoz42@tntech.edu), [eboraj42@tntech.edu](mailto:eboraj42@tntech.edu), [zsholt42@tntech.edu](mailto:zsholt42@tntech.edu), [glrobinson42@tntech.edu](mailto:glrobinson42@tntech.edu)

_Abstract_—This project aims to assist Tennessee Tech’s Motorsports club by designing the powertrain, controls, and power systems for the club’s first electric vehicle. This project, for both the senior design team and Tennessee Tech Motorsports, serves as an introduction to the development of electric vehicles by exposing engineering students to the rapidly developing field of electric vehicles.

# Intro

This project’s main goal is to design the various electrical systems of an electric formula car for Tennessee Tech University’s Motorsports club, herein referred to as Tennessee Tech Motorsports (TTM). Formula SAE is the organization that hosts the competition that this EV needs to be designed for, so Formula SAE has a set of rules and guidelines. These rules are where the majority of our constraints and specifications will come from and will be discussed in a later section. However, since this is the first EV that TTM is making, it is important to note that the design will be modified and iterated on for years to come, and this will also influence the design decisions.

# Fully Formulated Problem

Specifications of this project:
1. This electric powertrain shall have enough performance to be comparable to Tennessee Tech Motorsports internal combustion engine car.
    1. The EV powertrain of this project shall have a power output comparable to Tennessee Tech Motorsports' internal combustion engine. TTM's internal combustion engine has a power output of 52 horsepower, and 55 ft*lbs of torque. Thus, the EV powertrain shall have a similar power output to match these specifications.
    2.The car shall be able to operate for at least an hour to complete the FSAE endurance event before needing to recharge.
    3.The electric powertrain shall have the capability to reach a top speed of 60 miles per hour.
2. This Formula SAE Electric powertrain shall comply with all rules and regulations specified in the Formula SAE rule book [1]. Some of these rules are listed below:
3. The voltage measured between any two points shall not exceed 600 V DC.
4. The car shall use electric motors only.
5. The tractive system (every part connected to the motor and/or accumulator (battery)) motor shall be connected to the battery through a motor controller.
6. The accumulator container shall be completely closed at all times, and removeable from the vehicle while staying rule compliant.
7. The vehicle shall include a tractive systems active light that shall illuminate when the tractive system is active.
8. The entire Tractive System and GLV System (Grounded Low Voltage) shall be completely galvanically separated.
9. Shutdown System: The shutdown system consists of the following components connected in series. The purpose of this systems is to ensure the safety of the driver, team members in the near viscinity of the vehicle, and the vehicle itself. If one of these safety systems encounters a fault, the system has the ability to shut down all power to the vehicle. Each safety system is daisy chained to the previous/next safety system. Thus, if one system disengages power, none of the main components on the vehicle will be powered. The system shall only function when all contacts of the safety system are closed:
    1. Accumulator Management System
    2. Insulation Monitoring Device
    3. Brake System Plausibility Device
    4. Interlocks
    5. Master Switches
    6. Shutdown Buttons
    7. Brake Over Travel Switch
    8. Inertia Switch

A figure from the Formula SAE Rulebook [1] has been included to give a visual representation of all these systems: 
![Figure 1: Shutdown Circuit of a Formula SAE EV Car](https://github.com/northsack/F24_Team2_FormulaSAE/blob/main/Documentation/Images/Fig.%201%20shutdown%20circuit.png)\
Figure 1: Shutdown Circuit of a Formula SAE EV Car

10. The vehicle shall have an Insulation Monitoring Device (IMD) installed in the Tractive System
11. The vehicle shall have a standalone non programmable circuit (Brake System Plausibility Device – BSPD) to check for simultaneous braking and high power output.
    1. The BSPD shall open the shutdown circuit when both there is a demand for hard braking, and the motor/accumulator is at a level where 5 kW of electrical power in the DC circuit is delivered to the motor at the nominal battery voltage.

Constraints of this project:
1. This electric powertrain shall be designed around the budget allotted by the engineering department. Origin: Allowed budget.
2. This electric powertrain shall be designed with regards to the available tools, resources, and professional expertise available to the College of Engineering students at Tennessee Tech University. Origin: Available resources, either provided or purchased.
3. This electric powertrain shall be designed to operate in environments ranging from 0 C to 25 C. When competing in Michigan, the weather varies every year that the Formula SAE EV competition is held. The powertrain must be operational in a wide range of temperatures. Origin: Location of competition.
4. This electric powertrain shall be constrained by the Tennessee Tech shop policies. To ensure the safety of students working on this vehicle, the battery shall not be charged unless the powertrain is ready for testing. An alternate method of supplying voltage and power to the EV powertrain system must be used. Origin: TTM’s safety standards.

# Comparative Analysis of Potential Solutions

**Hypothesized Solutions**

**Solution A: Custom-Built Battery and Motor System**

This solution involves designing and building a custom battery pack and motor system specifically for the Formula SAE vehicle.
Advantages: Allows for full control over the specifications, such as battery capacity and motor power, potentially optimizing performance for endurance and power output.
Disadvantages: This solution requires significant design and development time, along with a steep learning curve for building a high-performance electric powertrain. Testing and validation time is limited, increasing the risk of performance issues or failures during competition.

**Solution B: Pre-Assembled Electric Motorcycle Powertrain (2022 Zero FXE)**

This solution utilizes the pre-assembled electric powertrain from a 2022 Zero FXE motorcycle, including the motor and battery system.
Advantages: Proven, reliable technology that already meets performance targets (52 horsepower and 55 ft-lbs of torque), reducing design and development time. The off-the-shelf solution minimizes the risk of failure and simplifies integration.
Disadvantages: Higher upfront cost and less flexibility for customization compared to a custom-built system. Additionally, modifications may be limited due to the pre-assembled nature of the system.

**Chosen Solution**

After comparing the two solutions, Solution B: Pre-Assembled Electric Motorcycle Powertrain (2022 Zero FXE) has been selected for the following reasons:

Proven Technology: 

The Zero FXE powertrain offers a reliable, tested system that meets the required power output and endurance criteria.
Reduced Development Risk: Leveraging a pre-assembled system minimizes the risks associated with designing a custom battery and motor system, which could lead to unforeseen challenges during testing and competition.

Focus on Optimization: 

With the powertrain already assembled, the team can concentrate on integrating the system into the vehicle and optimizing performance, reducing time spent on design and manufacturing.

**Conclusion**

The pre-assembled powertrain from the 2022 Zero FXE motorcycle provides the most practical and reliable solution for Tennessee Tech Motorsports’ Formula SAE Electric vehicle. It balances performance with reliability and allows the team to focus on fine-tuning and testing, ensuring compliance with competition rules and regulations.

# High-Level Solution

1. Hardware Block Diagram
![Figure 2: Hardware Block Diagram](https://github.com/northsack/F24_Team2_FormulaSAE/blob/conceptual_design/Documentation/Images/Block%20Diagram.png)
2. Operational Flow Chart
![](https://github.com/northsack/F24_Team2_FormulaSAE/blob/conceptual_design/Documentation/Images/Vehicle%20Flow%20Chart.png)

# Atomic Subsystem Specifications
1. Tractive System (High Voltage)​
   	
	1. Motor
	    - *Interface with other subsystems:*
     
     
                	| Connection                                         | Connection Type | Direction |
        	|----------------------------------------------------|-----------------|-----------|
        	| Phase A                                            | AC Power        | Input     |
        	| Phase B                                            | AC Power        | Input     |
                | Phase C                                            | AC Power        | Input     |
        	| Thermistor                                         | Analog          | Output    |        
	        | Sine Encoder                                       | Analog          | Output    |
                | Cosine Encoder                                     | Analog          | Output    |

			  1. Three-Phase Inputs (Phase A, Phase B, Phase C):<br>
				The motor subsystem will be powered by a three-phase AC system, with Phase A, Phase B, and Phase C providing the alternating current required for motor operation. These inputs will work in synchronization to generate a rotating magnetic field inside the motor, driving the rotor and generating mechanical power to move the vehicle. These phases will be monitored and controlled by the motor controller to ensure smooth and efficient operation of the motor. Proper balancing of these phases is essential for optimal performance and to prevent overheating or damage to the motor windings.
			  2. Thermistor (Temperature Monitoring):<br>
				&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A thermistor will be installed in the motor housing to monitor the temperature of the motor during operation. This sensor will provide real-time temperature data to the motor controller, allowing for thermal management and protection. If the temperature exceeds safe operating limits, the motor controller will take necessary actions such as reducing power output or initiating a system shutdown to prevent motor damage due to overheating.
			3. Sine Encoder (Sin) and Cosine Encoder (Cos):<br>
				&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The motor subsystem will include a sine and cosine encoder, which are critical for providing accurate rotor position feedback to the motor controller. These encoders will generate sine and cosine signals that correspond to the rotor’s angular position, allowing the controller to precisely adjust the current delivered to each phase. This ensures efficient and accurate torque generation, which is vital for both high-performance driving and smooth operation of the vehicle. The encoder system will also play a key role in controlling the motor's speed and synchronization, enabling seamless transitions in power delivery.
Accurate rotor position feedback ensures the motor operates at peak efficiency, delivering the right amount of torque and preventing misalignment. This directly impacts vehicle performance, especially in terms of acceleration and handling during cornering.

2. Motor Controller
	
 The motor controller serves as a fundamental element within the electric powertrain, tasked with overseeing the power distribution between the energy storage unit and the motor, thereby facilitating effective and accurate management of the vehicle's operational capabilities. A detailed examination of its roles and specifications is presented below:  

a. Power Regulation  The motor controller is responsible for regulating the direct current (DC) power sourced from the energy storage unit, converting it to alternating current (AC) power when interfacing with an AC motor, or managing the DC power for a DC motor. This regulation allows for the modulation of the motor's speed and torque. It meticulously adjusts the voltage and current delivered to the motor in response to the driver's throttle input, promoting seamless acceleration and optimal power distribution.  

b. Torque and Speed Control  The motor controller plays a crucial role in managing the torque produced by the motor by varying the current supplied, which allows for precise control over the power output directed to the vehicle's wheels. Furthermore, it regulates the rotational speed of the motor, ensuring that the vehicle can reach its maximum speed of 60 miles per hour while operating efficiently across diverse driving scenarios, from rapid acceleration to steady cruising.

c. Safety and Shutdown Functionality  Integrated within the shutdown system, the motor controller ensures that in the event of a malfunction—such as overheating, excessive current draw, or a failure in the Brake System Plausibility Device—the system can promptly disconnect power to the motor, thereby averting further operation. Additionally, the motor controller is equipped with multiple safety features, including overvoltage, overcurrent, and thermal protection mechanisms, to safeguard the motor and other components of the powertrain from potential damage.  

d. Thermal Management  During operation, particularly under high load conditions, the motor controller generates heat. It is essential for the controller to incorporate a thermal management system, whether through air or liquid cooling, to sustain optimal operating temperatures and prevent overheating during high-power demands or extended operational periods.  

e.  Control Algorithms and Efficiency  The motor controller employs sophisticated control algorithms, such as Field-Oriented Control for AC motors, to enhance performance and efficiency. These algorithms are designed to optimize the motor's response and energy consumption, contributing to the overall effectiveness of the electric powertrain.

 
3. Accumulator:
    - *Interface with other subsystems:*
    
    <br>**High Voltage Connections**
    
	| Connection                                         | Connection Type | Direction |
	|----------------------------------------------------|-----------------|-----------|
	| Motor Controller (+) and (-) Terminals             | DC Power        | Output    |
	| Insulation Monitoring Device (+) and (-) Terminals | DC Power        | Output    |

    <br>**Low Voltage Connections**
	| Connection                                         | Connection Type | Direction |
	|----------------------------------------------------|-----------------|-----------|
	| Shutdown Circuit (+) and (-)             	     | DC Power        | Input     |

   - *Operation:*
	   The accumulator subsystem is responsible for providing high voltage power to the motor and motor controller of the vehicle.  A breakdown of the systems of the Accumulator are as follows:
		1. Accumulator Isolation Relays:<br>
			&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Relays shall be used inside of the Accumulator container to control the power provided to the external connectors of the Accumulator.  Power shall only be provided to the external terminals when the Shutdown Circuit is closed (vehicle is ready to drive).  The AIRs shall be used to control both the positive and negative terminals of the Accumulator. The AIRs shall be normally open.
		2. Precharge Circuit:<br>
			&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;As part of the motor controller's design, capacitors are installed at the main high voltage terminals.  When the Accumulator Isolation Relays (AIRs) are closed (High Voltage (HV) power is turned on), and power is provided to the motor controller.  Without a Precharge Circuit, thousands of Amps can flow through the wires to charge the capacitors inside the motor controller when the AIRs close.  This can be dangerous because it can prematurely wear the AIRs, and possibly even weld the terminals of the AIRs together, preventing proper operation.  To prevent this, the Accumulator shall have a system designed to precharge the HV system to 90% of the Accumulator voltage before closing the AIRs.
		3. Discharge Circuit:<br>
		    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The accumulator shall contain a circuit that can discharge the same capacitors mentioned in statement **b** above.  When the shutdown circuit is open (vehicle is shutting down), the AIRs shall open, and the Discharge Circuit shall safely discharge the capacitors inside of the motor controller.
		4. Voltage Indicator:<br> 
		     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The Accumulator shall have an Indicator that will illuminate when high voltage is present on the external terminals of the accumulator container.  This Indicator shall be controlled by hardware and not software.  Addionally, the Voltage Indicator shall be installed where it can be seen while connecting the Accumulator to the HV Circuit.  The Voltage Indicator shall also be labelled "High Voltage Present."
		5. Accumulator Management System (AMS):<br> 
			&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A system shall be built to monitor the conditions of the accumulator.  This system must monitor the Accumulator while the Tractive System is active, and also while the Accumulator is charging.  If a fault is detected in one of the monitored conditions, the AMS shall open the vehicle's shutdown circuit, cutting off the HV power to the Tractive System.  Additionally, on the occurrence of a fault, the AMS shall turn on the AMS indicator light which shall be a red LED that is visible to the driver of the vehicle and marked with the lettering "AMS".  The AMS shall monitor the following conditions
				<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1. HV Voltage values
				<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2. Protection devices tripped or blown
				<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;3. Temperatures outside of the normal range of operation
	
 5. **Tractive System Active Light (TSAL):**

The Tractive System Active Light (TSAL) is a critical safety feature required by Formula SAE Electric rules to indicate when the vehicle’s high-voltage tractive system is live and energized. The purpose of the TSAL is to alert team members, track officials, and nearby personnel that the vehicle’s high-voltage system is active, ensuring safe handling and operation at all times.

**Design Requirements:**

The TSAL must be clearly visible to all individuals in proximity to the vehicle.
The light shall illuminate when the tractive system voltage exceeds 60V.
It must be controlled entirely by hardware and not by software, ensuring it remains functional even during software or system failures.
The TSAL must be located such that it is visible from all angles while the vehicle is being worked on or during operation on the track.

**Operation:**

When the accumulator is connected to the motor and the tractive system is powered, the TSAL will automatically turn on to indicate the presence of high voltage.
Once the shutdown circuit is triggered and the tractive system is no longer active, the TSAL will turn off, signaling that the high-voltage components are safe to interact with.
Safety Compliance:

The TSAL ensures compliance with Formula SAE Electric rules, which mandate the use of an indicator light to signal an active high-voltage tractive system. This is a key aspect of the safety system, reducing the risk of accidental exposure to high-voltage components.

	7. **Charger**  

The charger serves the essential function of safely recharging the accumulator (battery pack) of the Formula SAE electric vehicle. Its significance lies in maintaining the energy levels of the high-voltage battery, thereby ensuring the vehicle's readiness for endurance competitions and testing scenarios. The design of the charging system must adhere to safety regulations while optimizing operational efficiency.  

**Design Requirements:**  

The charger must align with the voltage and current specifications of the accumulator to avert risks of overcharging or overheating. It should be capable of supplying a regulated current to the battery while simultaneously monitoring its state of charge, temperature, and voltage levels. Compliance with Formula SAE regulations is imperative, which mandates galvanic isolation between the charger and the accumulator to mitigate the risk of electric shocks.  

**Operation:**  

The charging system interfaces with the vehicle’s accumulator through external terminals, facilitating battery charging without necessitating its removal from the vehicle. The charger will interact with the Accumulator Management System (AMS) to oversee battery conditions throughout the charging process, ceasing operation if any anomalies, such as over-temperature or over-voltage, are identified. Charging will only initiate when the tractive system is inactive, in accordance with safety protocols that prohibit charging during testing or active operation.  

**Safety Features:**  

The charger incorporates safety interlocks to ensure operation only occurs when the vehicle’s shutdown system is activated, thereby minimizing the risk of unintended high-voltage exposure. It is engineered to safeguard against short circuits, overheating, and overcharging, thereby enhancing the longevity and safety of the accumulator.

2. Grounded Low Voltage (GLV) System
    1. Safety Systems
       1. Shutdown Circuit:
          - *Interface with other subsystems:*
         
          <br>**High Voltage Connections**
          
 			| Connection                                         | Connection Type | Direction |
        	|----------------------------------------------------|-----------------|-----------|
        	| IMD            | DC Power       | Output    |

           <br>**Low Voltage Connections**
			| Connection                                         | Connection Type | Direction |
        	|----------------------------------------------------|-----------------|-----------|
        	| GVL (+)         			 | DC Power        | Input     |
        	| GVL (-)         			 | DC Power        | Output    |
       	  - *Operation:*
          	The shutdown circuit is responsible for cutting off power at the high voltage source (The Accumulator) in the event of a failure or misalignment in one of the other systems that power or drive the car. The shutdown circuit consists of other subsystems which will be described in their own section. The rest of the components are as follows:
            
            1. Inertia Switch:  
		An inertia switch is a simple switch device designed to stop the flow of electricity in the event of a hard impact. In the case for this system that will be a collision. So if a crash happens the inertia switch will open the shutdown circuit and thus disconnect the Accumulator.
                
            2. Shutdown Buttons:
            	The shutdown buttons are simple buttons that will open the shutdown circuit and thus disconnect the Accumulator.
            
            3. HVD Interlock(s):
                This device(s) provide an added safety measure to the car itself. The HCD Interlocks prevents someone from making contact to the high voltage in the system, as well as provided safety for when the high voltage is being disconnected.

	2. Brake System Plausibility Device (BSPD)
	3. Insulation Monitoring Device (IMD)
		- *Interface with other subsystems:*
  
  		<br>**High Voltage Connections**
          
 			| Connection                                         | Connection Type | Direction |
        	|----------------------------------------------------|-----------------|-----------|
        	| HV (+)(-)            | DC Power       | Input    |
    
           <br>**Low Voltage Connections**
			| Connection                                         | Connection Type | Direction |
        	|----------------------------------------------------|-----------------|-----------|
        	| GLV From BSPD (+)        		 | DC Power        | Input     |
        	| GLV (-)         			 | DC Power        | Output    |
		
		- *Operation:*
		The IMD monitors the insulation resistance between the high voltage system and the ground. If there were to be a fault in the high voltage systems of the vehicle, the IMD would detect it and open the shutdown circuit. When the IMD opens the shutdown circuit, a red indicator light turns on and stays on until the IMD is reset.

i.  Functionality of the BSPD

ii. Brake System Encoder:

The Brake System Plausibility Device (BSPD) serves as an essential safety mechanism that oversees the braking system to avert hazardous situations, such as the simultaneous application of brakes and high power output. The following outlines its components and operational principles:

The BSPD guarantees that high power output from the tractive system is not permitted when the brakes are engaged, thereby preventing the vehicle from accelerating during braking, which poses significant safety risks. Should braking be detected while power output surpasses 5 kW, the BSPD activates the vehicle’s shutdown circuit.

a. Brake Detection Mechanism

The BSPD continuously monitors the brake pedal position sensor to ascertain when the brake pedal is engaged. Upon application of the brakes, the BSPD evaluates the power output from the motor or accumulator to verify if the system is drawing more than 5 kW of power.

b. Monitoring Power Output

The BSPD is responsible for overseeing the electrical power delivered to the motor via the tractive system. If the power output exceeds 5 kW while the brakes are applied, the BSPD recognizes this as a fault condition.

c. Activation of Shutdown Circuit

In instances where braking occurs concurrently with high power output, the BSPD activates the shutdown circuit, thereby disconnecting power to the tractive system and preventing the motor from receiving additional high voltage. This process is automatic and does not require driver intervention, ensuring a prompt response to potentially unsafe conditions.

d. Autonomous Functionality

The BSPD functions as an independent, non-programmable device, distinct from the vehicle’s other electronic control units (ECUs), which enhances its reliability even in the event of failures in other systems. Its separation from software or programmable components further bolsters its safety profile.

e. BSPD Indicator Light

When the BSPD is activated, an indicator light is illuminated to inform the driver and pit crew of the shutdown event. This light is clearly marked "BSPD" and is strategically located on the vehicle's dashboard within the driver’s line of sight.

f. Reset Procedure

After the BSPD has triggered the shutdown circuit, it must be manually reset before the vehicle can resume operation. This ensures that the fault condition has been properly addressed before the vehicle is restarted.

ii. Brake System Encoder  

The Brake System Encoder plays a crucial role in precisely identifying the position of the brake pedal and transmitting this information to the vehicle's control systems. An overview of its components and functionality is presented below:  

a. Brake Pedal Position Detection:  The Brake System Encoder is affixed to the brake pedal assembly, where it gauges the position of the pedal during operation. It transforms the mechanical movement of the brake pedal into an electrical signal, delivering accurate data regarding the extent of braking force applied by the driver.  

b. Signal Relay:  The encoder transmits the brake position signal to the vehicle's control system, which includes the Brake System Plausibility Device (BSPD). This signal is essential for determining the activation of braking, enabling the BSPD to effectively evaluate the system's safety.  

c. Continuous Monitoring:  The Brake System Encoder perpetually tracks the brake pedal position in real time, facilitating an immediate response from the control system to any variations in braking force. This capability ensures that the vehicle behaves responsively, particularly in critical safety scenarios such as abrupt braking or simultaneous braking with high power output.  


# Ethical, Professional, and Standards Considerations
Designing the electronics for a Formula SAE car requires not only technical expertise but also adherence to a set of ethical, professional, and industry standards that ensure safety, integrity, and responsibility throughout the design and implementation process. These considerations include:

1. Safety and Risk Mitigation:
The foremost ethical obligation in designing the car’s electronics is ensuring the safety of the driver, team members, and anyone interacting with the vehicle. High-voltage systems, such as the accumulator and motor subsystems, must be designed with robust safeguards, such as proper insulation, fail-safes, and emergency shutdown circuits. Ethical engineering practice mandates that potential hazards be identified early and mitigated through careful design and rigorous testing, including adherence to fail-safe principles like precharge and discharge circuits.

2. Compliance with Standards and Regulations:
Formula SAE competition rules require compliance with specific technical and safety standards, including those related to high-voltage systems, wiring, and energy storage. Additionally, industry standards, such as those from the Institute of Electrical and Electronics Engineers (IEEE), International Electrotechnical Commission (IEC), and automotive standards like ISO 26262 (functional safety for road vehicles), guide the design and verification processes. Engineers must ensure that the car's electronics comply with these standards to prevent accidents and ensure the integrity of the competition.

3. Environmental Responsibility:
The shift toward electric vehicles (EVs), including Formula SAE electric cars, brings environmental responsibility into focus. Ethical design decisions should consider the environmental impact of materials used, energy efficiency, and waste management, including the disposal and recycling of electronic components and batteries. The design should aim to minimize the car’s ecological footprint while maximizing energy efficiency during operation.

4. Data Privacy and Security:
As the electronics system collects data for vehicle performance monitoring, telemetry, and diagnostics, engineers must consider the ethical implications of data collection, storage, and usage. Ensuring the security of data, especially in the context of wireless communications or during competition, is critical to protect proprietary information and the privacy of the team.

5. Honesty and Transparency in Reporting:
Engineers must practice honesty and transparency when documenting and reporting design decisions, performance metrics, and any faults or issues discovered during testing. Any potential risks or design limitations must be disclosed to avoid harm and ensure accountability. Ethical responsibility also involves not misrepresenting test results or overstating the capabilities of the system, as this can lead to dangerous situations in competition.

6. Team Collaboration and Professionalism:
In a multidisciplinary team, engineers must maintain professionalism, respecting the expertise and contributions of others while promoting an open and collaborative environment. Ethical considerations extend to the fair distribution of work, giving credit where due, and fostering a culture of continuous learning and ethical responsibility. Following professional codes of conduct, such as those outlined by the National Society of Professional Engineers (NSPE) or IEEE, ensures that team members act with integrity and responsibility.

7. Responsibility to Future Engineers and Society:
The Formula SAE competition serves as a learning platform for future engineers. Ethical considerations include mentoring and educating less-experienced team members, ensuring that knowledge transfer happens responsibly. The design decisions made today also set a precedent for the future of automotive and electric vehicle engineering. Designing with long-term societal impact in mind, including promoting safer, more sustainable technologies, is an ethical obligation for engineers working on such projects.

# Resources

**Budget Overview**:

The budget for the Formula SAE electric vehicle project is designed to cover critical components for the powertrain, safety systems, and required tools. This breakdown outlines the costs for key items necessary to meet both performance targets and regulatory compliance.



2022 Zero FXE Motorcycle (Battery & Electric Motor): $7,050

Speed Controller: $925

Aluminum Motor Plate: $125

Fire Blanket: $120

Buckets to Hold Sand (3): $75

DVT Configuration Software and Specialized Cable: $650

Total Current Budget:
$8,945


**Required Skills**:

Electrical Systems Design: Understanding of high-voltage power systems, motor control circuits, and safety protocols.

Control Systems: Knowledge of motor control algorithms (e.g., Field-Oriented Control), regenerative braking, and torque management.

Thermal Management: Ability to design and implement cooling solutions for motor and motor controller components.
Data Acquisition: Proficiency in using telemetry systems to monitor motor and controller performance.

Safety Compliance: Familiarity with Formula SAE regulations and experience in integrating shutdown systems and protective devices.

**Timeline: Gaant Chart**

A broad look at the current timeline of events is as follows:

August – December 2024: Design Project
January – May 2025: Build project
A more detailed look at the current timeline of events is as follows:

2024:

October 28: Conceptual Design Finished
November 30: Detailed Design Finished
2025:

January 20: Start putting the project together
April 11: Have the planned project scope finished and ready for tweaking
May 2: Project finished and ready to present



# Statement of Contribution

# References
1. Formula SAE, “Formula SAE Rules 2024 Version 1.0”, fsaeonline.com, <https://www.fsaeonline.com/cdsweb/gen/DownloadDocument.aspx?DocumentID=369d01c0-589d-4ebe-b8d4-b07544f4a52b> (accessed Oct 22, 2024)
