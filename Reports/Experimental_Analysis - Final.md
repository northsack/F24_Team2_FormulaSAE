
# Formula SAE Drivetrain – Experimental Analysis Report

## Experimental Analysis of Shutdown Circuit

#### 1. Purpose and Justification

To test the shutdown circuit, the goal was to verify that each component properly opens the circuit when triggered. The shutdown circuit includes two master switches, the GLV fuse, the BSPD module, the inertia switch, three shutdown buttons, and the BOTS switch. Each component will be actuated three times to ensure consistent and reliable operation.

#### 2. Detailed Procedure
The experiment used to test the shutdown circuit is as follows. The shutdown circuit will be turned on, and each component will then be actuated properly. The BSPD, unlike the other components, cannot be actuated physically—only electronically. To test that the BSPD is functioning correctly, various voltages ranging from 0 V to 5 V will be applied to its two sensor pins, followed by applying 13.8 V to the power pin. The BSPD datasheet includes a truth table that specifies when the relay—and thus the shutdown circuit—should open or close. The sensor pin voltages will be set according to the conditions listed in the truth table, the BSPD will be powered, and the shutdown circuit will be evaluated. This process will be repeated for each condition listed in the truth table.

**Data Collection:**  
The data collected will indicate the state of the shutdown circuit after each component is actuated.

**Trials:**  
Since the focus is on how each component affects the shutdown circuit, three trials will be conducted for each one. The BSPD’s most common modes of operation will also be tested with three trials each.


#### 3. Expected Results
The expected result is that each switch will successfully open the shutdown circuit. The BSPD is also expected to open the circuit unless both of its sensor pins are at or above 4.44 V. It is acceptable for one sensor pin to be in the 4.44 to 5 V range, as long as the other remains between 0.45 and 4.44 V.

#### 4. Actual Results
Since the data only reflects whether the shutdown circuit was disconnected after the tested component was actuated, a value of 0 indicates that the shutdown circuit opened, while a value of 1 indicates that it remained closed. The initial condition of the shutdown circuit in all trials will be closed (1).


| Part | Trial 1 | Trial 2 | Trial 3 |
|------|---------|---------|---------|
| Grounded Low Voltage Master Switch | 0 | 0 | 0 |
| Inertia Switch | 0 | 0 | 0 |
| Shutdown Buttons 1-3 | SDB 1: 0<br>SDB 2: 0<br>SDB 3: 0 | SDB 1: 0<br>SDB 2: 0<br>SDB 3: 0 | SDB 1: 0<br>SDB 2: 0<br>SDB 3: 0 |
| Broke Over Travel System | 0 | 0 | 0 |
| Tractive System Master Switch | 0 | 0 | 0 |

#### BSPD Truth Table

| Sensor 2 Voltage \ Sensor 1 Voltage | 0 V | 0 - 0.45 V | 0.45 - 4.44 V | 4.45 - 5 V |
|--------------------------------------|-----|-------------|----------------|-------------|
| 0 V | 0 | 0 | 0 | 0 |
| 0 - 0.45 V | 0 | 0 | 0 | 0 |
| 0.45 - 4.44 V | 0 | 0 | 1 | 1 |
| 4.45 - 5 V | 0 | 0 | 1 | 0 |

#### 5. Interpretation and Conclusions

The collected data indicates that all components behaved as expected. This is significant because it confirms that the shutdown circuit will function properly when integrated into the car, ensuring driver safety.

#### 6. Summary
While all the components of the shutdown circuit do behave as they should and do meet the success criteria from the conceptual design report it is important to mention that not every component of the shutdown described in the conceptual design is present in our final version of the shutdown circuit. This is because of some issues with purchasing the Insulation Monitoring Device (IMD), and High Voltage Disconnect (HVD). For the IMD a quote request must be submitted before purchasing and getting in contact with the manufacturer is a long process. Finding the appropriate HVD is difficult because the car’s chassis is not completed at the time of this report.

## Experimental Analysis of Motor Subsystem

### 1. Purpose and Justification

The purpose of this experimental analysis is to evaluate the operational performance of the motor subsystem under unloaded conditions. Since a full-power battery is currently unavailable, tests were conducted using a limited 6-amp current supply to verify that the motor functions correctly within the given constraints.

**Critical Success Criteria:**

- Verification that the motor operates when supplied with available power.
- Assessment of motor speed and response under limited current conditions.
- Validation of sensor outputs (temperature, torque, throttle) for reliability.
- Identification of any abnormalities or inefficiencies in motor operation.

These tests serve as a foundational baseline, allowing for future comparison once a full-power battery is available.

### 2. Experimental Procedure

**Equipment Used:**

- Zero Motorcycles FXE Motor  
- Motor Controller  
- 104V Power Supply (limited to ~6A)  
- Ammeter and Voltmeter  
- Oscilloscope (for future signal verification)  
- Motor Controller Software  

**Setup:**

- The motor was connected to the controller in the same way as shown in our wiring diagrams and powered by the limited supply.
- The motor controller was connected to a laptop for monitoring purposes. The motor controller software can be used to get measurements when the motor is running.
- The throttle was pressed slowly until grinding noise began, signaling low current-induced instability. Throttle was then released to avoid damage.
- Tests were repeated at constant throttle positions to ensure consistency.
- All data was captured using the motor controller’s built-in telemetry.

- For the shutdown circuit, all components were connected as shown in the wiring diagram.
- Each component was tested individually 3 separate times to ensure full capability to open the circuit if triggered.

**Safety:**

- The test area was cleared of obstructions.
- The motor was unloaded during all tests.

### 3. Expected Results

Given the system’s design for much higher current operation (up to 440A), we expected:

- Motor would spin but not reach high speeds.
- Torque values would be very low.
- Temperature would not rise significantly.
- RPM and torque would increase linearly with throttle until reaching the low-current limit.

**Traction Baseline Profile:**

- Max Forward Speed: 6050 rpm  
- Max Reverse Speed: 100 rpm  
- Ramp Up Rate During Drive: 7000 rpm/s  
- Ramp Down Rate During Drive: 1000 rpm/s  

**Local Motor Limits:**

- Max Torque: 100% of peak  
- Current Limit: 440A RMS  
- Peak Torque: 152 N-m  
- Max Motor Speed: 6100 rpm  
- Overspeed Protection: 8000 rpm  

These values indicate the motor's full capability. Compared to our low-power test (6A), the motor is vastly underutilized. Therefore, results seen here are only partial indicators of real-world performance.

### 4. Actual Results

#### Test 1: Basic Functionality Check

The motor successfully spun at low throttle levels without load. Grinding began when the throttle was pushed further, confirming the motor's current needs exceeded the power supply’s limit.

#### Test 2: Throttle Pedal Displacement vs Throttle Voltage

Using spacer with known, or measured thickness, we held the Throttle pedal stable at different displacemnts. The throttle voltage was then meausured through an oscilloscope to determine the rlationship between them.

![image](https://github.com/user-attachments/assets/81486fcb-98f1-4de0-b93e-4ee5fae0c880)


The graph shows the relationship between Throttle Pedal Displacement (mm) and Throttle Voltage (V). As expected, the voltage increases with pedal displacement, reflecting the progressive response of the throttle position sensor. 

The data demonstrates strong linearity, with the calculated R-squared value indicating a high percentage alignment to a linear trend. The voltage consistently increases with displacement, and the linear regression closely approximates the observed values. This confirms the tested data is both reliable and exhibits a strong linear relationship.
In order to improve the linearity and address the errors, some remeasuremnts were done (shown in graph below).
![image](https://github.com/user-attachments/assets/b8e4d0df-edee-4246-afc0-80259cec1272)
The new graph shows a higher linearity of 99.91%. Factors that affect the linearity include equipment imperfections and measurement imperfections. The testing was done using spacers which were not made to correctly fit the gap between the throttle pedal and the displacement screw on the throttle pedal. Therefore, the thickness of the measured spacer may not match exactly the perpendicular distance of the throttle displacement (distance from screw's resting position to the displaced screw position). The power supply used is also not what is meant to power the throttle; therefore, there may be imperfections once the throttle is pressed to its max or barely moved from the 0 position, which will justify the slight imperfect voltage levels at the beginning and end of the graphed line.

#### Test 3: Temperature Monitoring

Temperature was recorded via the motor controller. It remained at a constant 36°C throughout all tests. This is expected because the motor was operating at only a fraction of its rated power. Significant heat generation is unlikely until full-load conditions are tested.


### 5. Interpretation and Conclusions

- **Motor Operation:** The motor operates under minimal conditions. Its successful activation confirms fundamental functionality.
- **Limited Torque:** The torque values measured (~1.5 N-m max) are less than 1% of the rated 152 N-m. This confirms that the current supply is insufficient to push the motor toward its full capabilities.
- **Temperature:** No change was observed. This is expected given the low power usage. Future tests should re-examine thermal behavior.
- **Throttle-Torque Relationship:** There is a roughly proportional relationship between throttle and torque, but full validation will require higher current levels.

### 6. Summary
The motor subsystem was tested under limited current conditions to verify basic functionality and collect baseline data. Using a 104V power supply limited to 6A, the motor successfully activated and responded to throttle inputs, though grinding noises at higher throttle levels indicated insufficient current. Maximum recorded torque was approximately 1.56 N-m, significantly below the rated 152 N-m, and temperature remained stable at 36°C. The throttle-to-torque relationship appeared roughly proportional, though full validation requires higher current tests. These results confirm that the motor is operational and establish a foundation for future high-power evaluations.

## Statement of Contribution
Jesse Munoz: Performed tests on each part of the shutdown circuit as well as drafted the experimental analysis document.

Erlind Boraj: Performed tests on the motor and reviewed the document.

Zach Holt: Reviewed document and formatted into markdown.

Evan Morse: Performed tests on the motor.

Graham Robinson: Reviewed and revised the report.
