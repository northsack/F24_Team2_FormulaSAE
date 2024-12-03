# Formula SAE Electric Vehicle Detailed Design

**Graham Robinson**  
Tennessee Technological University, ECE Department  
Tennessee Tech Motorsports  
Cookeville, TN, USA  
glrobinson42@tntech.edu

# **Detailed Design: Motor Controller Subsystem**

#### **Function of the Subsystem**

The motor controller is one of the most critical components of the electric powertrain. Its primary function is to regulate the power delivered from the accumulator to the motor. For AC motors, it converts the DC power from the battery into AC power. For DC motors, it modulates the direct current directly. This regulation allows the motor to produce the desired speed and torque based on the driver's input. By adjusting voltage and current, the motor controller ensures smooth acceleration, precise torque control, and efficient power distribution under different driving conditions.

In addition to power regulation, the motor controller also helps the vehicle meet specific performance targets, like reaching a top speed of 60 miles per hour. It incorporates built-in safety and thermal management features to prevent overheating or powertrain failures during operation.

---

#### **Specifications and Constraints**

- **Power Input:** Operates within a DC voltage range of 48V to 96V to accommodate the energy supplied by the accumulator.  
- **Safety Integration:** Must be compatible with the shutdown system, including safety mechanisms like overvoltage, overcurrent, and thermal protection.  
- **Cooling System:** Requires efficient cooling (air or liquid) to maintain safe operating temperatures during prolonged use.  
- **Compliance:** Adheres to Formula SAE safety standards, such as the inclusion of a Brake System Plausibility Device (BSPD) and Insulation Monitoring Device (IMD).  
- **Torque and Speed Control:** Ensures precise adjustments based on the driver's throttle input to meet performance requirements.  
- **Efficiency:** Implements advanced algorithms, like Field-Oriented Control (FOC), to optimize power delivery and reduce energy loss.  
- **Subsystem Integration:** Must interface smoothly with other components, such as the accumulator, throttle sensors, and brake system.  

---

#### **APP Sensors (Accelerator Pedal Position Sensors)**

The Accelerator Pedal Position Sensors (APP sensors) are essential for communicating the driver’s throttle input to the motor controller. Two independent analog sensors (APP1 and APP2) are used for redundancy and safety.  

- **How They Work:**  
  APP1 and APP2 send proportional signals to the motor controller, which interprets the data to determine the driver’s desired speed and torque.  

- **Safety Redundancy:**  
  The system constantly cross-checks the signals from both sensors. If a discrepancy is detected, the motor controller triggers a fault state to prevent unintentional acceleration.  

- **Specifications:**  
  - Dual-sensor redundancy for fault tolerance  
  - Analog signal output ranging from 0V to 5V  
  - Designed to meet ISO 26262 safety standards  

- **Subsystem Integration:**  
  APP sensors connect directly to the motor controller, ensuring that the driver’s input is translated into reliable motor performance.  

---

#### **Overview of Proposed Solution**

The motor controller chosen for this design meets all necessary specifications and constraints. It is designed to convert DC power from the accumulator into the appropriate output (AC or DC) for the motor. Safety features such as thermal protection, overcurrent protection, and fault diagnostics are built in to protect the system during operation. 

To maximize performance and efficiency, the controller uses Field-Oriented Control (FOC) algorithms, allowing it to adjust torque and speed dynamically. The integration of a robust cooling system ensures the controller operates safely under high-power demands. Overall, this solution enables the electric powertrain to meet Formula SAE competition standards while achieving reliable performance.

---

#### **Interface with Other Subsystems**

The motor controller communicates with various subsystems, as shown below:

| **Connection**       | **Connection Type** | **Direction** |  
|-----------------------|---------------------|---------------|  
| Battery              | DC Power            | Input         |  
| Low Voltage          | DC Power            | Input         |  
| APP 1                | Analog              | Input         |  
| APP 2                | Analog              | Input         |  
| BSE                  | Analog              | Input         |  
| Phase A              | AC Power            | Output        |  
| Phase B              | AC Power            | Output        |  
| Phase C              | AC Power            | Output        |  
| Thermistor           | Analog              | Input         |  
| Sine Encoder         | Analog              | Input         |  
| Cosine Encoder       | Analog              | Input         |  

---

#### **Bill of Materials (BOM)**

| **Component Name**          | **Manufacturer** | **Part Number**  | **Distributor** | **Distributor Part Number** | **Quantity** | **Price** | **URL**                                                       |  
|-----------------------------|------------------|------------------|-----------------|----------------------------|--------------|-----------|--------------------------------------------------------------|  
| Motor Controller            | Sevcon          | 6585-503-001     | Sevcon          | 6585-503-001               | 1            | $800.00   | [Sevcon](https://www.sevcon.com)                              |  
| Sevcon DVT Software         | Sevcon          | DVT-2023         | Sevcon          | DVT-2023                   | 1            | $502.32   | [Sevcon](https://www.sevcon.com)                              |  
| Wiring Harness              | McMaster-Carr   | 7099K12          | McMaster-Carr   | 7099K12                    | 1            | $47.00    | [McMaster-Carr](https://www.mcmaster.com)                     |  
| Thermistor                  | Honeywell       | 15TS08-302       | Digi-Key        | 15TS08-302                 | 1            | $40.00    | [Digi-Key](https://www.digikey.com)                           |  
| Throttle Position Sensor    | Haltech         | HT-010402        | Haltech         | HT-010402                  | 1            | $160.00   | [Haltech](https://www.haltech.com/product/ht-010402-throttle-position-sensor-grey/) |  

**Total Cost:** $1,549.32  

---

#### **Analysis**

The motor controller design successfully meets the subsystem’s constraints and performance goals. Its ability to regulate power, manage torque, and adjust speed ensures the vehicle can perform under various conditions, including achieving a top speed of 60 mph.  

Safety features like overcurrent, overvoltage, and thermal protection prevent failures and extend the lifespan of components. The integration of APP sensors and control algorithms ensures reliable response to driver input while maximizing energy efficiency.  

By meeting Formula SAE standards, this motor controller provides the functionality and reliability required to compete effectively.  

---

# **Detailed Design: Charger Subsystem**

### **Function of the Subsystem**

The charger subsystem is responsible for safely recharging the accumulator, ensuring that the Formula SAE electric vehicle is fully powered for endurance events and testing. It works in conjunction with the Accumulator Management System (AMS) to monitor key parameters like state of charge, voltage, and temperature, and integrates with the shutdown system to ensure safe operation. The charger also prevents overcharging by delivering the appropriate power to the accumulator, keeping the vehicle ready for the next stage of competition.

---

### **Specifications and Constraints**

- **Voltage and Current Support:** Operates within a voltage range of 100V–400V and up to 20A for efficient charging.
- **Galvanic Isolation:** Prevents electrical contact between the charger and the accumulator, reducing shock risks.
- **Temperature Monitoring:** Continuously monitored by the AMS to prevent overheating during charging.
- **Safety Interlocks:** Charging can only occur when the tractive system is inactive and safety protocols are engaged.
- **Regulatory Compliance:** Meets Formula SAE safety standards, including galvanic isolation and charging interlocks.
- **Environmental Resilience:** Operates efficiently in temperatures ranging from 0°C to 25°C to accommodate varying conditions during the competition.

---

### **Overview of Proposed Solution**

The proposed charger design is optimized to ensure the accumulator is charged safely and efficiently:
- **Galvanic Isolation** is integrated to prevent high-voltage risks.
- **Regulated Power Delivery** ensures the accumulator is charged without risk of overvoltage or excessive current.
- **Temperature Resilience** ensures reliable operation in various environmental conditions.
- **AMS Integration** enables continuous monitoring of charging parameters, and **Safety Interlocks** prevent charging if unsafe conditions are detected.

This solution ensures the charger meets all functional requirements while adhering to safety protocols and Formula SAE standards.

---

### **Interface with Other Subsystems**

The charger subsystem interfaces with the following subsystems:

| **Connection**        | **Connection Type** | **Direction** |  
|-----------------------|---------------------|---------------|  
| Accumulator           | AC Power            | Input         |  
| AMS                   | Data Communication  | Input         |  
| Shutdown System       | Digital Control     | Input         |  

---

### **Bill of Materials (BOM)**

| **Component Name**      | **Manufacturer**    | **Part Number**  | **Distributor**   | **Distributor Part Number** | **Quantity** | **Price**  | **URL**                                                   |  
|-------------------------|---------------------|------------------|-------------------|----------------------------|--------------|------------|----------------------------------------------------------|  
| **Charger Unit**         | Sevcon              | 6585-503-000     | Sevcon            | 6585-503-000               | 1            | $500.00    | [Sevcon](https://www.sevcon.com)                          |  
| **Sevcon DVT Software**  | Sevcon              | DVT-2023         | Sevcon            | DVT-2023                   | 1            | $502.32    | [Sevcon](https://www.sevcon.com)                          |  
| **AC-DC Converter**      | Vicor               | VBM2400D24-12    | Digi-Key          | 946-2749                   | 1            | $225.00    | [Digi-Key](https://www.digikey.com)                       |  
| **ISOMETER® IR155 3204** | Bender              | IR155 3204       | Bender USA        | IR155 3204                 | 1            | $25.00     | [Bender USA](https://www.bender-usa.com)                  |  
| **Wiring Harness**       | McMaster-Carr       | 7099K12          | McMaster-Carr     | 7099K12                    | 1            | $47.00     | [McMaster-Carr](https://www.mcmaster.com)                 |  
| **Throttle Position Sensor** | Honeywell        | 15TS08-302       | Digi-Key          | 15TS08-302                 | 1            | $40.00     | [Digi-Key](https://www.digikey.com)                       |  

**Total Cost:** $1,599.32  

---

### **Analysis**

The charger subsystem fulfills all necessary specifications, ensuring the accumulator is charged safely and efficiently. The inclusion of **Galvanic Isolation** and **Safety Interlocks** meets the essential Formula SAE safety standards, reducing electrical hazard risks. The integration with the AMS ensures real-time monitoring of the charging process, while the **Temperature Resilience** guarantees reliable performance under varying environmental conditions. This design enables safe, efficient charging and extends the longevity of the accumulator.

---

### **References**

1. Formula SAE, "Formula SAE Electric Rules," SAE International, 2024.  
   Accessed: Nov. 20, 2024. [https://www.sae.org/](https://www.sae.org/)
  
2. Sevcon, "DVT Configuration Software Manual," 2022.  
   Accessed: Nov. 20, 2024. [https://www.sevcon.com](https://www.sevcon.com)

3. Vicor, "AC-DC Converter Specifications," 2023.  
   Accessed: Nov. 20, 2024. [https://www.vicorpower.com](https://www.vicorpower.com)

4. Bender, "ISOMETER® IR155 3204 User Manual," 2021.  
   Accessed: Nov. 20, 2024. [https://www.bender-usa.com](https://www.bender-usa.com)

5. Digi-Key, "Throttle Position Sensor Specifications," 2023.  
   Accessed: Nov. 20, 2024. [https://www.digikey.com](https://www.digikey.com)


---

