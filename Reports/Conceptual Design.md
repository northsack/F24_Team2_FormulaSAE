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

# High-Level Solution

1. Hardware Block Diagram
![Figure 2: Hardware Block Diagram](https://github.com/northsack/F24_Team2_FormulaSAE/blob/conceptual_design/Documentation/Images/Block%20Diagram.png)
2. Operational Flow Chart
![](https://github.com/northsack/F24_Team2_FormulaSAE/blob/conceptual_design/Documentation/Images/Vehicle%20Flow%20Chart.png)

# Atomic Subsystem Specifications
1. Tractive System (High Voltage)​
    1. Motor
    2. Motor Controller
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
        	| Shutdown Circuit (+) and (-)             			 | DC Power        | Input     |

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
    4. Tractive System Active Light
    5. IMD
    6. Charger
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
          	The shutdown circuit is responsible for cutting off power at the high voltage source (The Accumulator) in the event of a failure or misalignment in one of the other systems that power or drive the car.
The input of the shutdown circuit is a power signal, the Grounded Low Voltage (GLV) system voltage. The GLV Master Switch, Tractive System Master Switch, BSPD, IMD, inertia switch, shutdown button, AMS,             BOTS, and HVD Interlock(s) are connected in series and when all these systems are functioning normally they will provide power to the AIR subsystem, thus closing the high voltage Tractive System circuit.
The shutdown circuit will receive power signals from each of the devices connected to it, in series, and send out a power signal to the AIR subsystem.
The user interface for the driver shall consist of the shutdown buttons which will open the shutdown circuit thus shutting down the car’s electrical system, and the active lights provide visual feedback             to what systems are operational or not.
       3. BSPD


# Ethical, Professional, and Standards Considerations

# Resources
1. Budget
2. Skills
3. Timeline

# Statement of Contribution

# References
1. Formula SAE, “Formula SAE Rules 2024 Version 1.0”, fsaeonline.com, <https://www.fsaeonline.com/cdsweb/gen/DownloadDocument.aspx?DocumentID=369d01c0-589d-4ebe-b8d4-b07544f4a52b> (accessed Oct 22, 2024)
