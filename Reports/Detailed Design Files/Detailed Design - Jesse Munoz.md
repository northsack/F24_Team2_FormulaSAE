_Formula SAE Electric Vehicle Detailed Design_

Jesse Munoz  
Tennessee Technological University, ECE Department  
Tennessee Tech Motorsports  
Cookeville, TN, USA  
[jdmunoz42@tntech.edu](mailto:jdmunoz42@tntech.edu)

## Function of the Subsystem - Shutdown Circuit/Brake System Plausibility Device (BSPD)
The function of the BSPD subsystem is open the vehicle's shutdown circuit when a open or short circuit is detected in the input sensors, or when two shutdown conditions are true, for 0.5 seconds [1]. These shutdown conditions will be discussed in more detail in their own section. The BSPD will be placed in series with the other components of the vehicle's shutdown circuit [1].

## Specifications and Constraints
#### Shutdown System Specifications:
The shutdown system consists of the following components connected in series. The purpose of this systems is to ensure the safety of the driver, team members in the near viscinity of the vehicle, and the vehicle itself. If one of these safety systems encounters a fault, the system has the ability to shut down all power to the vehicle. Each safety system is daisy chained to the previous/next safety system. Thus, if one system disengages power, none of the main components on the vehicle will be powered. The system shall only function when all contacts of the safety system are closed:
    1. Accumulator Management System
    2. Insulation Monitoring Device
    3. Brake System Plausibility Device (BSPD)
    4. Interlocks
    5. Master Switches
    6. Shutdown Buttons
    7. Brake Over Travel Switch (BOTS)
    8. Inertia Switch 
#### BSPD System Specifications:  
   The BSPD shall comply with all rules and regulations specified in the Formula SAE rule book [1]. The specifications for this subsystems are listed below:
   1. The BSPD shall open the shutdown circuit when one or more of the input sensors has an open or short circuit.
   2. The BSPD shall open the shutdown circuit when both of the following shutdown conditions are met for a minimun of 0.1 seconds:
       - When the driver has pressed the brake pedal to or passed 50% [1].
       - When the motor/accumulator current is at a level so that the motor's DC circuit is at or above 5 kW [1].
     
  This figure from the Formula SAE Rulebook [1] shows how the shutdown circuit is connected: 
![Figure 1: Shutdown Circuit of a Formula SAE EV Car](https://github.com/northsack/F24_Team2_FormulaSAE/blob/main/Documentation/Images/Fig.%201%20shutdown%20circuit.png)\
Figure 1: Shutdown Circuit of a Formula SAE EV Car

#### BSPD System Constraints:
 - The BSPD shall have a 0.5 sec delay after the two shutdown conditions are met. These 2 shutdown conditions are described in the "BSPD System Specifications" section. This debouncing is to prevent the BSPD from opening the shutdown circuit in the event of a very short current spike or signal spike in the APPS.
 - The BSPD shall only open the shutdown circuit after both shutdown condidtions are true for 0.1 sec.
 - The brake pressure sensor shall send an analog signal to the BSPD when demanding hard braking. This may be a voltage signal ≥ 4.5 V.

## Overview of Proposed Solution
There are mainly two possible solutions to the problem this subsystem aims to solve for. The first possible solution is to the design, from scratch, an original BSPD, and the second solution is to find and purchase a BSPD module.  
The benefits of the first option is that the BSPD would be developed to fit our vehicle perfectly, however the disadvantage of this solution would be take much more time, and would be difficult to change, if an unexpected change is necceassary. 
The benefits of the second option is that the BSPD module is a complete and ready made device, and it is also known that other teams in the Formula SAE competition are successful in their use of a premade BSPD module. The disadvatages of this solution is that more research is needed to confirm the premade BSPD module fits the specs set by the Formula SAE competition as well as integrating a premade device into the rest of the project.  
For this subsystem purchaceing a premade BSPD module would be the simplest solution. Integrating a premade module would be a much more time efficient soultion compared to designing a new one.

The current selection for a premade BSPD module says that it is made to comply with current Formula SAE [2]. The specifications of the module, stated in its datasheet, seems to match witht he current Formula SAE EV competetion rules and contraints [3].

## Interface with Other Subsystems
**Shutdown Circuit:**  
The shutdown circuit is mostly made up of components that can be purchased and connected to the circuit. However, some components are more involved and require a more detailed description. One of these components is the Brake System Plausibility Device (BSPD).

- *Interface with other subsystems:*

  **High Voltage Connections**

  | Connection     | Connection Type | Direction |
  |----------------|-----------------|-----------|
  | IMD            | DC Power        | Output    |

   <br>**Low Voltage Connections**
    | Connection                                         | Connection Type | Direction |
    |----------------------------------------------------|-----------------|-----------|
    | GVL (+)         			 | DC Power        | Input     |
    | GVL (-)         			 | DC Power        | Output    |

    - The high voltage IMD connection will output the GLV current. The GVL current is the current in the Grounded Low Voltage circuit. As long as the IMD does not detect a fault in it's high voltage connections it will continue to flow the DC current through the shutdown circuit.  
    - The shutdown circuit's low voltage connections will be the power supply for the GLV system.

**Brake System Plausibility Device (BSPD):**  
The BSPD is a component in the shutdown circuit and is one of the more complex pieces of the circuit.

- *Interface with other subsystems:*

    **Low Voltage Connections**
    | Connection                 | Connection Type | Direction |
    |----------------------------|-----------------|-----------|
    | GVL (+)         			 | DC Power        | Input     |
    | Brake Presure Sensor       | Analog          | Input     |
    | Current Sensor         	 | Analog          | Input     |
    | GVL (-)         			 | DC Power        | Output    |

    - The BSPD will have three inputs, as shown in the table above. The first will be the the GLV system's DC power signal. This is the current that opens and closes the shutdown circuit. If this current flow is stopped then the shutdown circuit is opened and the high voltage power supply will be cut off.
    - The second input is the brake pressure sensor, this sensor tells the BSPD, though the current/voltage value, if the brake pedal is presses with enough pressure.
    - The third sensor is the current sensor. This sensor will detect the current from motor/accumulator subsystems, and needs to be able to fit a wire with an 8.2 mm diameter. It will detect the current value and send that signal to the BSPD which will then determine if the motor/accumulator subsystems' power usage is ≥ 5 kW.
    - The BSPD will have one output and that is the GLV DC power signal. As long as the BSPD does not detect the 2 shutdown conditions, as described in the BSPD specs, for 100 ms, the GLV current will flow thus keeping the shutdown circuit closed.

## Buildable Schematic
![Figure 2: Vhehicle Diagram](https://github.com/northsack/F24_Team2_FormulaSAE/blob/detailed_design/Documentation/Images/overall-vehicle-diagram.PNG)\
Figure 2: Vhehicle Diagram

## Bill of Materials (BOM)
| Item                               | Manufacteror       | Part Number           | Distributor  | Distributor part number  | Quantity  | Price    |
|------------------------------------|--------------------|-----------------------|--------------|--------------------------|-----------|----------|
| 1. BSPD FSAE 2025/2024 - EV ONLY   | Qtronic Engineering| BSPD FSAE 2021-2 v0.5 | Ebay         | 266497060229             | 1         | $200.00  |
| 2. Current Sensor                  | LEM                | HO 200-S-0100         | Newark       | 64AH3657                 | 1         | $60.00   |
| 3. 150 Psi Pressure Transducer     | AUTEX              | GSND-0556629788       | Amazon       | B00NIK98O8               | 1         | $50.00   |
|    **Total**          			 |                    |                       |              |                          |           | $310.00  |

URLs for items in the same order as they appear:
1. <https://www.ebay.com/itm/266497060229?_trksid=p4481478.c101506.m1851>
2. <https://www.newark.com/lem/hoys-200-s-0100/current-sensor-voltage-500a-to/dp/64AH3657>
3. <https://www.amazon.com/AUTEX-Pressure-Transducer-Stainless-Compatible/dp/B00NIK98O8/ref=asc_df_B00NIK98O8>
    
## Analysis
Overall the shutdown circuit is a circuit of constant checks of the different subsystems of the car. As long as each of the subsystems in the car function as intended and no sensors have any faults or short circuits, the shutdown circuit will continue to remain closed thus keeping the high voltage power supply connected to the motor. As long as each of the components of the shutdown circuit fit their own specifications and constraints, and the GLV power supplies enough energy to power these components, there should be no issue that this solution should not work.

By checking the proposed BSPD's pinout in its datasheet, it has 6 pins [3]. Pin one is the Vcc input for the module. Pin 2 shall be the GLV(+) input, this is the shutdown circuit power signal. Pin 3 is the output GLV(-), if the BSPD shutdown conditions are met for the specified time of 100 ms, then this pin will not conduct thus opening the shutdown circuit. Pin 4 is the brake pressure sensor, this is the pin that tells the BSPD if there is a demand for hard braking. Demand for hard braking will be determined by the voltage/current of the PSI Pressure Transducer, if its voltage raises or lowers out of the range of 0.5 V < V < 4.5 V, then there is either a short circuit or a demand for hard braking is present. The pressure sensor will be connected to the brake pedal with some tubing, and when the brake pedal is pressed it will increase the pressure applied to the sensor. Pin 5 is the current sensor, much like the brake pressure sensor, it will detect if the current the motor is pulling is enough to make the power ≥ 5 kW. If this is true then that means the car is moving at a higher speed, this also makes one of the shutdown conditions true. Pin 6 is the ground pin of the BSPD module [3]. Since this information comes from the datasheet then it means that this pre-made BSPD module will meet the desired specifications and constraints set by Formula SAE.

## References
1. Formula SAE, “Formula SAE Rules 2024 Version 1.0”, fsaeonline.com, <https://www.fsaeonline.com/cdsweb/gen/DownloadDocument.aspx?DocumentID=369d01c0-589d-4ebe-b8d4-b07544f4a52b> (accessed Nov 15, 2024)
2. Q-tronic Engineering, "BSPD FSAE 2025/2024 - EV ONLY", ebay.com, <https://www.ebay.com/itm/266497060229?_trksid=p2332490.c101224.m-1> (accessed Nov 15, 2024)
3. Q-tronic Engineering, "BSPD FSAE 2021-22 Datasheet:, (accessed Nov 15, 2024)
4. AUTEX, "150 Psi Pressure Transducer", Amazon.com, <https://www.amazon.com/AUTEX-Pressure-Transducer-Stainless-Compatible/dp/B00NIK98O8/ref=asc_df_B00NIK98O8> (accessed Nov 18, 2024)
5. LEM, "Current Transducer HO-S series Datasheet", (accessed Nov 19, 2024)
6. Wiscinsin Formula SAE Racing, "Electrical System Form FSAE-E2018", wisconsinracing.org, <https://www.wisconsinracing.org/wp-content/uploads/2020/10/2018_ESF_Submission.pdf> (accessed Nov 21, 2024)
