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
    2.	The car shall be able to operate for at least an hour to complete the FSAE endurance event before needing to recharge.
    3.	The electric powertrain shall have the capability to reach a top speed of 60 miles per hour.
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
![Figure 2: Hardware Block Diagram](https://github.com/northsack/F24_Team2_FormulaSAE/blob/conceptual_design/Documentation/Images/Block%20Diagram%203.png)
2. Operational Flow Chart
![](https://github.com/northsack/F24_Team2_FormulaSAE/blob/conceptual_design/Documentation/Images/Vehicle%20Flow%20Chart%204.png)

# Atomic Subsystem Specifications

- **Motor:**
  - *Interface with other subsystems*

      | Connection     | Connection Type | Direction |
      | -------------- | --------------- | --------- |
      | Phase A        | AC Power        | Input     |
      | Phase B        | AC Power        | Input     |
      | Phase C        | AC Power        | Input     |
      | Thermistor     | Analog          | Output    |
      | Sine Encoder   | Analog          | Output    |
      | Cosine Encoder | Analog          | Output    |
  - *Operation:*  
  	1. Three-Phase Inputs (Phase A, Phase B, Phase C):  
  The motor subsystem shall be powered by a three-phase AC system, with Phase A, Phase B, and Phase C providing the alternating current required for motor operation. These inputs shall work in synchronization to generate a rotating magnetic field inside the motor, driving the rotor and generating mechanical power to move the vehicle. These phases shall be monitored and controlled by the motor controller to ensure smooth and efficient operation of the motor. Proper balancing of these phases is essential for optimal performance and to prevent overheating or damage to the motor windings.
          
  	2. Thermistor (Temperature Monitoring):  
  A thermistor shall be installed in the motor housing to monitor the temperature of the motor during operation. This sensor shall provide real-time temperature data to the motor controller, allowing for thermal management and protection. If the temperature exceeds safe operating limits, the motor controller shall take necessary actions such as reducing power output or initiating a system shutdown to prevent motor damage due to overheating.
  
  	3. Sine Encoder (Sin) and Cosine Encoder (Cos):  
  The motor subsystem shall include a sine and cosine encoder, which are critical for providing accurate rotor position feedback to the motor controller. These encoders shall generate sine and cosine signals that correspond to the rotor’s angular position, allowing the controller to precisely adjust the current delivered to each phase. This ensures efficient and accurate torque generation, which is vital for both high-performance driving and smooth operation of the vehicle. The encoder system shall also play a key role in controlling the motor's speed and synchronization, enabling seamless transitions in power delivery.  
  Sine and cosine encoders enhance performance in applications like Formula SAE vehicles by providing high-resolution feedback on motor position and velocity. These encoders generate continuous analog signals that represent the motor’s rotational position. Their design allows fine interpolation, improving the precision of position readings and reducing errors compared to standard incremental encoders. This precision is crucial in high-performance electric vehicles, where accurate position data ensures smooth motor control and efficient power usage, especially at high speeds [2], [3].  
  One key advantage of sine-cosine encoders is their ability to use tan⁻¹ fine interpolation within a signal period, yielding higher accuracy in position readings. This reduces position error and ensures smoother control when the vehicle accelerates or decelerates. Additionally, sine-cosine encoders support high-resolution feedback loops, which enhance velocity control and stability, resulting in a more responsive and efficient drivetrain—important factors in racing scenarios​ [2], [3].

- **Motor Controller:**
  - *Interface with other subsystems*

      | Connection     | Connection Type | Direction |
      | -------------- | --------------- | --------- |
      | Battery		 | DC Power        | Input     |
      | Low Voltage    | DC Power        | Input     |
      | APP 1          | Analog          | Input     |  
      | App 2     	 | Analog          | Input     |   
      | BSE            | Analog          | Input     |  
      | Phase A        | AC Power        | Output    |   
      | Phase B        | AC Power        | Output    |   
      | Phase C        | AC Power        | Output    |    
      | Thermistor     | Analog          | Input     |   
      | Sine Encoder   | Analog          | Input     | 
      | Cosine Encoder | Analog          | Input     |

  - *Operation:*  
  	1. Power Regulation:  
  The motor controller shall regulate the direct current (DC) power sourced from the energy storage unit, converting it to alternating current (AC) power for an AC motor or managing DC power for a DC motor. This regulation shall enable the modulation of motor speed and torque, with the controller adjusting voltage and current in response to the driver's throttle input to ensure seamless acceleration and optimal power distribution.

  	2. Torque and Speed Control:  
  The motor controller shall manage the motor’s torque by varying the current supplied, allowing precise control over power output to the vehicle’s wheels. Additionally, it shall regulate the motor’s rotational speed, enabling the vehicle to reach its maximum speed of 60 miles per hour and operate efficiently across varied driving scenarios, including rapid acceleration and steady cruising.

  	3. Safety and Shutdown Functionality:  
  The motor controller shall be integrated within the shutdown system, ensuring that in the event of a malfunction—such as overheating, excessive current draw, or a Brake System Plausibility Device failure—the system shall promptly disconnect power to the motor, preventing further operation. The motor controller shall also include multiple safety features, such as overvoltage, overcurrent, and thermal protection, to safeguard the motor and powertrain components from potential damage.

  	4. Thermal Management:  
  The motor controller shall incorporate a thermal management system, whether through air or liquid cooling, to maintain optimal operating temperatures and prevent overheating, especially under high-power demands or prolonged operation.

  	5. Control Algorithms and Efficiency:  
  The motor controller shall employ advanced control algorithms, such as Field-Oriented Control for AC motors, to maximize performance and efficiency. These algorithms shall be designed to optimize motor response and energy consumption, contributing to the overall effectiveness of the electric powertrain.

 
- **Accumulator:**
  - *Interface with other subsystems:*
  
  	**High Voltage Connections**

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
		1. Accumulator Isolation Relays:  
		Relays shall be used inside of the Accumulator container to control the power provided to the external connectors of the Accumulator.  Power shall only be provided to the external terminals when the Shutdown Circuit is closed (vehicle is ready to drive).  The AIRs shall be used to control both the positive and negative terminals of the Accumulator. The AIRs shall be normally open.
		2. Precharge Circuit:  
		As part of the motor controller's design, capacitors are installed at the main high voltage terminals.  When the Accumulator Isolation Relays (AIRs) are closed (High Voltage (HV) power is turned on), and power is provided to the motor controller.  Without a Precharge Circuit, thousands of Amps can flow through the wires to charge the capacitors inside the motor controller when the AIRs close.  This can be dangerous because it can prematurely wear the AIRs, and possibly even weld the terminals of the AIRs together, preventing proper operation.  To prevent this, the Accumulator shall have a system designed to precharge the HV system to 90% of the Accumulator voltage before closing the AIRs.
            
		3. Discharge Circuit:  
		The accumulator shall contain a circuit that can discharge the same capacitors mentioned in statement **b** above.  When the shutdown circuit is open (vehicle is shutting down), the AIRs shall open, and the Discharge Circuit shall safely discharge the capacitors inside of the motor controller.
            
		4. Voltage Indicator:  
		The Accumulator shall have an Indicator that will illuminate when high voltage is present on the external terminals of the accumulator container.  This Indicator shall be controlled by hardware and not software.  Addionally, the Voltage Indicator shall be installed where it can be seen while connecting the Accumulator to the HV Circuit.  The Voltage Indicator shall also be labelled "High Voltage Present."
             
		5. Accumulator Management System (AMS):  
		A system shall be built to monitor the conditions of the accumulator.  This system must monitor the Accumulator while the Tractive System is active, and also while the Accumulator is charging.  If a fault is detected in one of the monitored conditions, the AMS shall open the vehicle's shutdown circuit, cutting off the HV power to the Tractive System.  Additionally, on the occurrence of a fault, the AMS shall turn on the AMS indicator light which shall be a red LED that is visible to the driver of the vehicle and marked with the lettering "AMS".  The AMS shall monitor the following conditions  
            1. HV Voltage values
            2. Protection devices tripped or blown
            3. Temperatures outside of the normal range of operation
	
 - **Tractive System Active Light (TSAL):**  
 	- *Interface with other subsystems:*
  
      **High Voltage Connections**

      | Connection                                         | Connection Type | Direction |
      |----------------------------------------------------|-----------------|-----------|
      | Accumulator            | AC Power       | Input    |

      <br>**Low Voltage Connections**
      | Connection                                         | Connection Type | Direction |
      |----------------------------------------------------|-----------------|-----------|
      | Shutdown Circuit (+)             	     | DC Power        | Input     |
    
		a. The Tractive System Active Light

		(TSAL) shall serve as a critical safety feature, as required by Formula SAE Electric rules, to indicate when the vehicle’s high-voltage tractive system is live and energized. The TSAL shall alert team members, track officials, and nearby personnel to the active status of the high-voltage system, ensuring safe handling and operation at all times.

		b. Design Requirements:

		The TSAL shall be clearly visible to all individuals near the vehicle. It shall illuminate whenever the tractive system voltage exceeds 60V. The TSAL shall be controlled entirely by hardware, not by software, ensuring functionality even in the event of software or system failures. Additionally, the TSAL shall be positioned to remain visible from all angles during vehicle maintenance and operation on the track.

		c. Safety Compliance:

		The TSAL shall ensure compliance with Formula SAE Electric rules, which mandate an indicator light to signal an active high-voltage tractive system. This feature shall be integral to the vehicle's safety system, reducing the risk of accidental exposure to high-voltage components.

		d. Operation:

		When the accumulator is connected to the motor and the tractive system is powered, the TSAL shall automatically turn on to indicate the presence of high voltage. Once the shutdown circuit is triggered and the tractive system is no longer active, the TSAL shall turn off, signaling that the high-voltage components are safe to interact with.


- **Charger:**  
	- *Interface with other subsystems:*
  
      **High Voltage Connections**

      | Connection                                         | Connection Type | Direction |
      |----------------------------------------------------|-----------------|-----------|
      | Accumulator            | AC Power       | Output    |
        
		a. Interface with other subsystems:

		The charger shall serve the essential function of safely recharging the accumulator (battery pack) of the Formula SAE electric vehicle, ensuring energy levels are maintained for endurance competitions and testing scenarios. The charging system shall adhere to all safety regulations while optimizing operational efficiency.

		b. Design Requirements:

		The charger shall align with the voltage and current specifications of the accumulator to avoid risks of overcharging or overheating. It shall be capable of supplying a regulated current while monitoring state of charge, temperature, and voltage levels. Compliance with Formula SAE regulations shall be ensured, requiring galvanic isolation between the charger and the accumulator to mitigate electric shock risk.

		c. Safety Features:

		The charger shall incorporate safety interlocks to ensure operation occurs only when the vehicle’s shutdown system is active, minimizing high-voltage exposure risks. It shall include protections against short circuits, overheating, and overcharging to enhance the accumulator’s safety and longevity.

		d. Operation:

		The charger shall interface with the accumulator through external terminals, allowing charging without removal from the vehicle. It shall interact with the Accumulator Management System (AMS) to monitor battery conditions throughout charging, ceasing operation if anomalies, such as over-temperature or over-voltage, are detected. Charging shall only initiate when the tractive system is inactive, per safety protocols prohibiting charging during testing or active operation.

- **Shutdown Circuit**  
The shutdown circuit is mostly made up of components that can be purchased and connected to the circuit. However, some components are more involved and require a more detailed description. These components are the Brake System Plausibility Device (BSPD) and the Insulation Monitoring Device (IMD).
	- *Interface with other subsystems:*

        **High Voltage Connections**

        | Connection                                         | Connection Type | Direction |
        |----------------------------------------------------|-----------------|-----------|
        | IMD            | DC Power       | Output    |

       <br>**Low Voltage Connections**
        | Connection                                         | Connection Type | Direction |
        |----------------------------------------------------|-----------------|-----------|
        | GVL (+)         			 | DC Power        | Input     |
        | GVL (-)         			 | DC Power        | Output    |
        - *Operation:*
          The shutdown circuit shall cut off power at the high voltage source (The Accumulator) in the event of a failure or misalignment in one of the other systems that power or drive the car. The shutdown circuit consists of other subsystems which will be described in their own section. The rest of the components are as follows:

          1. Inertia Switch:  
		An inertia switch is a simple switch device designed to stop the flow of electricity in the event of a hard impact. In the case for this system that will be a collision. So if a crash happens the inertia switch shall open the shutdown circuit and thus disconnect the Accumulator.
                
            2. Shutdown Buttons:  
            	The shutdown buttons are simple buttons that shall open the shutdown circuit and thus disconnect the Accumulator.
            
            3. HVD Interlock(s):  
                This device(s) provide an added safety measure to the car itself. The HVD Interlocks shall prevent someone from making contact to the high voltage in the system, as well as provided safety for when the high voltage is being disconnected.

-	**Brake System Plausibility Device (BSPD):**  
The BSPD is a component in the shutdown circuit and is one of the more complex pieces of the circuit.

	- *Interface with other subsystems:*

        **Low Voltage Connections**
        | Connection                                         | Connection Type | Direction |
        |----------------------------------------------------|-----------------|-----------|
        | GVL (+)         			 | DC Power        | Input     |
        | Brake Presure Sensor        			 | Analog        | Input     |
        | Current Sensor         			 | Analog        | Input     |
        | GVL (-)         			 | DC Power        | Output     |

      - *Operation:*<br>
         The Brake System Plausibility Device (BSPD) serves as an essential safety mechanism that shall oversee the braking system to avert hazardous situations, such as the simultaneous application of brakes and high power output. The following outlines its components and operational principles:
         
          1. Brake System Encoder:  
          The BSPD guarantees that high power output from the tractive system is not permitted when the brakes are engaged, thereby preventing the vehicle from accelerating during braking, which poses significant safety risks. Should braking be detected while power output surpasses 5 kW, the BSPD shall open the vehicle’s shutdown circuit.

         2. Brake Detection Mechanism:  
         The BSPD continuously monitors the brake pedal position sensor to ascertain when the brake pedal is engaged. Upon application of the brakes, the BSPD shall evaluate the power output from the motor or accumulator to verify if the system is drawing more than 5 kW of power.

         3.  Monitoring Power Output:  
         The BSPD is responsible for overseeing the electrical power delivered to the motor via the tractive system. If the power output exceeds 5 kW while the brakes are applied, the BSPD shall recognize this as a fault condition.

         4.  Activation of Shutdown Circuit:  
         In instances where braking occurs concurrently with high power output, the BSPD shall open the shutdown circuit, thereby disconnecting power to the tractive system and preventing the motor from receiving additional high voltage. This process is automatic and does not require driver intervention, ensuring a prompt response to potentially unsafe conditions.

         5.  Autonomous Functionality:  
         The BSPD shall function as an independent, non-programmable device, distinct from the vehicle’s other electronic control units (ECUs), which enhances its reliability even in the event of failures in other systems. Its separation from software or programmable components further bolsters its safety profile.

         6. BSPD Indicator Light:  
         When the BSPD is activated, an indicator light shall be illuminated to inform the driver and pit crew of the shutdown event. This light shall be clearly marked "BSPD" and strategically located on the vehicle's dashboard within the driver’s line of sight.

         7. Reset Procedure:  
         After the BSPD has triggered the shutdown circuit, it shall be manually reset before the vehicle can resume operation. This ensures that the fault condition has been properly addressed before the vehicle is restarted.

         8. Brake System Encoder:  
         The Brake System Encoder shall precisely identify the position of the brake pedal and transmitting this information to the vehicle's control systems. An overview of its components and functionality is presented below:<br>

         	1. Brake Pedal Position Detection:  
            The Brake System Encoder is affixed to the brake pedal assembly, where it gauges the position of the pedal during operation. It shall transform the mechanical movement of the brake pedal into an electrical signal, delivering accurate data regarding the extent of braking force applied by the driver.

         	2. Signal Relay:  
            The encoder shall transmit the brake position signal to the vehicle's control system, which includes the Brake System Plausibility Device (BSPD). This signal is essential for determining the activation of braking, enabling the BSPD to effectively evaluate the system's safety. 

        	3. Continuous Monitoring:  
            The Brake System Encoder shall perpetually track the brake pedal position in real time, facilitating an immediate response from the control system to any variations in braking force. This capability ensures that the vehicle behaves responsively, particularly in critical safety scenarios such as abrupt braking or simultaneous braking with high power output.
            
- **Insulation Monitoring Device (IMD):**  
The IMD is a component in the shutdown circuit and will be purchased but its inclusion in the circuit is more involved.
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
      The IMD shall monitor the insulation resistance between the high voltage system and the ground. If there were to be a fault in the high voltage systems of the vehicle, the IMD shall detect and open the shutdown circuit. When the IMD opens the shutdown circuit, a red indicator light shall turn on and stay on until the IMD is reset.

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

To address the consideration above, the following changes shall be implemented in our design:

1. Enhanced Safety Mechanisms:

	a. We may need to incorporate additional safety features or redundancies to mitigate risks. Implementing more rigorous isolation measures around high-voltage systems to protect against electrical shock. This will be the shut down circuits in the subsystems specifications.
   
	b. Including overcurrent protection, such as fuses or circuit breakers, to prevent damage or dangerous situations in case of electrical faults.

	c. Adding detailed interlock systems in the shutdown circuit to ensure rapid and safe disconnection in emergencies.

2. Increased Design Complexity to Meet Standards:

	a. A modular design that simplifies testing and replacement, ensuring each component adheres to required safety and performance standards. Most of the components were already tested on the 2022 Zero FXE bike and were easily movable and replaceable. All that is needed is reassembling and connecting the components together [4].
    
	b. Adding a thermistor for monitoring critical parameters such as temperature and voltage in real time.

3. Environmental Considerations in Component Selection:

	a. Considering a design with minimal electronic waste. This was done by reusing the system 2022 Zero FXE  bike.

4. Transparency in Documentation and Testing:

	a. Ethical standards emphasize the accuracy and transparency of documentation.
	Detailed, accessible design documentation that clearly outlines the functioning of each subsystem and records all design decisions. This is demonstrated in our GitHub documentation.
    
	b. Clear records of test results and protocols, highlighting any potential system 	  limitations or issues found during testing.

5. Design for Knowledge Transfer and Team Continuity:

	a. Since Formula SAE projects often pass to new team members each year, prioritizing clear, modular, and well-documented design can ease transitions.

	b. A design that’s modular enough for easy component replacement, troubleshooting, and upgrades.
    
	c. Comprehensive user and maintenance guides that help future team members understand the system and make modifications without compromising safety or performance.











# Resources

**Budget Overview**:

The budget for the Formula SAE electric vehicle project shall cover all critical components necessary for the powertrain, safety systems, and required tools to ensure that performance targets and regulatory compliance are met.



| **Description**                                | **Quantity** | **Unit Cost** | **Total** | **Assigned Team Member**              |
|------------------------------------------------|--------------|---------------|-----------|---------------------------------------|
| **COE Lab Request/ Sponsorship**               |              |               | **$1,600.40** |                                       |
| Start Up Tools/ Safety                         |              |               | $1,600.40 | All Team Members                      |
| U.S. General 30 in., 5-Drawer Mechanics Cart, Green |            |               | $279.00    | All Team Members                      |
| Kobalt 300-Piece Standard and Metric Tool Set  |              |               | $249.00    | All Team Members                      |
| Kobalt 10-Piece Assorted Pliers                |              |               | $49.98     | All Team Members                      |
| Kobalt 18-Piece Plastic Handle Magnetic Screwdriver Set | |            | $19.98     | All Team Members                      |
| Sevcon DVT Configuration Software & IXXAT Cable|              |               | $502.32    | **Graham Robinson**                   |
| McMaster-Carr Vehicle Wire Assortments         |              |               | $47.00     | **All Team Members**                  |
| Jrready ST6359 Deutsch Connector Kit           |              |               | $185.00    | **All Team Members**                  |
| Sevcon Wiring Harness -- Dual Signal Throttle  |              |               | $268.12    | **Graham Robinson**                   |
| Battery Blanket                                | 2            | $109.00       | $218.00    | **Evan Morse**                        |
| Tractive system active light                   |              |               | $60.00     | **Graham Robinson**                   |
| Buzzer for tractive system active              |              |               | $63.00     | **Graham Robinson**                   |
| ISOMETER® IR155 3204 (IMD)                     |              |               | $25.00     | **Erlind Boraj**                      |
| Sensata Resettable Crash Sensor (Inertia Switch)|            |               | $60.00     | **Zachary Holt**                      |
| HT-010402 Throttle Position Sensor             | 2            | $160.00       | $320.00    | **Graham Robinson**                   |
| T-Shirts work Shirts                           | 20           | $50.00        | $1,000.00  | **All Team Members**                  |
| Dress Shirts                                   | 20           | $50.00        | $1,000.00  | **All Team Members**                  |
| Office Supplies                                |              |               | $200.00    | **All Team Members**                  |
| Presentation Material                          |              |               | $400.00    | **All Team Members**                  |
| Design Competition Banners                     |              |               | $750.00    | **All Team Members**                  |
| SAE mandated and sponsor decals                |              |               | $850.00    | **All Team Members**                  |
| **COE Budget Total**                           |              |               | **$6,546.40** |                                       |





# **Required Skills**:

| **Team Member**        | **Subsystem**                     |
|------------------------|-----------------------------------|
| **Evan Morse**         | Accumulator                       |
| **Graham Robinson**    | Motor Controller, charger, tractive system active light |
| **Zachary Holt**       | Safety systems, BOTS              |
| **Erlind Boraj**       | Motor and IMD                     |
| **Jesse Munoz**        | Safety Systems, BSPD              |

Electrical Systems Design: Understanding of high-voltage power systems, motor control circuits, and safety protocols.

Control Systems: Knowledge of motor control algorithms (e.g., Field-Oriented Control), regenerative braking, and torque management.

Thermal Management: Ability to design and implement cooling solutions for motor and motor controller components.
Data Acquisition: Proficiency in using telemetry systems to monitor motor and controller performance.

Safety Compliance: Familiarity with Formula SAE regulations and experience in integrating shutdown systems and protective devices.

# **Timeline: Gaant Chart**

![](https://github.com/northsack/F24_Team2_FormulaSAE/blob/conceptual_design/Documentation/Images/Online%20Gantt%2020241102.png)



# Statement of Contribution
- **Evan Morse:** Operational flow chart, hardware block diagram. Subsystem assignment: Accumulator 
- **Graham Robinson:** Compare solutions, resources Subsystem assignment: Motor Controller, charger
- **Zachary Holt:** Operational flow chart, hardware block diagram. PowerPoint documentation for the Conceptual Design, including detailed charts, Timeline (Gantt Chart) Subsystem assignment: Safety systems
- **Erlind Boraj:** Ethical, professional, and standards considerations. Subsystem assignment: Motor, tractive system active light
- **Jesse Munoz:** Introduction and Fully Formulating the Problem. Subsystem assignment: Safety Systems

# References
1. Formula SAE, “Formula SAE Rules 2024 Version 1.0”, fsaeonline.com, <https://www.fsaeonline.com/cdsweb/gen/DownloadDocument.aspx?DocumentID=369d01c0-589d-4ebe-b8d4-b07544f4a52b> (accessed Oct 22, 2024)
2. Kollmorgen, "FPGA-Based Sin/Cos Encoder Processing," Kollmorgen Developer Network, Accessed: Oct. 23, 2024. <https://www.kollmorgen.com/en-us/developer-network/fpga-based-sin-cos-encoder-processing>
3. linearmotiontips, "What are the differences between incremental and sine-cosine encoders?" linearmotiontips.com, Accessed: Oct. 26, 2024. <https://www.linearmotiontips.com/differences-between-incremental-and-sine-cosine-encoders/>
4. Zero Motorcycles, "Zero Motorcycles FXE", zeromotorcycles.com, Accessed: Oct. 26, 2024. <https://zeromotorcycles.com/model/zero-fxe>
