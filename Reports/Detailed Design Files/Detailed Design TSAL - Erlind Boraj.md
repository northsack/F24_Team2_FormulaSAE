 # Formula SAE Electric- Tractive System Active Light

**Erlind Boraj**  
*Tennessee Technological University, ECE Department*  
**Tennessee Tech Motorsports**  
Cookeville, TN, USA  
[eboraj42@tntech.edu](mailto:eboraj42@tntech.edu)

# Function of the Subsystem

The Tractive System Active Light (TSAL) serves as a mandated safety indicator, required by Formula SAE Electric regulations, to communicate the active state of the vehicle’s high-voltage tractive system. Its primary function is to alert personnel to the presence of high-voltage conditions, ensuring safe handling and operation during all phases of vehicle use. The TSAL illuminates whenever the tractive system voltage exceeds 60V and deactivates only when the tractive system is safely powered down. This functionality provides a clear, unambiguous indication of the system's status, preventing inadvertent exposure to high voltage. The Tractive System Active Light (TSAL) circuit is designed to indicate the presence of high voltage (HV) in a Formula SAE electric vehicle's tractive system, ensuring compliance with FSAE regulations. The TSAL provides visual feedback using red and green lights to signal system status.


# Specifications and Constraints

#### Design Specifications:
- **Voltage Threshold:** The TSAL must activate at a minimum tractive system voltage of 60V.
- **Hardware-Based Control:** The TSAL must function independently of software to ensure reliability in case of software or system failures.
- **Visibility:** The TSAL must be clearly visible from all angles during vehicle operation and maintenance.

#### Constraints:
- **Safety Standards Compliance:** The TSAL must meet Formula SAE Electric rules, which mandate the use of an indicator light to signal an active high-voltage system.
- **System Integration:** The TSAL must interface with the accumulator and shutdown circuit to ensure correct activation and deactivation.
- **Physical Placement:** The TSAL must be positioned on the vehicle to ensure maximum visibility to nearby personnel.

#### Rationale for Constraints:
- Compliance with FSAE rules ensures the vehicle is competition-eligible.
- Hardware-based control eliminates the risk of software-related failures.
- Proper positioning and visibility enhance operational safety and prevent accidents.

# Overview of Proposed Solution

The proposed TSAL subsystem utilizes hardware-based activation triggered by the shutdown circuit and high-voltage connections. This design integrates directly with the accumulator and the DC power input from the shutdown circuit to ensure precise activation when the tractive system is live. It automatically illuminates when the tractive system voltage exceeds 60V and turns off when the shutdown circuit disables the high-voltage system. This design complies with all Formula SAE Electric safety requirements, ensuring reliability and safety during operation and maintenance while maintaining a straightforward and robust hardware configuration.

# Interface with Other Subsystems

The Tractive System Active Light (TSAL) subsystem interfaces with both high- and low-voltage systems to ensure reliable operation and compliance with safety standards. These connections enable precise activation and deactivation of the TSAL based on the tractive system's operational state.

#### Inputs
- **High-Voltage Input (Accumulator):**  
  The TSAL indirectly receives power from the accumulator, which steps down the tractive system voltage to a level usable by the GLV system. The TSAL activates when the tractive system voltage exceeds 60V.

- **Low-Voltage Input (Shutdown Circuit):**  
  The TSAL is directly connected to the shutdown circuit, which enables or disables the TSAL by controlling the power supplied to it. The shutdown circuit ensures that the TSAL deactivates when the tractive system is no longer live.

#### Outputs
- **Visual Indicator:**  
  The TSAL provides a highly visible flashing light when the tractive system voltage is active, signaling the presence of high voltage to team members, track officials, and nearby personnel.

#### Communication and Data Transfer
- **Method of Communication:**  
  The TSAL subsystem relies on hardware signals for communication. The accumulator powers the TSAL only when the tractive system is active, ensuring hardware-based control without the need for software intervention.

- **Data Transmitted:**  
  The TSAL does not transmit digital data but serves as a direct hardware-driven visual signal. Its on/off state communicates the operational status of the high-voltage tractive system.

  
  #### Isolated Power Supply  
  The power supply utilizes a 6-pin connector that serves as the main power and T-cell output interface. The incoming power connects directly to GLV+ (Grounded Low Voltage positive), which represents the raw positive voltage from the car. To protect the system from potential reverse polarity damage, the power is routed through a rectifier diode, converting it into VCC. This polarity-protected version of GLV+ ensures stable power for sensitive components. The system also includes an isolated 12V supply using a SPAN 0-8X12, a 12V-to-12V DC-DC converter. This isolated 12V (notated as +12V) powers the high-voltage side of the circuit. Grounding is split into two reference points: GLV- for low-voltage ground and a separate high-voltage ground symbol for the high-voltage side, ensuring proper isolation and safety.

# Printed Circuit Board Layout
<img width="797" alt="Fixed TSAL schematic" src="https://github.com/user-attachments/assets/0fc1c25a-64b6-4844-87bc-5fbe00c74da0">

![image](https://github.com/user-attachments/assets/c2b4f60c-930d-41de-b73a-cfef7b9d9db9)


![462561839_603419298698998_6469560685586508983_n](https://github.com/user-attachments/assets/a571366d-d4d7-4bf7-badc-f7fa59feae46)

# BOM

| Designator     | Component Name     | Type                  | Qty | Unit Price ($) | Cost ($) | Seller  | Link                                                                                                                             |
|----------------|--------------------|-----------------------|-----|----------------|----------|---------|----------------------------------------------------------------------------------------------------------------------------------|
| R2, R4, R6, R7 | 249K               | Resistor              | 4   | 0.1            | 0.4      | DigiKey | [Link](https://www.digikey.com/en/products/detail/stackpole-electronics-inc/RMCF0402FT249K/1761551)                             |
| R9, R13, R19   | 2K2                | Resistor              | 3   | 0.1            | 0.3      | Mouser  | [Link](https://www.mouser.com/ProductDetail/YAGEO/RC0603FR-072K2L)                                                             |
| R1             | 75K                | Resistor              | 1   | 0.3            | 0.3      | Mouser  | [Link](https://www.mouser.com/ProductDetail/Panasonic/ERJ-UP6D7502V)                                                           |
| R3             | 24K                | Resistor              | 1   | 0.3            | 0.3      | Mouser  | [Link](https://www.mouser.com/ProductDetail/Panasonic/ERJ-UP6D2402V)                                                           |
| R5             | 900                | Resistor              | 1   | 0.24           | 0.24     | Mouser  | [Link](https://www.mouser.com/ProductDetail/YAGEO/RT1206CRE07900RL)                                                           |
| R10, R11       | 100                | Resistor              | 2   | 0.59           | 1.18     | Mouser  | [Link](https://www.mouser.com/ProductDetail/Vishay/CRCW2010100RJNEFIF)                                                        |
| R14, R18       | 10K                | Resistor              | 2   | 0.49           | 0.98     | Mouser  | [Link](https://www.mouser.com/ProductDetail/Vishay/CRCW121010K0JNEAIF)                                                        |
| R15, R16       | 22K                | Resistor              | 2   | 0.43           | 0.86     | Mouser  | [Link](https://www.mouser.com/ProductDetail/Panasonic/ERA-2VPB2202X)                                                           |
| R17            | 220K               | Resistor              | 1   | 0.19           | 0.19     | Mouser  | [Link](https://www.mouser.com/ProductDetail/Panasonic/ERA-6AED224V)                                                           |
| R8             | 49K9               | Resistor              | 1   | 0.64           | 0.64     | Mouser  | [Link](https://www.mouser.com/ProductDetail/YAGEO/RT0402BRB0749K9L)                                                           |
| R12            | 1M                 | Resistor              | 1   | 0.86           | 0.86     | Mouser  | [Link](https://www.mouser.com/ProductDetail/Vishay-Draloric/RCV25121M00JNEG)                                                   |
| U1            | SPAN02A-12             | DC DC CONVERTER 12V 2W              | 1   | 6.50           | 6.50     | DigiKey  | [Link](https://www.mouser.com/ProductDetail/Vishay-Draloric/RCV25121M00JNEG)                                                   |
| Q2, Q4         | MCT06P10-TP        | Seminconductor           | 2   | 1.18           | 2.36     | DigiKey | [Link](https://www.digikey.com/en/products/detail/micro-commercial-co/MCT06P10-TP/10054657)                                     |
| U3             | 4N35               | Optocoupler           | 1   | 0.71           | 0.71     | Mouser  | [Link](https://www.mouser.com/ProductDetail/Vishay/4N35)                                                                       |
| Q1, Q3         | 2N7002             | MOSFET                | 2   | 0.16           | 0.32     | Mouser  | [Link](https://www.mouser.com/ProductDetail/Nexperia/2N7002215)                                                               |
| C2             | 10nF               | Capacitor             | 1   | 0.11           | 0.11     | DigiKey | [Link](https://www.digikey.com/en/products/detail/murata-electronics/GRM21BR61C106KE15K/2546903)                                 |
| C3, C4, C5     | 100nF              | Capacitor             | 3   | 0.53           | 1.59     | DigiKey | [Link](https://www.digikey.com/en/products/detail/murata-electronics/GRM31CD80J107MEA8K/13905021)                                 |
| U2             | LM311              | Comparator            | 1   | 0.41           | 0.41     | Mouser  | [Link](https://www.mouser.com/ProductDetail/Texas-Instruments/LM311P)                                                         |
| D2, D3             | 12V Zener          | Zener Diode           | 2   | 0.18           | 0.36     | Mouser  | [Link](https://www.mouser.com/ProductDetail/Nexperia/1N4742A113)                                                              |
| N/A            | PCB                | PCB Multilayer        | 1   | 2              | 2        | JLCPCB  | Custom Product, no link                                                                                                         |
| N/A            | MEJ1S1215SC        | Isolated DC-DC Converter | 1   | 8.63           | 8.63     | Mouser  | [Link](https://www.mouser.com/ProductDetail/Murata-Power-Solutions/MEJ1S1215SC)                                                |
| U1             | MC1455BDR2G        | Timer                 | 1   | 0.36           | 0.36     | Mouser  | [Link](https://www.mouser.com/ProductDetail/onsemi/MC1455BDR2G)                                                               |
| D1             | 1N4007             | Diode                 | 1   | 0.13           | 0.13     | DigiKey | [Link](https://www.digikey.com/en/products/detail/diodes-inc/1N4007/1137589)                                                   |
| **Total**      |                    |                       |     |                | **29.54** |         |                                                                                                                                    |
                                                                                                                                                       |


**Note:** This BOM does not account for spare parts. Quatities in the table represent the minimum quantity needed for the one PCB. The team will order at least twice the quantity shown in the BOM. The BOM does not account for shipping cost or bulk prices. Sellers are subject to change, based on their shipping prices and time. 

# Analysis

#### Circuit Overview

The TSAL circuit is built on a single control board and consists of HV connections from the tractive system, a 6-pin connector for power, ground, and outputs to the indicator lights. High-side outputs are utilized, allowing the lights to share a common ground if necessary.

#### Core Circuit Components:
- A comparator for voltage threshold detection.
- MOSFETs for output switching.
- An optocoupler for isolation.
- A 555 timer for light flashing functionality.
- Voltage dividers and protection elements for accurate and safe operation.

#### Voltage Threshold Detection
- **Reference Voltage:**  
  A voltage divider sets a reference voltage of approximately 3V using a 12V input. This reference ensures that the circuit detects voltages above 60V in the tractive system.
  
- **Input Voltage Scaling:**  
  A separate voltage divider scales the input voltage to a level compatible with the comparator. At 60V input, the scaled voltage exceeds the 3V reference, triggering the circuit.

#### Circuit Protection
- **Voltage Divider Resistors:**  
  The resistors in the input voltage divider are rated for 200V each and arranged to safely handle up to 600V.
  
- **Zener Diodes:**  
  A Zener diode clamps the input voltage to protect the comparator from transient spikes exceeding 12V. This ensures robust operation under noisy conditions.

- **Polarity Protection:**  
  A rectifier diode is included to protect against reverse polarity on the low-voltage supply.

#### Signal Isolation and Logic Control
- **Optocoupler:**  
  The comparator output drives an optocoupler LED. When the input voltage is above the threshold, the optocoupler blocks current flow, isolating the HV system from the rest of the circuit.
  
- **MOSFET Control:**  
  The optocoupler's output feeds into a MOSFET-based inverter. This controls the enable pin of a 555 timer and the gate of another MOSFET, which, in turn, drives the red and green indicator lights.


#### Indicator Light Operation

- **Red Light (High Voltage):**  
  When HV is detected, the 555 timer operates in astable mode, generating a flashing signal. This drives a P-channel MOSFET, activating the red light.
  
- **Green Light (Safe State):**  
  When HV is absent, the P-channel MOSFET for the red light is disabled, and a separate MOSFET activates the green light.

#### Power Management
- **Voltage Regulation:**  
  The circuit uses an isolated 12V supply for the HV side. The low-voltage side is powered through a polarity-protected connection.

- **Current Handling:**  
  The design ensures sufficient current capacity for all components, avoiding bottlenecks. The design ensures sufficient current capacity for all components, especially focusing on the red and green LEDs. The selected MOSFETs (2N7002) are rated for continuous currents up to 5A. This rating is significantly higher than the current typically required to drive LEDs. Most standard red and green LEDs have a forward current requirement of around 20mA to 30mA each, with a maximum forward voltage of around 2.0V to 2.4V for red LEDs and 2.0V to 3.2V for green LEDs.

Given these operating conditions, the total current needed for both LEDs combined would be at most 60mA (30mA each, conservatively), which is only 1.2% of the 5A capacity. This margin ensures that the MOSFETs are operating well below their maximum continuous current rating, providing a robust and highly reliable design.

LED Selection and Part Justification

The specific LED parts chosen for this design are as follows:

Red LED: Vishay TLHR4400
Green LED: Vishay TLHG4400
These LEDs are known for their high brightness and low current requirements. The forward current for both models is around 20mA, and they operate with a forward voltage of about 2.1V (red) and 2.2V (green), perfectly aligned with the design's power supply system.


#### Design Considerations and Improvements
- **Hysteresis Resistor:**  
  A hysteresis resistor was initially included to stabilize the comparator output but was later removed due to potential unintended current paths. This modification minimizes risk without affecting performance.
  
- **Circuit Testing:**  
  A high-side switch configuration was implemented using the optocoupler. Though unconventional, this approach prevents issues like saturation voltage instability encountered in earlier designs.


#### User Feedback Features

- **Additional Feedback:**  
  We may consider an onboard red LED that mirrors the external red light's flashing pattern, providing additional visual feedback for troubleshooting or testing.


**This design ensures compliance with FSAE safety standards while maintaining simplicity and robustness. The inclusion of protective elements and thoughtful component selection guarantees reliable operation in the demanding environment of an electric race car.***

# References

1. Formula SAE, “Formula SAE Rules 2024 Version 1.0,” *fsaeonline.com*,  
   [https://www.fsaeonline.com/cdsweb/gen/DownloadDocument.aspx?DocumentID=369d01c0-589d-4ebe-b8d4-b07544f4a52b](https://www.fsaeonline.com/cdsweb/gen/DownloadDocument.aspx?DocumentID=369d01c0-589d-4ebe-b8d4-b07544f4a52b) (accessed Nov 15, 2024).

2. Wisconsin Formula SAE Racing, "Electrical System Form FSAE-E2018," *wisconsinracing.org*,  
   [https://www.wisconsinracing.org/wp-content/uploads/2020/10/2018_ESF_Submission.pdf](https://www.wisconsinracing.org/wp-content/uploads/2020/10/2018_ESF_Submission.pdf) (accessed Nov 21, 2024).

3. MIT, "Formula SAE EV Battery Design," *MIT DSpace*.  
   [https://dspace.mit.edu](https://dspace.mit.edu). (accessed Nov 21, 2024).

4. Meah, S., et al., "Design, build, and test drive a FSAE electric vehicle," *The Journal of Engineering*, vol. 2020, no. 1, pp. 1-12, 2020.  
   [https://ietresearch.onlinelibrary.wiley.com/doi/pdf/10.1049/joe.2020.0015](https://ietresearch.onlinelibrary.wiley.com/doi/pdf/10.1049/joe.2020.0015) (accessed Nov 21, 2024).

5. LEM, "Current Transducer HO-S series Datasheet," *LEM*.  
   [https://www.lem.com](https://www.lem.com) (accessed Nov 21, 2024).

6. "Video Title," *YouTube*, published by [Channel Name], [Video Length]. Available: [https://www.youtube.com/watch?v=5dQUlfogNlM](https://www.youtube.com/watch?v=5dQUlfogNlM). [Accessed: Nov. 21, 2024].

7. FormulaElectricRacingNUST. "Tractive System Activation Light 2024." Hackster.io, 16 July 2024. [Online]. Available: https://www.hackster.io/formulaelectricracingnust/tractive-system-activation-light-2024-fbaa8f. [Accessed: 21 Nov 2024].

8. vsdave1616. "Schematic for TSAL_KE1_Green: Designing a Tractive System Active Light." Flux.ai, [Online]. Available: https://www.flux.ai/vsdave1616/tsalke1green. [Accessed: 21 Nov 2024].

9. Susanto, R. "The Electrical Circuitry for Formula SAE-Electric 2012." ROBLAB.org, 2012. [Online]. Available: https://roblab.org/theses/2012-REV-SAE-Electrics-Susanto.pdf. [Accessed: 21 Nov 2024].

10. ephrenm. "tt08-tsal: Semiconductor design for FSAE EV Tractive System Active Light (TSAL)." GitHub, [Online]. Available: https://github.com/ephrenm/tt08-tsal. [Accessed: 21 Nov 2024].

11. Eurocircuits. "Formula Cruisers Season 20/21." Eurocircuits, 2021. [Online]. Available: https://www.eurocircuits.com/blog/formula-cruisers-season-20-21/. [Accessed: 21 Nov 2024].





