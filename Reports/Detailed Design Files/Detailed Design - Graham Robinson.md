Formula SAE Electric Vehicle Detailed Design

Graham Robinson

Tennessee Technological University, ECE Department

Tennessee Tech Motorsports

Cookeville, TN, USA

glrobinson42@tntech.edu

# The Revieew Person

# **Detailed Design Motor Controller**

#### **Function of the Subsystem:**

The motor controller plays a critical role in regulating the power supplied to the motor by the accumulator, converting the direct current (DC) from the battery into alternating current (AC) for AC motors or managing DC power directly for DC motors. It modulates motor speed and torque by adjusting the voltage and current in response to the driver’s input, ensuring smooth acceleration, precise torque control, and optimal power distribution across varying driving conditions. The motor controller ensures that the electric vehicle can reach its target performance goals, including a top speed of 60 miles per hour, and safely manage the motor’s power and thermal limits during operation.

---

#### **Specifications and Constraints:**

- **Power Input:** Must support a range of DC input voltages (48V - 96V) and output accordingly to either an AC or DC motor.
- **Safety Requirements:** Must integrate with the vehicle’s shutdown system, including overvoltage, overcurrent, and thermal protection features to prevent damage to the motor and other powertrain components.
- **Thermal Management:** Requires a cooling system (either air or liquid) to keep the controller within safe operating temperatures, especially during high-power demands.
- **Regulatory Compliance:** Must adhere to Formula SAE standards, including compatibility with required safety features such as the Brake System Plausibility Device (BSPD) and Insulation Monitoring Device (IMD).
- **Torque Control:** Must allow for precise control of motor torque and speed, providing real-time adjustments based on throttle input.
- **Efficiency:** Must optimize power usage and efficiency, employing control algorithms like Field-Oriented Control (FOC) for AC motors.
- **Subsystem Integration:** Needs seamless integration with the accumulator, throttle system, and other powertrain components to ensure smooth vehicle operation.

---

#### **Overview of Proposed Solution:**

The motor controller selected for this system will fulfill the subsystem’s specifications by converting DC power from the accumulator into the necessary form (AC or DC) to power the motor, allowing the vehicle to achieve its desired speed and torque. It will be equipped with essential safety features, including thermal protection, overcurrent protection, and real-time diagnostics for system monitoring. The motor controller will employ advanced control algorithms such as Field-Oriented Control (FOC) to maximize motor efficiency, and it will be integrated with a robust cooling system to prevent overheating during intense operation.

The solution meets the specifications of torque and speed control, safety, and thermal management while ensuring the vehicle operates within the defined parameters of Formula SAE. By optimizing power distribution and controlling the motor's performance, the motor controller will enable the vehicle to meet the competition’s performance requirements and safety regulations.

---

#### **Interface with Other Subsystems:**

The motor controller interfaces with several other subsystems within the electric powertrain:

| Connection     | Connection Type | Direction |
|----------------|-----------------|-----------|
| Battery        | DC Power        | Input     |
| Low Voltage    | DC Power        | Input     |
| APP 1          | Analog          | Input     |
| APP 2          | Analog          | Input     |
| BSE            | Analog          | Input     |
| Phase A        | AC Power        | Output    |
| Phase B        | AC Power        | Output    |
| Phase C        | AC Power        | Output    |
| Thermistor     | Analog          | Input     |
| Sine Encoder   | Analog          | Input     |
| Cosine Encoder | Analog          | Input     |

- **Battery Input:** The motor controller receives DC power from the accumulator, which is converted to AC or DC output for the motor.
- **Throttle Input (APP 1 & APP 2):** Analog signals from the throttle position sensors provide feedback to the motor controller, dictating the required torque and speed.
- **BSE (Brake System Input):** The brake system provides an analog signal to the motor controller, indicating braking status.
- **Motor Outputs (Phase A, B, C):** The motor controller sends AC power to the motor through three-phase outputs (A, B, C) to control the motor's speed and torque.
- **Thermal and Encoder Inputs:** The motor controller monitors thermal conditions (via thermistor) and motor position (via sine and cosine encoders) to adjust the motor’s performance and prevent overheating.

---

#### **Bill of Materials (BOM):**

| Component Name               | Manufacturer | Part Number       | Distributor    | Distributor Part Number | Quantity | Price   | URL                                                           |
|------------------------------|--------------|-------------------|----------------|-------------------------|----------|---------|---------------------------------------------------------------|
| **Motor Controller**          | Sevcon       | 6585-503-001      | Sevcon         | 6585-503-001            | 1        | $800.00 | [Sevcon](https://www.sevcon.com)                               |
| **Sevcon DVT Software**       | Sevcon       | DVT-2023          | Sevcon         | DVT-2023                | 1        | $502.32 | [Sevcon](https://www.sevcon.com)                               |
| **Wiring Harness**            | McMaster-Carr| 7099K12           | McMaster-Carr  | 7099K12                 | 1        | $47.00  | [McMaster-Carr](https://www.mcmaster.com)                      |
| **Thermistor**                | Honeywell    | 15TS08-302        | Digi-Key       | 15TS08-302              | 1        | $40.00  | [Digi-Key](https://www.digikey.com)                            |
| **Throttle Position Sensor**  | Haltech      | HT-010402         | Haltech        | HT-010402               | 1        | $160.00 | [Haltech](https://www.haltech.com/product/ht-010402-throttle-position-sensor-grey/) |

#### **Total Subsystem Cost:**

**$1,549.32**

---

#### **Analysis:**

The design of the motor controller effectively meets the system’s requirements by incorporating key features such as power regulation, safety, and thermal management. The integration of advanced control algorithms like Field-Oriented Control (FOC) maximizes motor efficiency, contributing to the vehicle’s overall performance. The motor controller’s ability to manage both speed and torque ensures the vehicle can achieve its required top speed of 60 miles per hour while maintaining control over the power distribution.

The system’s safety features, including overcurrent protection, overvoltage protection, and thermal management, ensure the motor and powertrain are safeguarded against potential failures. Additionally, by incorporating real-time feedback through encoders and sensors, the motor controller can adjust its operations dynamically, ensuring optimal performance in varying conditions.

Given the carefully selected components, the motor controller will integrate seamlessly with the overall electric powertrain and meet all Formula SAE regulations, ensuring the vehicle’s competitiveness and safety during operation.

---

#### **References:**

1. Sevcon Motor Controller [Sevcon](https://www.sevcon.com)
2. Sevcon DVT Software [Sevcon](https://www.sevcon.com)
3. Honeywell Thermistor [Digi-Key](https://www.digikey.com)
4. Haltech Throttle Position Sensor [Haltech](https://www.haltech.com/product/ht-010402-throttle-position-sensor-grey/)

# Detailed Design: Charger Subsystem  


### **Function of the Subsystem**  

The charger subsystem serves a critical role in the Formula SAE electric vehicle by ensuring the accumulator (battery pack) is safely and efficiently recharged. Its primary function is to replenish the energy needed for vehicle operation during endurance events and testing scenarios while adhering to strict safety and performance standards.  

This subsystem integrates seamlessly with the overall vehicle system, interfacing with the Accumulator Management System (AMS) to monitor key parameters such as state of charge, voltage, and temperature. Additionally, the charger interacts with the shutdown system, ensuring operation only occurs under safe conditions.  

The design prioritizes safety by incorporating galvanic isolation, temperature monitoring, and interlocks to prevent high-voltage risks. Operationally, it allows for charging without removing the accumulator from the vehicle, enhancing efficiency and minimizing downtime. Through its functionality, the charger subsystem supports the reliability and competitiveness of the Formula SAE electric vehicle.  


---

### **Specifications and Constraints**  

#### **Specifications**  
The charger subsystem for the Formula SAE electric vehicle must adhere to the following specifications to ensure safety, functionality, and compliance:  
1. **Voltage and Current Alignment:**  
   - Must provide regulated voltage and current to match the accumulator's charging requirements, preventing overcharging or overheating.  
   - Supports an accumulator voltage range of 100V–400V with a maximum current output of 20A.  
2. **Galvanic Isolation:**  
   - Ensures no direct electrical connection between the charger and accumulator, reducing the risk of electric shock.  
3. **Temperature Monitoring:**  
   - Integrated with the AMS to continuously monitor the accumulator's temperature during charging.  
4. **Charging Mode:**  
   - Charging is restricted to when the tractive system is inactive, in compliance with Formula SAE safety regulations.  


#### **Constraints**  
The charger subsystem must operate within the following constraints, which stem from physical, regulatory, ethical, and socio-economic factors:  

1. **Physical and Operational Constraints:**  
   - **Thermal Environment:**  
     The system must function in a temperature range of 0°C–25°C, addressing competition conditions in Michigan's variable weather.  
   - **Power Availability:**  
     Operates using standard AC power (110–240V), as provided in competition and testing environments.  

2. **Regulatory and Safety Standards:**  
   - **Formula SAE Compliance:**  
     The charger must meet all safety and electrical design standards specified by the competition, including galvanic isolation and safe operation protocols.  
   - **Shop Safety Protocols:**  
     Charging is permitted only when the accumulator is fully secured, and the shutdown system is active.  

3. **Ethical and Socio-Economic Constraints:**  
   - **Safety-First Design:**  
     Prioritizes operator safety by incorporating galvanic isolation and interlocks to prevent accidental high-voltage exposure.  
   - **Budget Constraints:**  
     Components and design decisions are limited by the $893.44 budget allocated for the charger subsystem. Cost-effective design choices are made to maximize functionality without exceeding the budget.  

4. **Subsystem Interdependence:**  
   - **AMS Integration:**  
     Requires reliable communication with the AMS to ensure accurate monitoring of the accumulator's state of charge, temperature, and voltage.  
   - **Shutdown System Interlocks:**  
     The charger cannot initiate charging unless the tractive system is inactive and safety interlocks are engaged.  

#### **Rationale for Constraints**  
- **Physical constraints** such as thermal and voltage ranges ensure the subsystem performs reliably under expected conditions.  
- **Regulatory constraints** are necessary for compliance with Formula SAE rules, prioritizing safety and competition readiness.  
- **Ethical and socio-economic constraints** balance safety, cost, and resource efficiency, ensuring the design is responsible and practical for Tennessee Tech Motorsports’ goals.  

---  


### **Overview of Proposed Solution**  

The proposed solution for the charger subsystem is a robust, integrated system designed to safely and efficiently recharge the accumulator while meeting all specifications and constraints. The charger will interface seamlessly with the Accumulator Management System (AMS) to monitor and regulate key parameters, such as state of charge, voltage, and temperature, ensuring compliance with Formula SAE safety standards.  

Key design features include:  
1. **Galvanic Isolation:**  
   - Prevents direct electrical contact between the AC power source and the accumulator, significantly reducing the risk of electric shock.  

2. **Regulated Power Delivery:**  
   - Supplies stable voltage and current tailored to the accumulator’s requirements, avoiding overcharging and overheating while maximizing charging efficiency.  

3. **Safety Interlocks:**  
   - Ensures that charging can only occur when the vehicle's shutdown system is active and the tractive system is deactivated, minimizing high-voltage risks during operation or testing.  

4. **Integrated Monitoring:**  
   - Works in conjunction with the AMS to continuously track accumulator conditions, such as temperature and state of charge, automatically ceasing operation if anomalies like over-voltage or overheating are detected.  

5. **Temperature Resilience:**  
   - Designed to operate reliably in a temperature range of 0°C–25°C, accommodating the variable weather conditions of the Formula SAE competition in Michigan.  


---  

### **Interfaces with Other Subsystems**  
The charger interfaces with key subsystems as follows:  
- **Accumulator:** Provides high-voltage AC power for recharging.  
- **AMS:** Monitors battery conditions during charging to ensure safe operation.  
- **Shutdown System:** Restricts charging unless all safety protocols are met.  

---

### **Buildable Diagram**  


---


### **Bill of Materials (BOM)**  

Here’s the updated **Bill of Materials (BOM)** with the added **Throttle Position Sensor** and its link:



| Component Name        | Manufacturer          | Part Number        | Distributor      | Distributor Part Number | Quantity | Price   | URL                                                    |
|-----------------------|-----------------------|--------------------|------------------|-------------------------|----------|---------|--------------------------------------------------------|
| **Charger Unit**       | Sevcon                | 6585-503-000       | Sevcon           | 6585-503-000            | 1        | $500.00 | [Sevcon](https://www.sevcon.com)                       |
| **Sevcon DVT Software**| Sevcon                | DVT-2023           | Sevcon           | DVT-2023                | 1        | $502.32 | [Sevcon](https://www.sevcon.com)                       |
| **AC-DC Converter**    | Vicor                 | VBM2400D24-12      | Digi-Key         | 946-2749                | 1        | $225.00 | [Digi-Key](https://www.digikey.com)                    |
| **ISOMETER® IR155 3204** | Bender               | IR155 3204         | Bender USA       | IR155 3204              | 1        | $25.00  | [Bender USA](https://www.bender-usa.com)               |
| **Wiring Harness**     | McMaster-Carr         | 7099K12            | McMaster-Carr    | 7099K12                 | 1        | $47.00  | [McMaster-Carr](https://www.mcmaster.com)              |
| **Throttle Position Sensor** | Honeywell        | 15TS08-302         | Digi-Key         | 15TS08-302              | 2        | $160.00 | [Digi-Key](https://www.digikey.com)                    |
| **Throttle Position Sensor** | Haltech         | HT-010402          | Haltech          | HT-010402               | 1        | $160.00 | [Haltech](https://www.haltech.com/product/ht-010402-throttle-position-sensor-grey/) |

#### **Total Subsystem Cost:**  
**$1,599.32**



---  
#### **Analysis of Crucial Design Decisions**  
1. **Galvanic Isolation:** Selected to prioritize operator safety and meet Formula SAE regulations.  
2. **Integrated AMS Communication:** Enables efficient fault detection and response, enhancing accumulator reliability.  
3. **In-Vehicle Charging Design:** Streamlined charging process improves usability while maintaining safety.  
4. **Safety Interlocks:** Minimize high-voltage exposure risks and ensure operational integrity.  
---

#### **Execution Plan**  
**Skill Sets:**  
- **Electrical Engineering:** Design and assembly of high-voltage connections and safety systems.  
- **Software Integration:** Programming AMS interfaces for monitoring and control.  
- **Mechanical Engineering:** Securing the charger unit within the vehicle.  

**Time Requirements:**  
1. **Component Procurement:** 2 weeks  
2. **System Assembly:** 1 week  
3. **Safety and Operational Testing:** 2 weeks  


---

### **References**  

1. Formula SAE, "Formula SAE Electric Rules," SAE International, 2024. [1]  
   Accessed: Nov. 20, 2024. [https://www.sae.org/](https://www.sae.org/)

2. U.S. Department of Energy, "Electric Vehicle Battery Charging," 2022. [2]  
   Accessed: Nov. 20, 2024. [https://www.energy.gov/eere/electric-vehicles](https://www.energy.gov/eere/electric-vehicles)

3. Sevcon, "DVT Configuration Software Manual," 2022. [3]  
   Accessed: Nov. 20, 2024. [https://www.sevcon.com](https://www.sevcon.com)

4. "ISOMETER® IR155 3204 Insulation Monitoring Device," Bender Inc., 2021. [4]  
   Accessed: Nov. 20, 2024. [https://www.bender-usa.com](https://www.bender-usa.com)

5. Sensata Technologies, "Resettable Crash Sensor (Inertia Switch) User Manual," 2021. [5]  
   Accessed: Nov. 20, 2024. [https://www.sensata.com](https://www.sensata.com)

6. McMaster-Carr, "Vehicle Wire Assortments," 2023. [6]  
   Accessed: Nov. 20, 2024. [https://www.mcmaster.com](https://www.mcmaster.com)

7. Sevcon Motor Controller [Sevcon](https://www.sevcon.com)

8. Sevcon DVT Software [Sevcon](https://www.sevcon.com)
   
9. Honeywell Thermistor [Digi-Key](https://www.digikey.com)

10. Haltech Throttle Position Sensor [Haltech](https://www.haltech.com/product/ht-010402-throttle-position-sensor-grey/)
