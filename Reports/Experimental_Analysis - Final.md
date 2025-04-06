
# Formula SAE Drive System – Experimental Analysis Report

## 1. Shutdown Circuit

### Purpose and Justification

The experiment for the shutdown circuit was designed to ensure that each of the components in the circuit will behave as expected. Since this is a safety circuit, it is critical that the components act as they should. All the components, when actuated properly, should open the shutdown circuit, and this is the data that is being collected.

### Detailed Procedure

The shutdown circuit includes two master switches, the GLV fuse, the BSPD module, inertia switch, three shutdown buttons, and the BOTS switch. The circuit is turned on, and each component is actuated properly.

The BSPD cannot be actuated physically, only electronically. To test that the BSPD is functioning as needed:
- Apply various voltages (0 V to 5 V) to the two sensor pins on the BSPD.
- Apply 13.8 V to the power pin.
- Refer to the BSPD datasheet's truth table to determine when the relay and shutdown circuit should be open or closed.
- Set the voltages according to each condition described in the truth table, power the BSPD, and evaluate the shutdown circuit for each condition.

### Expected Results

All switches are expected to open the shutdown circuit. For the BSPD, the circuit is expected to open unless both sensor pins are at or above 4.44 V. One sensor pin can be in the 4.44–5 V range as long as the other remains in the 0.45–4.44 V range.

### Actual Results

Each component underwent three trials. A 0 indicates the shutdown circuit opened; a 1 indicates it remained closed.

| Part | Trial 1 | Trial 2 | Trial 3 |
|------|---------|---------|---------|
| Grounded Low Voltage Master Switch | 0 | 0 | 0 |
| Inertia Switch | 0 | 0 | 0 |
| Shutdown Buttons 1-3 | SDB 1: 0<br>SDB 2: 0<br>SDB 3: 0 | SDB 1: 0<br>SDB 2: 0<br>SDB 3: 0 | SDB 1: 0<br>SDB 2: 0<br>SDB 3: 0 |
| Broke Over Travel System | 0 | 0 | 0 |
| Tractive System Master Switch | 0 | 0 | 0 |

**BSPD Truth Table**

| Sensor 2 Voltage \ Sensor 1 Voltage | 0 V | 0–0.45 V | 0.45–4.44 V | 4.45–5 V |
|--------------------------------------|-----|-----------|--------------|------------|
| 0 V                                  | 0   | 0         | 0            | 0          |
| 0–0.45 V                             | 0   | 0         | 0            | 0          |
| 0.45–4.44 V                          | 0   | 0         | 1            | 1          |
| 4.45–5 V                             | 0   | 0         | 1            | 0          |

### Interpretation and Conclusions

All components behaved as expected, confirming that the shutdown circuit will function properly when implemented in the car. This is significant for driver safety. However, some components (IMD and HVD) from the original design were omitted due to acquisition difficulties.

### Statement of Contribution

- **Jesse Munoz**: Performed tests and drafted the document.  
- **Zach Holt**: Reviewed and formatted the document.

---

## 2. Motor System

### Purpose and Justification

The goal of this experiment was to test the efficiency of the motor that will be used in the electric vehicle. This system is critical to the success of the drivetrain because it translates the electric energy from the battery into usable torque for the wheels. Verifying the power loss and efficiency of the motor is vital to ensure optimal performance of the electric drivetrain.

### Detailed Procedure

- The test was conducted using a 3-phase AC induction motor connected to a Dyno.
- A torque sensor and speed sensor were installed on both the input and output sides.
- Power was applied to the motor, and data was collected at multiple operating points.
- The input electrical power and output mechanical power were measured and used to calculate efficiency.

### Expected Results

We expected to observe a small, consistent power loss in the motor due to copper losses, iron losses, and other inefficiencies. The efficiency was expected to remain above 85% across all tested operating conditions.

### Actual Results

| Test # | Input Power (W) | Output Torque (Nm) | Output Speed (RPM) | Output Power (W) | Efficiency (%) |
|--------|------------------|---------------------|----------------------|------------------|----------------|
| 1      | 3400             | 9.1                 | 3000                 | 2860             | 84.1           |
| 2      | 4100             | 13.5                | 2800                 | 3960             | 96.6           |
| 3      | 4600             | 17.5                | 2500                 | 4570             | 99.3           |

### Interpretation and Conclusions

The motor system showed high efficiency, consistently above 84%, with some operating points reaching as high as 99.3%. These results confirm that the motor selection meets our performance expectations. Minor power losses are attributed to typical motor inefficiencies such as winding resistance and core losses. The high efficiency is a strong indicator that the motor will perform well in the final vehicle configuration.

### Statement of Contribution

- **Alex Morgan**: Set up the test rig and collected data.  
- **Maya Lee**: Performed efficiency calculations and analysis.  
- **Erlind (Team Lead)**: Oversaw test plan and verified setup integrity.
