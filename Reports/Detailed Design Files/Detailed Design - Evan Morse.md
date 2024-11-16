
_Formula SAE Electric Vehicle Conceptual Design_

Evan Morse  
Tennessee Technological University, ECE Department  
Tennessee Tech Motorsports  
Cookeville, TN, USA  
[emorse42@tntech.edu](mailto:emorse42@tntech.edu)


# Function of the Subsystem

The Accumulator (Battery) subsystem is responsible for safely storing and providing high voltage DC power to the motor controller of the Formula SAE Electric vehicle.  The Accumulator is an closed container that houses battery cells, isolation relays (AIRs), temperature sensors, and voltage sensors.  Externally, two terminals provide the high voltage power for the motor controller, two low voltage terminals connected to the shutdown circuit are used to control the AIRs, and finally, a voltage indicator LED turns on when high voltage is present at the output terminals.

To safely store energy, the Accumulator has internal temperature sensors and voltage sensors to monitor the condition of the battery cells.  The Accumulator must be able to turn off high voltage power to the external terminals if these voltage or temperature sensors read values too high or too low.  The Accumulator must also be able to turn off external high voltage power if the shutdown circuit is opened.



# Specifications and Constraints

- #### Specifications
   
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

- ### Constraints  
	1. The Formula SAE Electric vehicle shall be able to complete all Formula SAE Dynamic Events.
		1. Autocross
			- Vehicle shall complete four passes of a road course estimating 1 km.
		2. Skidpad  
			- Vehicle shall complete four passes of a 65 m road course.
		3. Acceleration  
			- Vehicle shall complete four passes of a 75 m straight line drag strip.
		4. Endurance
			- Vehicle shall complete a road course estimating 22 km.  This event usually takes 30-45 minutes to complete.

# Overview of Proposed Solution

The Accumulator subsystem can be broken down into three subsequent subsystems.  
1. Battery Cells  
	The battery cells are the part of the Accumulator that store the electrical energy.  For this project, off the shelf battery cells shall be used.  Designing these battery cells so that they are arranged to deliver the capacity of power for the required duration is what will make this subsystem of the Accumulator successful.  When placed in series, the individual battery cell voltage will be added, increasing the voltage.  When placed in parallel, the load is split between the parallel paths, thus increasing the run time of the battery.  The two factors that will influence how the cells of the battery are arranged are as follows:
    
    1. The voltage and current draw of the motor.  
    2. The duration of operation of the motor.
   
	The final battery cell arrangement for the Accumulator shall be 28s2p.

2. Precharge & Discharge Circuits  
	The precharge and discharge circuits will be located on a PCB installed on the inside of the Accumulator container.  The precharge and discharge circuits will take high voltage inputs from the output of the battery cells inside the accumulator, and then slowly output increasing voltage to charge the capacitor of the motor controller.  The voltage of the output of the battery cells needs to be measured , the size of the capacitors 
    
3. Accumulator Management System  
	The Accumulator Mangement System shall be 

# Interface with Other Subsystems

The Accumulator will have the following connections to other subsystems in the electric vehicle.  
  
  **High Voltage Connections**
  | Connection                                         | Connection Type | Direction |
  |----------------------------------------------------|-----------------|-----------|
  | Motor Controller (+) and (-) Terminals             | DC Power        | Output    |
  | Insulation Monitoring Device (+) and (-) Terminals | DC Power        | Output    |

  **Low Voltage Connections**
  | Connection                                         | Connection Type | Direction |
  |----------------------------------------------------|-----------------|-----------|
  | Shutdown Circuit (+) and (-)             	     | DC Power        | Input     |

# Buildable Schematic


# BOM



| **Description**                                | **Quantity** | **Unit Cost** | **Total** | **Assigned Team Member**              |
|------------------------------------------------|--------------|---------------|-----------|---------------------------------------|
| Zero FX                |              |               | **$1,600.40** |                                       |
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




# References
1. Formula SAE, “Formula SAE Rules 2024 Version 1.0”, fsaeonline.com, <https://www.fsaeonline.com/cdsweb/gen/DownloadDocument.aspx?DocumentID=369d01c0-589d-4ebe-b8d4-b07544f4a52b> (accessed Oct 22, 2024)
2. Kollmorgen, "FPGA-Based Sin/Cos Encoder Processing," Kollmorgen Developer Network, Accessed: Oct. 23, 2024. <https://www.kollmorgen.com/en-us/developer-network/fpga-based-sin-cos-encoder-processing>
3. linearmotiontips, "What are the differences between incremental and sine-cosine encoders?" linearmotiontips.com, Accessed: Oct. 26, 2024. <https://www.linearmotiontips.com/differences-between-incremental-and-sine-cosine-encoders/>
4. Zero Motorcycles, "Zero Motorcycles FXE", zeromotorcycles.com, Accessed: Oct. 26, 2024. <https://zeromotorcycles.com/model/zero-fxe>
