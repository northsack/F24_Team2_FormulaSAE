# Experimental Analysis of Motor Subsystem

---

## 1. Purpose and Justification
The purpose of this experimental analysis is to evaluate the operational performance of the motor subsystem under unloaded conditions. Since a full-power battery is currently unavailable, tests were conducted using a limited 6-amp current supply to verify that the motor functions correctly within the given constraints.

### Critical Success Criteria:
- Verification that the motor operates when supplied with available power.
- Assessment of motor speed and response under limited current conditions.
- Validation of sensor outputs (temperature, RPM, throttle) for reliability.
- Identification of any abnormalities or inefficiencies in motor operation.

These tests serve as a foundational baseline, allowing for future comparison once a full-power battery is available.

---

## 2. Experimental Procedure

### Equipment Used:
- Zero Motorcycles FXE Motor
- Motor Controller
- 104V Power Supply (limited to ~6A)
- Ammeter and Voltmeter
- Oscilloscope (for future signal verification)
- Motor Controller Software

### Setup:
- The motor was connected to the controller and powered by the limited supply.
- The throttle was pressed slowly until a grinding noise began, signaling low current-induced instability. The throttle was then released to prevent potential damage.
- Tests were repeated at constant throttle positions to ensure consistency.
- All data was captured using the motor controller’s built-in telemetry.

### Safety:
- The test area was cleared of obstructions.
- The motor was unloaded during all tests.

---

## 3. Expected Results
Given the system’s design for much higher current operation (up to 440A), we expected:
- Motor would spin but not reach high speeds.
- Torque values would be very low.
- Temperature would not rise significantly.
- Torque would increase proportionally with throttle until reaching the low-current limit.

We expected deviations from ideal operation due to the restricted current input.

---

## 4. Actual Results

### Test 1: Basic Functionality Check
The motor successfully spun at low throttle levels without load. Grinding began when the throttle was pushed further, confirming the motor's current needs exceeded the power supply’s limit.

### Test 2: Maximum Torque Recording

| Run | Max Throttle Voltage (V) | Max Torque (Nm) |
|-----|--------------------------|------------------|
| 1   | 0.358                    | 2.3125           |
| 2   | 0.299                    | 1.3140           |
| 3   | 0.301                    | 1.3125           |
| 4   | 0.326                    | 1.3125           |

**Averages:** Max Throttle Voltage: 0.321V, Max Torque: 1.5629 Nm

### Test 3: Proportional Torque vs. Throttle

| Run | Throttle Voltage (V) | Torque (Nm) |
|-----|----------------------|-------------|
| 1   | 0.315                | 0.4375      |
| 2   | 0.315                | 0.5628      |
| 3   | 0.315                | 0.4375      |
| 4   | 0.315                | 0.5625      |

**Averages:** Throttle Voltage: 0.315V, Torque: 0.5001 Nm

**Change in Torque Between Tests 2 and 3:** 3.125  
**Change in Throttle Voltage:** ~1.02

### Test 4: Temperature Monitoring
Temperature was recorded via the motor controller. It remained at a constant 36°C throughout all tests. This is expected because the motor was operating at only a fraction of its rated power. Significant heat generation is unlikely until full-load conditions are tested.

---

## 5. Reference - Motor Controller Specifications (from controller software)

### Traction Baseline Profile


