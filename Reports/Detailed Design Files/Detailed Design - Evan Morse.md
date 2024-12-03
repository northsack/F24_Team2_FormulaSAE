
_Formula SAE Electric Vehicle Conceptual Design_

Evan Morse  
Tennessee Technological University, ECE Department  
Tennessee Tech Motorsports  
Cookeville, TN, USA  
[emorse42@tntech.edu](mailto:emorse42@tntech.edu)


# Function of the Subsystem

The Accumulator (Battery) subsystem is responsible for safely storing and providing high voltage DC power to the motor controller of the Formula SAE Electric vehicle.  The Accumulator is an enclosed container that houses battery cells, isolation relays (AIRs), temperature sensors, voltage sensors, precharge circuits, discharge circuits, and a battery managemeny system (BMS).  Externally, two terminals provide the high voltage power for the motor controller, three low voltage terminals connected to the shutdown circuit and low voltage battery are used to control the AIRs, and finally, a voltage indicator LED turns on when high voltage is present at the output terminals.


# Specifications and Constraints

- #### Specifications
   
	1. Accumulator Isolation Relays:  
		Relays shall be used inside of the Accumulator container to control the power provided to the external connectors of the Accumulator.  Power shall only be provided to the external terminals when the Shutdown Circuit is closed (vehicle is ready to drive).  The AIRs shall be used to control both the positive and negative terminals of the Accumulator. The AIRs shall be normally open.
	2. Precharge Circuit:  
		As part of the motor controller's design, capacitors are installed at the main high voltage terminals.  When the Accumulator Isolation Relays (AIRs) are closed (High Voltage (HV) power is turned on), and power is provided to the motor controller.  Without a Precharge Circuit, thousands of Amps can flow through the wires to charge the capacitors inside the motor controller when the AIRs close.  This can be dangerous because it can prematurely wear the AIRs, and possibly even weld the terminals of the AIRs together, preventing proper operation.  To prevent this, the Accumulator shall have a system designed to precharge the HV system to 90% of the current Accumulator voltage before closing the AIRs.      
	3. Discharge Circuit:  
		The accumulator shall contain a circuit that can discharge the same capacitors mentioned in statement **ii** above.  When the shutdown circuit is open (vehicle is shutting down), the AIRs shall open, and the Discharge Circuit shall safely discharge the capacitors inside of the motor controller.
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
    
    1. The voltage and current draw of the motor.  [100 V & 120 Amps Continuous, 300 Amps Burst]
    2. The duration of operation of the motor.  [40 minutes]
   
	The final battery cell arrangement for the Accumulator shall be 28s4p.  Farasis 29Ah 3.65V Lithium Polymer batteries will be used as the battery cells.

2. Precharge & Discharge Circuits  
	The precharge and discharge circuits will be circuits located inside of the Accumulator container.  The precharge and discharge circuits will take high voltage inputs from the output of the battery cells inside the accumulator, and the voltage across the motor controller.  Digital logic and a seperate relay to send current through a resistor shall be used to slowly charge the capacitors in the motor controller to at least 90% of the Accumulator's voltage.  
    
3. Battery Management System  
	The Battery Mangement System consists of temperature and voltage sensors inside of the Accumulator container.  If the voltage of the battery cells does not meet the normal operating range, the battery management system will turn off the AIRs to prevent the Accumulator from being discharged/overcharged.  Likewise, if the temperature of the accumulator does not meet the normal operating range, the BMS will turn off the AIRs.
    
    The BMS sensors will be controlled with a low power microcontroller that programmed to periodically wake up and check the values of the sensors.

# Interface with Other Subsystems

The Accumulator will have the following connections to other subsystems in the electric vehicle.  
  
  **High Voltage Connections**
  
  In order to power the high voltage components of the Electric vehicle, the Accumulator will output high voltage to the following systems.
  | Connection                                         | Connection Type | Direction |
  |----------------------------------------------------|-----------------|-----------|
  | Motor Controller (+) and (-) Terminals             | DC Power        | Output    |
  | Insulation Monitoring Device (+) and (-) Terminals | DC Power        | Output    |

  
  
 **Low Voltage Connections**
 
 The following low voltage connections are required for the Accumulator to control itself.  The Shutdown Circuit controls whether the Accumulator provides high voltage power at the output terminals, and the Low Voltage Battery connection supplies the required power to control the internal microcontroller and relays.
 | Connection                                         | Connection Type | Direction |
  |----------------------------------------------------|-----------------|-----------|
  | Shutdown Circuit (+) and (-)             	     | DC Power        | Input     |
  | 12 V Low Voltage Battery (+) and (-)				| DC Power 		 | Input 	|
  | Motor Controller Ready (+) and (-)               | DC Power         | Output    |
# Buildable Schematic
![Figure 1: Overall Schematic of Vehicle](https://github.com/northsack/F24_Team2_FormulaSAE/blob/detailed_design/Documentation/Images/overall-vehicle-diagram.PNG)
![Figure 2: Buildable Schematic of Accumulator](https://github.com/northsack/F24_Team2_FormulaSAE/blob/Evan-Morse--DD/Documentation/Images/Buildable-Schematic-Evan.PNG)

# BOM

| Component             | Manufacturer   | Part Number      | Distributor | Distributor Part #      | Quantity | Price  | URL                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| --------------------- | -------------- | ---------------- | ----------- | ----------------------- | -------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Battery Cells         | Farasis        | 60160230         | Alibaba     | ####                    | 112      | $14.50   | https://www.alibaba.com/product-detail/Farasis-Prismatic-Rechargeable-Ultra-Thin-Lithium_62473567947.html                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Q1, Q2, Q3, Q4 (Transistors)       | onsemi         | TIP122           | Amazon      | B0CBKHTF9Z              | 1        | $8.99  | [https://www.amazon.com/ALLECIN-TIP122-Darlington-Transistor-Transistors/dp/B0CBKHTF9Z?dib=eyJ2IjoiMSJ9.h3c-xIy3MyTNjNTX3uCVtRncMGsMHjaKeTqh1-8ZQN2GaInGdv6KozpXRd5nZVJNOPgiOhSRMMZ3okbZTwFnY9nirRAOiN8g-0SOUXSu-Lk5dk4uh-kKCB-1MdaJsiRep4_-_ayYb-DQ4QF-cuxOH5FG7Z687LuZhnIQQZxkC8EJjWEVB55LhyVNK-Vh5JSSKY80nMxgyLUdfh8IP_1dYw46OF7kOLGvdrbK8O36h2k.fBX-gdyq_e9Lp2Pc58ckj_bTbTS5j_WYXSlCoZGbC6Q&dib_tag=se&keywords=TIP122&qid=1733194417&sr=8-3&th=1](https://www.amazon.com/ALLECIN-TIP122-Darlington-Transistor-Transistors/dp/B0CBKHTF9Z?dib=eyJ2IjoiMSJ9.h3c-xIy3MyTNjNTX3uCVtRncMGsMHjaKeTqh1-8ZQN2GaInGdv6KozpXRd5nZVJNOPgiOhSRMMZ3okbZTwFnY9nirRAOiN8g-0SOUXSu-Lk5dk4uh-kKCB-1MdaJsiRep4_-_ayYb-DQ4QF-cuxOH5FG7Z687LuZhnIQQZxkC8EJjWEVB55LhyVNK-Vh5JSSKY80nMxgyLUdfh8IP_1dYw46OF7kOLGvdrbK8O36h2k.fBX-gdyq_e9Lp2Pc58ckj_bTbTS5j_WYXSlCoZGbC6Q&dib_tag=se&keywords=TIP122&qid=1733194417&sr=8-3&th=1)                                                                         |
| K1, K2, K3, K4 (Relays)         | TE Connectivity / Kilovac | EV200AAANA     | Mouser      | 655-EV200AAANA        | 4        | $189.73  | https://www.mouser.com/ProductDetail/TE-Connectivity-Kilovac/EV200AAANA?qs=tpWFTnCUDEKGgTXTYtpAEg%3D%3D                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Arduino Nano          | Arduino        | ARD_A000005      | Amazon      | B07VX7MX27              | 1        | $17.95 | [https://www.amazon.com/Arduino-Nano-Every-Single-Board/dp/B07VX7MX27?crid=1LTHRM3UGK3U8&dib=eyJ2IjoiMSJ9.6QPRL9EGieCqVheJYNSvYLiNSaIKqAuyrl-iTXMnEEHYFiJQrWrv8ahaguyc8bG-NeOkg0eyTdYLProro4RyuP80w9jiGMb8jRXz6B9xBl3jx5ZzqxCvvDYRim6hrz_xRwVB6dOBms27Ejk3AvgLyzIm1D7wNhyg1zS0eUeXl3A7_JnFb7XSaPUJuODuozBnj8OcWCBIXTN6dFRPu4zwrxOXV0yxlRo0imHxENLkwGQ.SCHLFaFGCGWRKENxoprbb_u7VFxuCl7UB13y59WNYsI&dib_tag=se&keywords=arduino+nano&qid=1733195801&sprefix=arduino+nano%2Caps%2C142&sr=8-8](https://www.amazon.com/Arduino-Nano-Every-Single-Board/dp/B07VX7MX27?crid=1LTHRM3UGK3U8&dib=eyJ2IjoiMSJ9.6QPRL9EGieCqVheJYNSvYLiNSaIKqAuyrl-iTXMnEEHYFiJQrWrv8ahaguyc8bG-NeOkg0eyTdYLProro4RyuP80w9jiGMb8jRXz6B9xBl3jx5ZzqxCvvDYRim6hrz_xRwVB6dOBms27Ejk3AvgLyzIm1D7wNhyg1zS0eUeXl3A7_JnFb7XSaPUJuODuozBnj8OcWCBIXTN6dFRPu4zwrxOXV0yxlRo0imHxENLkwGQ.SCHLFaFGCGWRKENxoprbb_u7VFxuCl7UB13y59WNYsI&dib_tag=se&keywords=arduino+nano&qid=1733195801&sprefix=arduino+nano%2Caps%2C142&sr=8-8) |
| 12 V to 5 V Converter | EVVO           | XL1509-5.0-EV    | Amazon      | 5272-XL1509-5.0-EVTR-ND | 1        | $1.20  | https://www.digikey.com/en/products/detail/evvo/XL1509-5-0-EV/24370105                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| R1, R2                | uxcell         | a18041900ux0121  | Amazon      | B07FDXPT9Y              | 1        | $9.99  | https://www.amazon.com/uxcell-Aluminum-Resistor-Wirewound-Resistors/dp/B07FDXPT9Y?crid=SU42UCI7WKUG&dib=eyJ2IjoiMSJ9.BvhEZmsMvIku6qpTr0hBuuIamWlkULPzcKUmtskqhG_PxXVcyvpYMYBHG6hgMVkw0XW1jDBrNwcjocXNtaPpJHPcrTk3W3f8QopGz-eVuIBWQn3OSOuQ9MtX0IalSSvBR8gwm_zKJwwBx8_3SwpWGz_N4bKHDGAw52bFXuJDsiuv6H6G7f1PFunyngil0q__E24Zsc6_DdlHPCn_pGDXv-TqXc7lem-_b6itaoKLD04.Y95WjLdYuQzL4HEHlbbTEJR9c0YZEWBEmqPMREl5Sm0&dib_tag=se&keywords=uxcell+50w+400+ohm&qid=1733194969&sprefix=uxcell+50w+400+ohm%2Caps%2C109&sr=8-1                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| R4, R8                | EDGELEC        | EFR-W1D00-A:MF   | Amazon      | B07WHQMDTV              | 1        | $6.99  | https://www.amazon.com/EDGELEC-Resistor-Tolerance-Multiple-Resistance/dp/B07WHQMDTV/142-1492945-6536653?pd_rd_w=SNsmE&content-id=amzn1.sym.751acc83-5c05-42d0-a15e-303622651e1e&pf_rd_p=751acc83-5c05-42d0-a15e-303622651e1e&pf_rd_r=KYN7SDGTDDS20W3KG5VX&pd_rd_wg=KfKNZ&pd_rd_r=3c300556-6d7a-4598-b5aa-960adf82a5b2&pd_rd_i=B07WGMZQ5F&th=1                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| R5                    | EDGELEC        | ‎ EFR-W1D00-A:MF | Amazon      | B07WGN2L95              | 1        | $6.99  | https://www.amazon.com/EDGELEC-Resistor-Tolerance-Multiple-Resistance/dp/B07WGN2L95/142-1492945-6536653?pd_rd_w=SNsmE&content-id=amzn1.sym.751acc83-5c05-42d0-a15e-303622651e1e&pf_rd_p=751acc83-5c05-42d0-a15e-303622651e1e&pf_rd_r=KYN7SDGTDDS20W3KG5VX&pd_rd_wg=KfKNZ&pd_rd_r=3c300556-6d7a-4598-b5aa-960adf82a5b2&pd_rd_i=B07WGMZQ5F&th=1                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| R6                    | EDGELEC        | EFR-W1D00-A:MF   | Amazon      | ‎B07WHQLPLQ             | 1        | $6.99  | https://www.amazon.com/EDGELEC-Resistor-Tolerance-Multiple-Resistance/dp/B07WHQLPLQ/142-1492945-6536653?pd_rd_w=SNsmE&content-id=amzn1.sym.751acc83-5c05-42d0-a15e-303622651e1e&pf_rd_p=751acc83-5c05-42d0-a15e-303622651e1e&pf_rd_r=KYN7SDGTDDS20W3KG5VX&pd_rd_wg=KfKNZ&pd_rd_r=3c300556-6d7a-4598-b5aa-960adf82a5b2&pd_rd_i=B07WGMZQ5F&th=1                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| R3, R7                | EDGELEC        | EFR-W1D00-A:MF   | Amazon      | B07WGMZQ5F              | 1        | $6.99  | https://www.amazon.com/EDGELEC-Resistor-Tolerance-Multiple-Resistance/dp/B07WGMZQ5F/142-1492945-6536653?pd_rd_w=SNsmE&content-id=amzn1.sym.751acc83-5c05-42d0-a15e-303622651e1e&pf_rd_p=751acc83-5c05-42d0-a15e-303622651e1e&pf_rd_r=KYN7SDGTDDS20W3KG5VX&pd_rd_wg=KfKNZ&pd_rd_r=3c300556-6d7a-4598-b5aa-960adf82a5b2&pd_rd_i=B07WGMZQ5F&th=1                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |

Total Cost: $2499                                 

# Analysis
### Battery Cells  
##### Requirements:

The first step of designing the optimized battery cell structure is to determine the required power and run time of the battery.  For the Formula SAE Electric competition, the longest event is the Endurance event which can take teams 30-45 minutes to complete.  Thus the battery needs to be designed to run for at least 45 minutes.

The second step for designing a battery is to determine the voltage and current that the battery needs to supply.  The Sevcon Gen 4 controller that will be used in the FSAE Electric vehicle requires 48-150 V, and it's nominal voltage rating is 110 V.  For this battery, the nominal voltage will be 102 V.  The maximum voltage will be 116 V.  The continuous current draw from the Sevcon Gen 4 controller is 120 A, and the burst (10 Second) current draw is 300 Amps.  Thus the power requirements for the batteries are:

| Battery Run Time | Motor Controller Voltage Range| Motor Controller Current Consumption             |
|------------------|-----------------|------------------------------|
| 45 Minutes       | (48V - 150V)    | 120 Amps Continuous, 300 Amps Burst |

##### Battery Cell Specifications
Off the shelf battery cells will be used for this accumulator.  These cells are documented well, cost effective, and proven to be reliable.  The specific cells that will be used for this project are Farasis 29Ah 3.65V Lithium Polymer batteries.

| Max Voltage  | Nominal Voltage | Max Discharge Current  | Continuous Discharge Current | Ah Rating |
|--------------|-----------------|------------------------|------------------------------|------|
| 4.25 V       | 3.65 V          | 174 Amps               | 87 Amps                      | 29 Ah|

##### Battery Cell Arrangement Calculations
In order to build an Accumulator to power this vehicle, the battery cells must be arranged to provide the required voltage, current, and run time.  When the battery cells are arranged in series the battery cells in series' voltage is added, thus increasing the overall battery output voltage.  Installing the battery cells in parallel increases the current capacity of the Accumulator, as well as increasing the run time of the Accumulator.

###### Series Calculation

In order to provide a nominal 102 V, the number of cells in series must be calculated.  

		Series Battery Cells = 102 V (Battery Voltage) / 3.65 V (Individual Cell Voltage)
        Series Battery Cells = 27.95
        Series Battery Cells = 28

The maximum voltage of the Accumulator with **28 cells** in series will be

		Max Voltage = 28 (# of Cells) * 4.25 V (Maximum Cell Voltage)
        Max Voltage = 119 V
        
From this calculation, the maximum voltage falls within range of the motor controller's specification.

Finally, the minimum voltage value will be calculated

		Minimum Voltage = 28 (# of Cells) * 2.75 V (Minimum Cell Voltage)
        Minumum Voltage = 77 V
From this calculation, the minimum voltage falls within range of the motor controller's specification.  

All of these voltages also are legal under the FSAE Rulebook.  No voltage greater than 600 V DC is present in the Accumulator.

###### Parallel Calculation

In order to deliver the required current and desired runtime, battery cells must be placed in parallel.  The available current is added for each parallel segement.  The number of parallel cells can be calculated as follows:
		
        Parallel Battery Cells = 300 (Max Motor Burst Current) / 174 (Max Battery Cell Burst Current)
        Parallel Battery Cells = 1.72
        Parallel Battery Cells = 2
        
Thus, based on maximum burst current, the required parallel cells are two.

The last calculation that effects parallel cells is the desired run time.  The run time needs to be 45 minutes.
		
        Parallel Battery Cells = [0.75 (Desired Run Time in Hours) * 120 Amps (Motor Controller Constant Current)] / 29 Ah (Individual Cell aH)
        Parallel Battery Cells = 3.10
        Parallel Battery Cells = 4
		
        Run Time of 4 Battery Cells in Parallel = 4 (# of Parallel Cells) * 29 aH (Individual Cell aH) / 120 Amps
        Run Time of 4 Battery Cells in Parallel = 0.96 Hours = 58 Minutes
  
Based off of this calculation, the battery needs four parallel runs of batteries.

##### Summary
From the calculations of the load and run time, the Accumulator's battery cell structure will be 28 cells in series in 4 parallel runs (28s4p).

### Precharge and Discharge Circuits

When the shutdown circuit is closed, the Accumulator will begin precharging the capacitors inside the motor controller.  Once the capacitors have been precharged, then the Accumulator will turn off the precharge circuit by opening the precharge relay, and then the Accumulator will close the AIR relays to provide full high voltage power to the external terminals.

###### Relays

In order to provide power to the external terminals of the Accumulator, Accumulator Isolation Relays (AIRs) must be used.  The AIRs that will be used for this vehicle are KILOVAC EV200 AAANA. These relays are normally open, have 12 V controlled coils, are rated for voltages within the range of 12-900 Volts, and meet all rules specifications for the FSAE Electric competition.  

###### Microcontroller Behavior
To operate the internal relays and monitor the motor controller voltage, an Arduino Nano microcontroller will be used inside of the Accumulator.  The Arduino Nano will use digital outputs to control transistors to operate the relays for precharging, discharging, and normal operation, as well as signal to the motor controller when it is safe to operate the motor.  The Arduino Nano will also use an analogue input to monitor the voltage of the motor controller.  This analogue input will act as the feedback in the precharge system. 

The microcontroller must be able to communicate with the motor controller to prevent the motor from running when the precharge circuit is in operation.  If the motor starts while precharging, the precharge resistor will be destroyed by the amount of power the motor will pull.

A voltage divider circuit is necessary to step down the voltage across the motor controller from the range of 120 V to 77 V to a 0-5 V range so that the microcontroller can monitor the voltage of the motor controller.  Once the microcontroller observes that the monitored voltage is at least 90% of the Accumulator voltage, then the microcontroller can turn off the precharge circuit.

Transistors are necessary because the Arduino's digital outputs are only 5 Volts, but the relay coils for the Accumulator require 12 Volts.  Thus the 5 Volt digital output of the Arduino will not be sufficient to control these relays.  Each output of the microcontroller is connected to the base of a BJT NpN transistor.  The Emitter of the BJT is connected to the relay, and the Collector of the BJT is connected to the 12 Volt supply.

The operations of the microcontroller are as follows:

1. Shutdown Circuit open ---> closed (Car is ready to drive):
	1. Microcontroller will open the discharge circuit relay, and will close the precharge relay which will begin charging the capacitors
	2. Microcontroller will monitor the voltage across the motor controller
	3. Once the monitored voltage is greater than or equal to 90 % of the Accumulator's current voltage, the microcontroller will open the precharge relay and close the + and - terminal AIRs.  The microcontroller will also provide power across the Motor Controller Ready terminals.  As an example, if the Accumulator's voltage is 102 V, this precharge circuit would charge the capacitors to 92 V before closing the AIRs and powering the Motor Controller Ready terminals.  
	
2. Shutdown Circuit closed ---> open (Car needs to stop):
	1. Microcontroller will keep the - terminal AIR closed, but will open the + terminal AIR as well as close the discharge relay.

###### Precharge Circuit Design
After programming the microcontroller, the precharge circuit must be designed.  The precharge circuit is an RC circuit that consists of a resistor in series with the motor controller capacitors.  The resistor will provide a small current to slowly charge the capacitors of the motor controller to 90% of the Accumulator voltage (As per mandated in the FSAE Rulebook.)  The main design objective for this circuit to determine what size resistor is required for the precharge circuit.  To find the resistance value, the capacitance of the motor controller capacitors must be known.  The capacitors for the Sevcon Gen 4 controller are 2400 microFarads.  Since the nominal battery voltage is 102 V, an RC circuit can be designed to slowly charge the motor controller capacitors.

![Figure 3: LTSpice simulation of Precharge Circuit](https://github.com/northsack/F24_Team2_FormulaSAE/blob/detailed_design/Documentation/Images/Precharge.PNG)

From this LTSpice simulation, it can be observed that with a 400 Ohm resistor, the precharge circuit will charge the motor controller capacitors to 92 Volts (90 % of the Accumulator voltage as mandated in the Formula SAE Rulebook) in roughly 2.3 seconds.  

###### Discharge Circuit Design
Similar to the precharge circuit, the discharge circuit is an RC circuit that is supposed to fully discharge the capacitors inside of the motor controller in 15 seconds.  If the same resistor is used for the discharge circuit as the precharge circuit, the circuit will discharge the capacitors in roughly 5 seconds.  This meets the FSAE Rules, and will safely discharge all high voltage power from the vehicle, so that work can safely be performed.

![Figure 4: LTSpice simulation of Precharge Circuit](https://github.com/northsack/F24_Team2_FormulaSAE/blob/detailed_design/Documentation/Images/Discharge.PNG)

From this LTSpice simulation, it can be observed that it will take roughly 5 second to discharge the capacitors with a 400 Ohm resistor.  This will pass the requirement of discharging within 15 seconds that the FSAE rules mandate.

# References
1. Formula SAE, “Formula SAE Rules 2024 Version 1.0”, fsaeonline.com, <https://www.fsaeonline.com/cdsweb/gen/DownloadDocument.aspx?DocumentID=369d01c0-589d-4ebe-b8d4-b07544f4a52b> (accessed Oct 22, 2024)
2. Tesla500, "Sevcon Gen4 AC motor controller teardown", omeganaught.com, <http://omeganaught.com/2014/05/sevcon-gen4-ac-motor-controller-teardown/> (accessed Nov 17, 2024)
3. Jason Sylvestre, "Electrical System Form FSAE-E2018", wisconsinracing.org, <https://www.wisconsinracing.org/wp-content/uploads/2020/10/2018_ESF_Submission.pdf> (accessed Nov 17, 2024)
4. Wisconsin Racing, "WISCONSIN RACING 223E ELECTRICAL DESIGNS", wisconsinracing.com, <https://www.wisconsinracing.org/wp-content/uploads/2024/05/Release-of-223E-Electrical-Designs.pdf> (accessed Nov 17, 2024)
