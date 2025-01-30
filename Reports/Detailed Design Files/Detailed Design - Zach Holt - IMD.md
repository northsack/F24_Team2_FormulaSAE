
_Formula SAE Electric Vehicle Detailed Design_

Zach Holt
Tennessee Technological University, ECE Department  
Tennessee Tech Motorsports  
Cookeville, TN, USA  
[zsholt42@tntech.edu](mailto:zsholt42@tntech.edu)

## Function of the Subsystem: Shutdown Circuit - Insulation Monitoring Device (IMD)
The function of the IMD inside the shutdown circuit is to detect any possible electrical faults in the high voltage system. It does this by monitoring the insulation resistance between the high voltage system and the ground. It is part of the shutdown circuit, and its purpose is to open the shutdown circuit when any possible faults are detected.

## Specifications and Restraints
As the IMD is a part of the shutdown circuit, it is bound by the rules and regulations specified in the FSAE-EV Rulebook [1]. The rules pertaining to the IMD are as follows:
1. The IMD shall detect insulation resistance below 500 Ohms/Volt of the maximum tractive system voltage and trigger the shutdown circuit accordingly.
2. It shall continuously monitor the isolation resistance between the high-voltage system and the chassis ground during all operational phases.
3. The IMD shall be connected in the shutdown circuit to disable the tractive system if an isolation fault is detected.
4. The IMD shall not rely on programmable logic or software for safety-critical functionality, ensuring it operates independently and reliably.
5. In the event of an IMD failure, the system shall default to a safe state, interrupting the shutdown circuit to disable the vehicle.


## Overview of Proposed Solution
The proposed solution is to purchase an IMD and integrate it within our vehicle. The IMD we have chosen can be purchased online from Bender [2]. This solution makes sense for our project as buying the part is a complete solution. The part is approved and recommended by the Formula SAE rulebook.

## Interface With Other Subsystems
The IMD is part of the shutdown circuit. It is connected in series with the inertia switch and the Brake System Plausibility Device. The input will come from the Inertia Switch, and the output will go to the BSPD.

**BOTS Connections**

| Connection  | Connection Type | Direction |
|-----------|-----------------|-----------|
| HV (+)  | DC Power        | Input     |
| HV (-)   | DC Power        | Input    |
| Pin 1  | Ground        | Input     |
| Pin 2  | LV Battery      | Input    |
| Pin 3  | Ground       | Input    |
| Pin 4  | Ground        | Input     |
| Pin 8  | Status Signal      | Output    |

![](https://github.com/northsack/F24_Team2_FormulaSAE/blob/detailed_design/Documentation/Images/overall-vehicle-diagram.PNG)
Figure 1: Vehicle Wiring Diagram

The IMD is shown on the left side of the wiring diagram and is connected in series with the BOTS and Accumulator.


## BOM

| Item                            | Manufacturer       | Part Number           | Distributor  | Distributor part number  | Quantity  | Price    | URL |
|---------------------------------|--------------------|-----------------------|--------------|--------------------------|-----------|----------|--------|
|  ISOMETER® IR155-3203/IR155-3204 (IMD)  | Bender | Part # | Bender | Distr.#   | 1         | $xx.xx  | <https://www.bender.de/en/products/insulation-monitoring/isometer-ir155-3203-ir155-3204/> |
| **Total**          			  |                    |                       |              |                          |           | $xx.xx |   |

## Analysis
The choice to purchase an IMD is intended to speed up the building process for the vehicle and to be able to adhere to the rules and constraints of Formula SAE. This IMD is a good choice because it IMD meets the requirements of the Formula SAE Rulebook, as it is one of the IMDs listed in the approved parts list for Formula SAE. Since it is already recommended withing the Formula SAE rulebook, it saves us time from having to do more research than necessary to choose an IMD. Overall, this is the best solution for all intended purposes as it does not make sense for us to design our own IMD. By going thiis route with the IMD, we just need to know how to connect it to the shutdown circuit.

## References
1. Formula SAE, “Formula SAE Rules 2024 Version 1.0”, fsaeonline.com, <https://www.fsaeonline.com/cdsweb/gen/DownloadDocument.aspx?DocumentID=369d01c0-589d-4ebe-b8d4-b07544f4a52b> (accessed Nov 15, 2024)
2. Bender, "ISOMETER® IR155-3203/IR155-3204", bender.de, <https://www.bender.de/en/products/insulation-monitoring/isometer-ir155-3203-ir155-3204/>, (accessed Nov 19, 2024)
3. Bender, "ISOMETER® IR155-3203/IR155-3204 Datasheet", (accessed Nov 19, 2024)
