# Formula SAE Electric - Motor

**Erlind Boraj**  
*Tennessee Technological University, ECE Department*  
**Tennessee Tech Motorsports**  
Cookeville, TN, USA  
[eboraj42@tntech.edu](mailto:eboraj42@tntech.edu)

# Function of the Subsystem

The motor subsystem of the Formula SAE electric car serves as the primary source of propulsion, converting electrical energy from the battery into mechanical energy to drive the wheels. The motor ensures the vehicle achieves the desired performance metrics, including acceleration, top speed, and torque. Aligned with the team's conceptual design, the motor integrates with the powertrain and the control systems, contributing to a lightweight and efficient design that meets competition requirements. Moreover, the motor must operate reliably under the conditions of an FSAE race, including 4 hours of total racing time, rapid acceleration, and 60-75 mph speeds.

# Specifications and Constraints

#### Weight Constraints
The team targeted a car payload of 400 lbs, significantly lower than the 600 lbs payload seen in many other FSAE teams' designs. This necessitated a lightweight motor to avoid overburdening the vehicle and prevent the need for structural modifications to the already designed chassis and other components. Keeping the motor's weight in check was essential to maintaining the overall structural integrity and balance of the car.

#### Performance Specifications
The motor was required to deliver at least 60 horsepower and 60 foot-pounds of torque. These specifications were crucial to ensure the car's competitive performance in acceleration, handling, and speed.

#### Dimensional Fit
The motor had to be compatible with the pre-designed chassis. Any deviation in size or mounting requirements would have led to costly redesigns and fabrication delays, which the team aimed to avoid.

#### Economic Considerations
Cost was a significant constraint. The team successfully negotiated a 20% discount from the manufacturer. This decision exemplifies the balance between performance and budget—a critical consideration in engineering projects.

#### Standards and Ethical Constraints
The motor had to comply with FSAE technical standards, ensuring safety and adherence to competition rules. Additionally, the team aimed to minimize the environmental impact by selecting an electric motor over traditional combustion engines, aligning with broader ethical and sustainability goals.

#### Integration with Other Subsystems
The motor's compatibility with the electric drivetrain and battery system posed additional constraints. Any changes to the motor specifications would require recalibration of the control systems, increasing complexity.

# Overview of Proposed Solution

The proposed TSAL subsystem utilizes hardware-based activation triggered by the shutdown circuit and high-voltage connections. The TSAL integrates directly with the accumulator and the DC power input from the shutdown circuit to ensure precise activation when the tractive system is live. It automatically illuminates when the tractive system voltage exceeds 60V and turns off when the shutdown circuit disables the high-voltage system. This design complies with all Formula SAE Electric safety requirements, ensuring reliability and safety during operation and maintenance while maintaining a straightforward and robust hardware configuration.

# Interface with Other Subsystems

The Motor Subsystem interfaces with various electrical and mechanical systems to deliver power to the drivetrain while maintaining compatibility with the vehicle's design and operational requirements. These connections ensure efficient energy transfer, precise control, and integration with the overall system.

#### Inputs

- **High-Voltage Input (Accumulator):**  
  The motor receives power directly from the accumulator through the motor controller. The high-voltage DC power is converted to three-phase AC to drive the motor efficiently.

- **Control Signals (Motor Controller):**  
  The motor relies on input signals from the motor controller to regulate speed, torque, and direction. These signals are derived from inputs such as throttle position, torque requests, and feedback from sensors.

- **Feedback Signals (Encoder):**  
  The motor receives position and velocity feedback from the sine and cosine encoders, which are critical for precise motor control and synchronization.

#### Outputs

- **Mechanical Power:**  
  The motor delivers mechanical rotational power to the drivetrain, propelling the vehicle forward. This output is characterized by torque and speed, meeting the specified performance requirements.

- **Electrical Feedback (Thermal Sensor):**  
  The motor outputs temperature data through its thermistor to monitor and prevent overheating. This information is used by the motor controller to adjust performance or shut down the system if necessary.

#### Communication and Data Transfer

-**Method of Communication:**
The motor communicates with the motor controller through analog and digital signals, such as encoder feedback and temperature data. Control signals are sent via direct wiring to ensure high-speed, reliable communication.

-**Data Transmitted:**
Feedback data includes encoder signals (sine and cosine waveforms) for position and speed, and thermistor signals for temperature monitoring. These are processed by the motor controller to optimize performance and ensure safe operation.

# BOM

| Component Name       | Type            | Qty | Price ($) | Seller   |
|----------------------|-----------------|-----|-----------|----------|
| 2022 Zero FXE                | Motor        | 1   | 11195     | Max Motorsports   |
| **Total**           |                 |     | **11195**|          |

**Note:** This BOM only shows the original price of the bike. It does not account for discounts give to academic projects, or depriciation of the bike at the time of purchase.This BOM does not account for spare parts. Quatities in the table represent the minimum quantity needed. The BOM does not account for shipping cost.

# Analysis

The motor subsystem is designed to fulfill the performance, reliability, and safety requirements of the Formula SAE electric vehicle, adhering to all specified constraints while ensuring optimal functionality. The following analysis demonstrates how the motor design satisfies the intended functions and constraints.

#### Compliance with Performance Constraints

- #### Three-Phase Input Design:
1. The motor receives power via three-phase AC inputs (Phase A, Phase B, and Phase C), providing the rotating magnetic field required for efficient mechanical energy conversion. 
2. Synchronization and control of these phases are handled by the motor controller, ensuring balanced operation that prevents overheating or stress on the motor windings. This satisfies the need for reliable energy conversion under varying torque and speed demands.

- #### Torque and Power Output:
1. The motor subsystem meets the performance specifications of 60 horsepower and 60 ft-lbs of torque. This ensures sufficient mechanical power for the vehicle's propulsion while maintaining compliance with Formula SAE performance guidelines. 
2. The use of sine and cosine encoders enables high-resolution feedback, ensuring precise rotor position and speed control. This enhances torque generation and smooth operation, critical for competitive racing scenarios.

#### Safety and Thermal Management

- #### Thermistor for Temperature Monitoring:
1. The inclusion of a thermistor ensures continuous monitoring of the motor's operating temperature.
2. The thermistor provides analog feedback to the motor controller, which can adjust power output or initiate a shutdown if temperatures exceed safe limits. This feature mitigates risks associated with overheating, extending the motor's operational life and maintaining safety.

- #### Hardware-Driven Safety:
1. The system relies on hardware-based feedback from encoders and the thermistor, reducing dependency on software and minimizing the risk of failure due to software malfunctions. This ensures consistent safety and performance under all operating conditions.

#### Efficiency and Precision

- #### Sine and Cosine Encoders:
1. The sine and cosine encoders provide continuous analog signals corresponding to the rotor’s angular position. Their high-resolution feedback loops allow fine interpolation, improving position accuracy and reducing errors compared to standard encoders. 
2. This precision ensures smoother control during acceleration and deceleration, vital for maintaining stability and efficiency in high-performance scenarios.

- #### Dynamic Phase Control:
1. The motor controller dynamically adjusts current delivery to the three-phase inputs based on feedback from the encoders. This feature optimizes energy use, reduces losses, and enhances the drivetrain's responsiveness, directly contributing to better vehicle performance.

### Integration with Vehicle Design

- #### Physical and Electrical Integration:
1. The motor’s compact size and compatibility with the existing chassis design eliminate the need for structural modifications. This ensures seamless integration while maintaining weight constraints and overall vehicle balance. 
2. Its electrical interface with the accumulator and motor controller aligns with the overall system architecture, simplifying system assembly and troubleshooting.

- #### Regulatory Compliance:
1. The subsystem adheres to Formula SAE safety and performance regulations, ensuring the vehicle’s eligibility for competition. Features such as high-voltage isolation and thermal management contribute to meeting these standards.

   
# References

1. Formula SAE, “Formula SAE Rules 2024 Version 1.0,” *fsaeonline.com*,  
   [https://www.fsaeonline.com/cdsweb/gen/DownloadDocument.aspx?DocumentID=369d01c0-589d-4ebe-b8d4-b07544f4a52b](https://www.fsaeonline.com/cdsweb/gen/DownloadDocument.aspx?DocumentID=369d01c0-589d-4ebe-b8d4-b07544f4a52b) (accessed Nov 15, 2024).

2. Wisconsin Formula SAE Racing, "Electrical System Form FSAE-E2018," *wisconsinracing.org*,  
   [https://www.wisconsinracing.org/wp-content/uploads/2020/10/2018_ESF_Submission.pdf](https://www.wisconsinracing.org/wp-content/uploads/2020/10/2018_ESF_Submission.pdf) (accessed Nov 21, 2024).
   
3. Motion Control Tips, "What is a sine encoder (aka sine-cosine encoder)?", Oct. 16, 2019. [Online]. Available: https://www.motioncontroltips.com/what-is-a-sine-encoder-aka-sine-cosine-encoder/.

4. Control.com, "Encoders vs. Resolvers: Applications and Characteristics." [Online]. Available: https://www.control.com/technical-articles/encoders-vs-resolvers-applications-and-characteristics/.


