
_Formula SAE Electric Vehicle Detailed Design_

Zach Holt
Tennessee Technological University, ECE Department  
Tennessee Tech Motorsports  
Cookeville, TN, USA  
[zsholt42@tntech.edu](mailto:zsholt42@tntech.edu)

## Function of the Subsystem: Shutdown Circuit - Brake Overtravel Switch (BOTS)
The function of the BOTS inside the shutdown circuit is to detect movement of a braking mechanism beyond its designed limit. It is part of the shutdown circuit, and its purpose is to open the shutdown circuit when excessive overtravel is detected.

## Specifications and Restraints
As the BOTS is a part of the shutdown circuit, it is bound by the rules and regulations specified in the FSAE-EV Rulebook [1]. The rules pertaining to the BOTS are as follows:
1. The BOTS shall directly carry the shutdown circuit current.
2. The BOTS shall open the shutdown circuit when acivated, stopping all accumulator current and ensuring the tractive system shuts down.

## Overview of Proposed Solution
The proposed solution is to purchase a BOTS and integrate it within our vehicle. This solution makes sense for our project as it will save time and resources for our team. The BOTS we choose shall follow the constraints specified in the Formula SAE rulebook.

## Interface With Other Subsystems



## BOM

| Item                            | Manufacturer       | Part Number           | Distributor  | Distributor part number  | Quantity  | Price    |
|---------------------------------|--------------------|-----------------------|--------------|--------------------------|-----------|----------|
|  V15W-WZ200A05-AW1 (Brake Overtravel Switch)  | Honeywell | V15W-WZ200A05-AW1 | Mouser Electronics  | 785-V15W-WZ200A05AW1             | 1         | $20.00  |
| **Total**          			  |                    |                       |              |                          |           | $20.00  |

## References
1. Formula SAE, “Formula SAE Rules 2024 Version 1.0”, fsaeonline.com, <https://www.fsaeonline.com/cdsweb/gen/DownloadDocument.aspx?DocumentID=369d01c0-589d-4ebe-b8d4-b07544f4a52b> (accessed Nov 15, 2024)
2. Mouser Electronics, "V15W-WZ200A05-AW1", mouser.com, <https://www.mouser.com/ProductDetail/Honeywell/V15W-WZ200A05-AW1?qs=0Ys4hG7ORMcM0vmcdmCykg%3D%3D>, (accessed Nov 18, 2024)
3. Mouser Electronics, "V15W-WZ200A05-AW1 Datasheet", (accessed Nov 18, 2024)