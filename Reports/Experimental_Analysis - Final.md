
# Formula SAE Drivetrain – Experimental Analysis Report

## Experimental Analysis of Shutdown Circuit

#### 1. Purpose and Justification

To test the shutdown circuit, the goal was to verify that each component properly opens the circuit when triggered. The shutdown circuit includes two master switches, the GLV fuse, the BSPD module, the inertia switch, three shutdown buttons, and the BOTS switch. Each component will be actuated three times to ensure consistent and reliable operation.

#### 2. Detailed Procedure
The experiment that will be used to test the shutdown circuit is as follows. The shutdown circuit will be turned on, and then each component will be actuated properly. The BSPD, unlike the other components, cannot be actuated physically only electronically. To test that the BSPD is functioning as needed the two sensor pins on the BSPD will have various voltages applied to them from 0 V to 5 V and then 13.8 V will be applied to the power pin. A datasheet for the BSPD has a truth table that tells when the relay, and shutdown circuit, on the board will be opened or closed. The voltages on the sensor pins will then be set to the conditions described on the truth table and then the BSPD will be powered and the shutdown circuit will be evaluated. This will be done for each of the conditions labeled on the truth table. 

Data Collection: The data being collected will be the condition of the shutdown circuit after the device under test has been actuated. 
Trials: Since the shutdown circuit’s data is mostly data on how the switches affect the shutdown circuit only three trials, for each component will be collected. The BSPD’s most common modes of operation will also undergo three trials each. 

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
While all the components of the shutdown circuit do behave as they should and do meet the success criteria from the conceptual design report it is important to mention that not every component of the shutdown described in the conceptual design is present in our final version of the shutdown circuit. This is because of some issues with purchasing the Insulation Monitoring Device (IMD), and High Voltage Disconnect (HVD). For the IMD a quote request must be submitted before purchasing and getting in contact with the manufacturer is a long process. The HVD was difficult because finding the appropriate disconnect is difficult because the car’s chassis is not completed at the time of this report.

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

- The motor was connected to the controller and powered by the limited supply.
- The throttle was pressed slowly until grinding noise began, signaling low current-induced instability. Throttle was then released to avoid damage.
- Tests were repeated at constant throttle positions to ensure consistency.
- All data was captured using the motor controller’s built-in telemetry.

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

#### Test 2: Maximum Torque Recording
"Maximum torque" refers to the highest torque recorded by the motor controller when gradually increasing the throttle until the motor reaches its malfunction point. During this process, motor speed behavior was observed, and torque and voltage were recorded at the peak point. The highest voltage and torque values displayed by the motor controller software at this point were designated as max voltage and max torque.

| Run | Max Throttle Voltage (V) | Max Torque (N-m) |
|-----|---------------------------|-----------------|
| 1   | 0.358                     | 2.3125          |
| 2   | 0.299                     | 1.3140          |
| 3   | 0.301                     | 1.3125          |
| 4   | 0.326                     | 1.3125          |

**Averages:**
- Max Throttle Voltage: 0.321V  
- Max Torque: 1.5629 N-m  

#### Test 3: Proportional Torque vs. Throttle

The objective was to determine whether the increase in torque is proportional to the increase in throttle input, with throttle position represented by throttle voltage. This test evaluates whether torque increases at the same rate as throttle voltage—for example, whether doubling the throttle input results in doubled torque. During each test run, the throttle was held at a stable position and pressed the same fixed distance. This distance was an arbitrary value between zero and full throttle.


| Run | Throttle Voltage (V) | Torque (N-m) |
|-----|-----------------------|-------------|
| 1   | 0.315                 | 0.4375      |
| 2   | 0.315                 | 0.5628      |
| 3   | 0.315                 | 0.4375      |
| 4   | 0.315                 | 0.5625      |

**Averages:**
- Throttle Voltage: 0.315V  
- Torque: 0.5001 N-m  

**Change in Torque Between Tests 2 and 3:** 3.125  
**Change in Throttle Voltage:** ~1.02  

#### Test 4: Temperature Monitoring

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

Graham Robinson: Reviewed and Revised the report.
