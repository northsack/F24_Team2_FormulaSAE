# Shutdown Circuit

## Experiment

### Purpose
To test the shutdown circuit to ensure that the components open the circuit when they should. The shutdown circuit includes:
- Two master switches
- The GLV fuse
- The BSPD module
- Inertia switch
- Three shutdown buttons
- The BOTS switch

Each component will be actuated 3 times to verify proper operation.

### Procedure
1. Power on the shutdown circuit.
2. Actuate each component properly.
3. The BSPD cannot be actuated physically—only electronically.
   - Apply various voltages (0 V to 5 V) to the two sensor pins on the BSPD.
   - Apply 13.8 V to the power pin.
   - Refer to the BSPD datasheet truth table to determine expected behavior.
4. Set sensor pin voltages to match truth table conditions.
5. Evaluate shutdown circuit behavior under each condition.

### Data Collection
- Record the condition of the shutdown circuit after each device is actuated.

### Trials
- Each component: 3 trials.
- BSPD: 3 trials for each common mode of operation.

---

## Purpose and Justification

The experiment is designed to ensure each component behaves as expected in this safety-critical circuit. Proper actuation of any component should open the shutdown circuit.

---

## Detailed Procedure

(Same as earlier procedure, repeated for emphasis in the original.)

1. Turn on the shutdown circuit.
2. Actuate each component.
3. For BSPD:
   - Apply 0–5 V to sensor pins.
   - Apply 13.8 V to the power pin.
   - Use the truth table to guide sensor conditions.
   - Observe the state of the shutdown circuit for each condition.

---

## Expected Results

- All switches should open the shutdown circuit.
- BSPD will open the circuit unless **both sensor pins are ≥ 4.44 V**.
- One sensor pin may be between **4.44–5 V** as long as the other stays between **0.45–4.44 V**.

---

## Actual Results

> 0 = Shutdown circuit opened  
> 1 = Shutdown circuit remained closed

**Initial condition of the shutdown circuit in all trials: 1 (closed)**

| Part                          | Trial 1 | Trial 2 | Trial 3 |
|-------------------------------|---------|---------|---------|
| Grounded Low Voltage Master Switch | 0       | 0       | 0       |
| Inertia Switch                | 0       | 0       | 0       |
| Shutdown Buttons 1–3         |         |         |         |
| - SDB 1                      | 0       | 0       | 0       |
| - SDB 2                      | 0       | 0       | 0       |
| - SDB 3                      | 0       | 0       | 0       |
| Broke Over Travel System     | 0       | 0       | 0       |
| Tractive System Master Switch| 0       | 0       | 0       |

**BSPD Truth Table Behavior**

| Sensor 1 Voltage \ Sensor 2 Voltage | 0 V | 0–0.45 V | 0.45–4.44 V | 4.45–5 V |
|-------------------------------------|-----|-----------|--------------|-----------|
| 0 V                                 | 0   | 0         | 0            | 0         |
| 0–0.45 V                            | 0   | 0         | 0            | 0         |
| 0.45–4.44 V                         | 0   | 0         | 1            | 1         |
| 4.45–5 V                            | 0   | 0         | 1            | 0         |

---

## Interpretation and Conclusions

All components behaved as expected, confirming the shutdown circuit will function reliably in the vehicle and enhance driver safety.

---

## Summary

All tested components of the shutdown circuit meet the success criteria from the conceptual design report. However, not all originally planned components were included:

- **IMD (Insulation Monitoring Device)**: Purchase required a manufacturer quote and lengthy contact process.
- **HVD (High Voltage Disconnect)**: Hard to specify without a completed car chassis.

---

