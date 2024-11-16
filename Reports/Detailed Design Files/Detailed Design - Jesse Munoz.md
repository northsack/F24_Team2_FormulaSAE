
_Formula SAE Electric Vehicle Detailed Design_

Jesse Munoz  
Tennessee Technological University, ECE Department  
Tennessee Tech Motorsports  
Cookeville, TN, USA  
[jdmunoz42@tntech.edu](mailto:jdmunoz42@tntech.edu)

## Function of the Subsystem - Shutdown Circuit/Brake System Plausibility Device (BSPD)
The function of the BSPD subsystem is open the vehicle's shutdown circuit when a open or short circuit is detected in the input sensors or when two condidtions true, for 0.5 seconds [1]. The BSPD will be placed in series with the other components of the vehicle's shutdown circuit [1].

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
   2. The BSPD shall open the shutdown circuit when both of the following conditions are met for a minimun of 0.5 seconds:
       - When the driver has pressed the brakes far enough.
       - When the motor/accumulator current is at a level so that the motor's DC circuit is at or above 5 kW.
     
  This figure from the Formula SAE Rulebook [1] shows how the shutdown circuit is connected: 
![Figure 1: Shutdown Circuit of a Formula SAE EV Car](https://github.com/northsack/F24_Team2_FormulaSAE/blob/main/Documentation/Images/Fig.%201%20shutdown%20circuit.png)\
Figure 1: Shutdown Circuit of a Formula SAE EV Car

#### BSPD System Constraints:
    

## Overview of Proposed Solution
There are mainly two possible solutions to the problem this subsystem aims to solve for. The first possible solution is to the design, from scratch, an original BSPD, and the second solution is to find and purchase a BSPD module.  
The benefits of the first option is that the BSPD would be developed to fit our vehicle perfectly, however the disadvantage of this solution would be take much more time, and would be difficult to change, if an unexpected change is necceassary. 
The benefits of the second option is that the BSPD module is a complete and ready made device, and it is also known that other teams in the Formula SAE competition are successful in their use of a premade BSPD module. The disadvatages of this solution is that more research is needed to confirm the premade BSPD module fits the specs set by the Formula SAE competition as well as integrating a premade device into the rest of the project.  
For this subsystem purchaceing a premade BSPD module would be the simplest solution. Integrating a premade module would be a much more time efficient soultion compared to designing a new one.

The current selection for a premade BSPD module says that it is made to comply with current Formula SAE [2]. The specifications of the module, stated in its datasheet, seems to match witht he current Formula SAE EV competetion rules and contraints [3].

## Interface with Other Subsystems
**Shutdown Circuit:**  
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

**Brake System Plausibility Device (BSPD):**  
The BSPD is a component in the shutdown circuit and is one of the more complex pieces of the circuit.

- *Interface with other subsystems:*

    **Low Voltage Connections**
    | Connection                                         | Connection Type | Direction |
    |----------------------------------------------------|-----------------|-----------|
    | GVL (+)         			 | DC Power        | Input     |
    | Brake Presure Sensor        			 | Analog        | Input     |
    | Current Sensor         			 | Analog        | Input     |
    | GVL (-)         			 | DC Power        | Output     |

## Bill of Materials (BOM)       **(IN PROGRESS)**
| Item                            | Price    |   
|---------------------------------|----------|
| BSPD FSAE 2025/2024 - EV ONLY   |          |
| HO 200-S-0100	 (current Sensor) |          |
|           			          |          |
|           			          |          |
    
## Analysis

## References
1. Formula SAE, “Formula SAE Rules 2024 Version 1.0”, fsaeonline.com, <https://www.fsaeonline.com/cdsweb/gen/DownloadDocument.aspx?DocumentID=369d01c0-589d-4ebe-b8d4-b07544f4a52b> (accessed Nov 15, 2024)
2. Q-tronic Engineering, "BSPD FSAE 2025/2024 - EV ONLY", ebay.com, <https://www.ebay.com/itm/266497060229?_trksid=p2332490.c101224.m-1> (accessed Nov 15, 2024)
3. Q-tronic Engineering, "BSPD FSAE 2021-22 Datasheet:, (accessed Nov 15, 2024)
