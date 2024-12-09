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

The motor controller selected for this electric powertrain was chosen based on its compliance with Formula SAE specifications, as supported by manufacturer datasheets and calculations. 

The controller integrates essential safety features, such as thermal and overcurrent protection, verified by operational limits listed in the datasheet. Field-Oriented Control (FOC) algorithms enhance dynamic torque and speed regulation, as evidenced by the controller's detailed specifications. Calculations confirming the controller’s capacity to handle the system’s voltage, current, and power align with the vehicle's tractive system requirements. Additionally, its cooling system, designed for efficient heat dissipation, ensures consistent performance under demanding conditions, validated through the manufacturer’s testing data.

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

| **Component Name**          | **Manufacturer** | **Part Number**  | **Distributor**      | **Distributor Part Number** | **Quantity** | **Price**   | **URL**                                                                                                                                       |  
|-----------------------------|------------------|------------------|----------------------|-----------------------------|--------------|-------------|-----------------------------------------------------------------------------------------------------------------------------------------------|  
| **Size 4 Gen 4.5 Controller** | Sevcon           | 60-07009         | Koup's Cycle Shop    | 60-07009                   | 1            | $1,078.84   | [Zero Motorcycles Controller](https://shop.koups.com/products/zero-motorcycles-controller-size-4-gen-4-5-sevcon-special-order-60-07009)     |  
| **Wiring Harness**           | McMaster-Carr    | 7099K12          | McMaster-Carr        | 7099K12                    | 1            | $47.00      | [McMaster-Carr Wiring Harness](https://www.mcmaster.com/products/wire-assortments/wire-assortments-7/)                                       |  

**Total Cost:** $1,125.84  

---

#### **Analysis**

To achieve 60 mph, the motor needs to operate at approximately 4500 RPM based on a 4:1 gear ratio and an 18-inch tire diameter. The Zero FXE motor, paired with the controller, is designed to operate efficiently up to 6000 RPM, providing a comfortable margin for this speed.

Also, at 60 mph, the power demand from aerodynamic drag and rolling resistance is calculated to be around 22 kW. The motor controller, with a peak output of 38.8 kW, easily meets this requirement, ensuring sufficient reserve power for acceleration or changes in load conditions.

In addition, the controller uses advanced field-oriented control (FOC) algorithms to regulate torque and speed, ensuring precise and reliable operation. This not only achieves the required speed but also maximizes energy efficiency and driver responsiveness under varying conditions.

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
| **Charger Unit**         | Zero Motorcycles | Quick Charger | Zero Motorcycles | 6585-503-000               | 1            | $775.00    | [Zero Motorcycles Quick Charger](https://zeromotorcycles.com/accessories/products/quick-charger) |  
| **Sevcon Gen4 Programming Cable** | Sevcon      | N/A              | Electric Drive Engineering | N/A                        | 1            | $426.18    | [Sevcon Gen4 Programming Cable](https://electricdriveengineering.com.au/product/sevcon-gen4-programming-cable/)  |  
| **AC-DC Converter**      | The Supply Net      | WSAE-12V125A     | The Supply Net    | WSAE-12V125A               | 1            | $240.00    | [AC-DC 12V 125A Power Brick with WSAE Connector](https://www.thesupplynet.com/acdc-12v-125a-power-brick-wsae-connector?srsltid=AfmBOopqHRMiYitNzeE8L6awpIhihYKF9gfj_LipGCbgrjFatGHNVgUw) |  
| **ISOMETER® IR155 3204** | Bender              | IR155 3204       | Bender USA        | IR155 3204                 | 1            | $25.00     | [Bender USA](https://www.benderinc.com/products/ground-fault-monitoring-ungrounded/isometer-ir155-03-04-series/)                  |  
| **Wiring Harness**       | Electric Drive Engineering | Dual Signal Throttle | Electric Drive Engineering | N/A                        | 1            | $262.67    | [Sevcon Wiring Harness](https://electricdriveengineering.com.au/product/sevcon-wiring-harness-dual-signal-throttle/) |  
| **Throttle Position Sensor** | Haltech        | HT-010402        | Haltech           | HT-010402                  | 2            | $160.00     | [Haltech Throttle Position Sensor](https://www.haltech.com/product/ht-010402-throttle-position-sensor-grey/?srsltid=AfmBOoo3lPV1Rw_vwTMvW8oLD3R7tEIcO57HCTEhnnryN1GeVIJoi4_w)                       |  

**Total Cost:** $2,048.85  

---

### **Analysis**

The charger subsystem meets Formula SAE safety and performance specifications, supported by manufacturer documentation and preliminary calculations. The inclusion of **Galvanic Isolation** is verified in the datasheet [2]. This demonstrates compliance with electrical safety standards by mitigating risks of leakage currents. **Safety Interlocks** are validated through design schematics, ensuring proper disengagement during faults. Compatibility with the AMS for real-time monitoring is established through protocol alignment specified in the manufacturer's manual. Lastly, **Temperature Resilience** is substantiated by the operational range outlined in the datasheet, confirming reliability under competition conditions.

---

### **References**

1. Formula SAE, "Formula SAE Electric Rules," SAE International, 2024. Accessed: Nov. 20, 2024. [https://www.sae.org/](https://www.sae.org/)  

2. Zero Motorcycles, "Quick Charger Specifications," 2023. Accessed: Nov. 20, 2024. [https://zeromotorcycles.com](https://zeromotorcycles.com)  

3. Sevcon, "DVT Configuration Software Manual," 2022. Accessed: Nov. 20, 2024. [https://www.sevcon.com](https://www.sevcon.com)  

4. Bender, "ISOMETER® IR155 3204 User Manual," 2021. Accessed: Nov. 20, 2024. [https://www.bender-usa.com](https://www.bender-usa.com)  

5. Electric Drive Engineering, "Sevcon Wiring Harness Specifications," 2023. Accessed: Nov. 20, 2024. [https://electricdriveengineering.com](https://electricdriveengineering.com)  

6. Haltech, "Throttle Position Sensor Datasheet," 2023. Accessed: Nov. 20, 2024. [https://www.haltech.com](https://www.haltech.com)

7. Sevcon, "Size 4 Gen 4.5 Controller," Part No. 60-07009. Accessed: Dec. 2, 2024. [Koup's Cycle Shop](https://shop.koups.com/products/zero-motorcycles-controller-size-4-gen-4-5-sevcon-special-order-60-07009).  

8. McMaster-Carr, "Wiring Harness, 7099K12," 2024. Accessed: Dec. 2, 2024. [McMaster-Carr Wiring Harness](https://www.mcmaster.com/products/wire-assortments/wire-assortments-7/).   
---

