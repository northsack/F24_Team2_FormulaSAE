# Shutdown Circuit

## Experiment

### Purpose
To test the shutdown circuit testing that the components do actually open the circuit when it should. The shutdown circuit that is built includes two master switches, the GLV fuse, the BSPD module, inertia switch, three shutdown buttons, and the BOTS switch. Each component will be actuated 3 times to ensure that  

### Procedure
The experiment that will be used to test the shutdown circuit is as follows. The shutdown circuit will be turned on, and then each component will be actuated properly. The BSPD, unlike the other components, cannot be actuated physically only electronically. To test that the BSPD is functioning as needed the two sensor pins on the BSPD will have various voltages applied to them from 0 V to 5 V and then 13.8 V will be applied to the power pin. A datasheet for the BSPD has a truth table that tells when the relay, and shutdown circuit, on the board will be opened or closed. The voltages on the sensor pins will then be set to the conditions described on the truth table and then the BSPD will be powered and the shutdown circuit will be evaluated. This will be done for each of the conditions labeled on the truth table. 

### Data Collection
The data being collected will be the condition of the shutdown circuit after the device under test has been actuated. 

### Trials
Since the shutdown circuit’s data is mostly data on how the switches affect the shutdown circuit only three trials, for each component will be collected. The BSPD’s most common modes of operation will also undergo three trials each. 

## Purpose and Justification
The experiment for the shutdown circuit was designed to ensure that each of the components in the circuit will behave as expected. Since this is a safety circuit it is critical that the components act as they should. All the components when actuated properly should open the shutdown circuit, and this is the data that is being collected. 

## Detailed Procedure
The experiment that will be used to test the shutdown circuit is as follows. The shutdown circuit will be turned on, and then each component will be actuated properly. The BSPD, unlike the other components, cannot be actuated physically only electronically. To test that the BSPD is functioning as needed the two sensor pins on the BSPD will have various voltages applied to them from 0 V to 5 V and then 13.8 V will be applied to the power pin. A datasheet for the BSPD has a truth table that tells when the relay, and shutdown circuit, on the board will be opened or closed. The voltages on the sensor pins will then be set to the conditions described on the truth table and then the BSPD will be powered and the shutdown circuit will be evaluated. This will be done for each of the conditions labeled on the truth table. 

## Expected Results
The expected results will be that the switches will open the shutdown circuit. The BSPD is expected to also open the shutdown circuit, unless the voltage of both of the sensor pins are at or above 4.44 V. The voltage of one sensor pin can be in the 4.44 to 5 volt range as long as the other sensor pin remains in the 0.45 to 4.44 volt range. 

## Actual Results
Since the data is only if the shutdown circuit was disconnected after the component under test is actuated, a 0 will indicate that the shutdown circuit opened and a 1 will indicate that the shutdown circuit remained closed, the starting condition of the shutdown circuit in all trials will be closed (1)

| Part | Trial 1 | Trial 2 | Trial 3 |
|------|---------|---------|---------|
| Grounded Low Voltage Master Switch | 0 | 0 | 0 |
| Inertia Switch | 0 | 0 | 0 |
| Shutdown Buttons 1-3 | SDB 1: 0<br>SDB 2: 0<br>SDB 3: 0 | SDB 1: 0<br>SDB 2: 0<br>SDB 3: 0 | SDB 1: 0<br>SDB 2: 0<br>SDB 3: 0 |
| Broke Over Travel System | 0 | 0 | 0 |
| Tractive System Master Switch | 0 | 0 | 0 |

### BSPD Truth Table

| Sensor 2 Voltage \ Sensor 1 Voltage | 0 V | 0 - 0.45 V | 0.45 - 4.44 V | 4.45 - 5 V |
|--------------------------------------|-----|-------------|----------------|-------------|
| 0 V | 0 | 0 | 0 | 0 |
| 0 - 0.45 V | 0 | 0 | 0 | 0 |
| 0.45 - 4.44 V | 0 | 0 | 1 | 1 |
| 4.45 - 5 V | 0 | 0 | 1 | 0 |

## Interpretation and Conclusions
From the collected data it seems that all the components behave as expected. This is significant because it shows that the shutdown circuit will behave as it is needed when it is built into the car and thus will protect the driver. 

## Summary
While all the components of the shutdown circuit do behave as they should and do meet the success criteria from the conceptual design report it is important to mention that not every component of the shutdown described in the conceptual design is present in our final version of the shutdown circuit. This is because of some issues with purchasing the Insulation Monitoring Device (IMD), and High Voltage Disconnect (HVD). For the IMD a quote request must be submitted before purchasing and getting in contact with the manufacturer is a long process. The HVD was difficult because finding the appropriate disconnect is difficult because the car’s chassis is not completed at the time of this report.
