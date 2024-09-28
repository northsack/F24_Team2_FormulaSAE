_Formula SAE Electric Vehicle Project Proposal_

Evan Morse, Jesse Munoz, Zach Holt, Erlind Boraj, Graham Robinson  
Tennessee Technological University, ECE Department  
Tennessee Tech Motorsports  
Cookeville, TN, USA  
[emorse42@tntech.edu](mailto:emorse42@tntech.edu), [jdmunoz42@tntech.edu](mailto:jdmunoz42@tntech.edu), [eboraj42@tntech.edu](mailto:eboraj42@tntech.edu), [zsholt42@tntech.edu](mailto:zsholt42@tntech.edu), [glrobinson42@tntech.edu](mailto:glrobinson42@tntech.edu)

_Abstract_—This project aims to assist Tennessee Tech’s Motorsports club by designing the powertrain, controls, and power systems for the club’s first electric vehicle. This project, for both the senior design team and Tennessee Tech Motorsports, serves as an introduction to the development of electric vehicles by exposing engineering students to the rapidly developing field of electric vehicles.

# Define Problem

1. _Background_

The goal of this project is to design the power system and powertrain system of an electric formula SAE car for Tennessee Tech’s Formula SAE club, herein referred to as Tennessee Tech Motorsports (TTM). This will be the club’s first electric car, so it is crucial that these systems are designed to comply with the rules, specifications, and constraints of the Formula SAE guidelines which will be discussed in their own section.

Since this is Tennessee Tech’s first electric vehicle, much research and collaboration with Tennessee Tech Motorsports is necessary. It is also important to note that these vehicles are very iterative and are modified and adjusted over the course of multiple years. This will be considered when designing the systems this project aims to complete.

This project, and the Formula SAE Electric competition, gives new engineers exposure to the rapidly developing field of electric automotive engineering. With more engineers being introduced to the field the potential for innovation increases. Innovations that could have a positive impact on society. These potential effects will be discussed later in its own section.

1. _Objective_

The main goal of this project is to design the powertrain and power system for the electric vehicle, so that it meets the specifications and constraints set by Formula SAE. To be more specific a tractive system to drive and stop the car will be designed. The tractive system, and any related subsystems should be in a state so that Tennessee Tech Motorsports can continue to adjust and develop the rest of the vehicle.

1. _Benefits_

The main benefit of this project its relation to Tennessee Tech Motorsports. Completing this project will help the club enter the electric vehicle into the Formula SAE Electric competition. This will expose current and future members to the field of electric automotive engineering. Students and faculty of all engineering disciplines will learn more about electric vehicles and contribute new ideas to the field.

1. _Challenges/Obstacles_

This project presents several key challenges that must be carefully managed to ensure its success:

1. **Compliance with Formula SAE Regulations**:  
    The primary constraint is adhering to the rigorous rules and specifications set forth by the Formula SAE competition. All design decisions must align with these regulations to ensure the vehicle is eligible to compete. This requires a thorough understanding of the Formula SAE guidelines and frequent consultation to avoid violations.
2. **Limited Control Over the Vehicle’s Structure**:  
    As this project focuses on the powertrain and electrical systems, the team has limited ability to modify or redesign the physical structure of the vehicle. Tennessee Tech Motorsports is responsible for building the car, meaning that we must work within the constraints of their design choices. Any proposed modifications to the vehicle must be communicated clearly to Tennessee Tech Motorsports, and we may need to persuade them to adopt changes that will optimize system integration.
3. **Iterative Development**:  
    Given that this is Tennessee Tech Motorsports’ first electric vehicle, we anticipate a learning curve and a process of continuous iteration. The systems we design will likely be refined and adjusted in subsequent years, making it essential that we provide flexible and modular solutions that future teams can build upon.
4. _Availability_

Availability of resources, personnel, and time will be a significant factor in this project's success. The design and development of the powertrain and power system must be coordinated within the schedules of multiple teams and stakeholders. One key challenge will be working with mechanical engineers not directly involved in this project. Their availability will dictate how quickly certain aspects of the design can be integrated into the vehicle.

Additionally, members of Tennessee Tech Motorsports may have competing commitments that could limit their availability for collaboration, requiring careful planning and clear communication to ensure the project progresses smoothly. Our team will need to remain flexible and adaptable, balancing tight deadlines and resource constraints while ensuring that the systems are delivered on time and meet the required standards.

To mitigate availability issues, we plan to establish a regular communication schedule, prioritize tasks, and set clear milestones to keep the project on track despite potential delays or scheduling conflicts.

1. _Stakeholders_

The stakeholders involved in this project are:

1. **Tennessee Tech Motorsports**:  
    As the primary recipient of the powertrain and electrical systems, Tennessee Tech Motorsports will benefit from a working electric vehicle that meets the competition's specifications. Our work will empower the club to compete in future Formula SAE Electric competitions and pave the way for further development in electric vehicle technology.
2. **Tennessee Tech University**:  
    The university itself is also a key stakeholder, as successful competition outcomes could bring increased recognition and funding. Additionally, this project can generate greater interest in engineering programs, particularly in electric vehicles and renewable energy technologies. The university stands to benefit from both the academic and practical experiences gained by students working on this innovative project (refer to section V, C: Timeline).

# Specifications and Constraints

## Specifications of this project

1. This electric powertrain shall have enough performance to be comparable to Tennessee Tech Motorsports internal combustion engine car.
    1. The EV powertrain shall have comparable performance to a 50-horsepower internal combustion engine.
    2. The car shall be able to operate for at least an hour to complete the FSAE endurance event before needing to recharge.
    3. The electric powertrain shall have the capability to reach a top speed of 60 miles per hour.
2. This Formula SAE Electric powertrain shall comply with all rules and regulations specified in the Formula SAE rule book \[1\]. Some of these rules are listed below:
3. The voltage measured between any two points may not exceed 600 V DC.
4. Only electric motors are allowed.
5. The tractive system (every part connected to the motor and/or accumulator (battery)) motor must be connected to the battery through a motor controller.
6. The accumulator container must be completely closed at all times, and removeable from the vehicle while staying rule compliant.
7. The vehicle must include a tractive systems active light that must illuminate when the tractive system is active.
8. The entire Tractive System and GLV System (Grounded Low Voltage) must be completely galvanically separated.
9. Shutdown System: The shutdown system consists of the following components, connected in series:
10. Accumulator Management System
11. Insulation Monitoring Device
12. Brake System Plausibility Device
13. Interlocks
14. Master Switches
15. Shutdown Buttons
16. Brake Over Travel Switch
17. Inertia Switch

A figure has been included to give a visual representation of all these systems:
![Figure 1: Shutdown Circuit of a Formula SAE EV Car](https://github.com/northsack/F24_Team2_FormulaSAE/blob/main/Documentation/Images/Fig.%201%20shutdown%20circuit.png)
Figure 1: Shutdown Circuit of a Formula SAE EV Car

1. An Accumulator Management System must monitor the Accumulator’s Voltage and Temperature when the Tractive System is Active, and/or when the Accumulator is connected to a charger.
2. The vehicle must have an Insulation Monitoring Device (IMD) installed in the Tractive System
3. The vehicle must have a standalone nonprogrammable circuit (Brake System Plausibility Device – BSPD) to check for simultaneous braking and high power output. The BSPD must open the shutdown circuit when both there is a demand for hard braking, and the motor/accumulator is at a level where 5 kW of electrical power in the DC circuit is delivered to the motor at the nominal battery voltage.

## Constraints of this project

1. This electric powertrain shall be designed around the budget allotted by the engineering department.
2. This electric powertrain shall be designed with regards to the available tools, resources, and professional expertise available to the College of Engineering students at Tennessee Tech University.

# Identify Relevant Literature (Patents)

Patents are important for a Formula SAE electric car because they protect the unique technologies and innovations developed, such as improved battery systems and electric powertrains. Securing patents ensures that the team behind the design has exclusive rights to their work, preventing others from copying it without proper permission. Patents not only help safeguard their hard-earned research and investment, but it also opens doors for potential licensing and commercial opportunities beyond the field of motorsports. A noteworthy illustration that will need further research is the Electric Zero Motorcycle, which has a self-regenerative braking system. The technology effectively recovers energy during braking, which allows for more battery usage. Additional research will allow for more knowledge about the DVT configuration software and speed controller patents to allow for better wiring when the time comes.

# Set Goals and Measurements

The specifications of this project are defined in the Formula SAE Rules \[1\]. This powertrain shall be comparable in power to Tennessee Tech Motorsports’ internal combustion (IC) engine currently used in their Formula SAE competition car.

First, the electric powertrain’s success shall be measured by checking the specifications of the powertrain against the mandated rules by the Formula SAE competition. An example of this would be the Electronic Throttle Control (ETC) system that the SAE organization requires. If the two Accelerator Pedal Position Sensors (APPS) read values that have a 10% or greater difference for a duration of 100 milliseconds, the powertrain must disable itself automatically. To test a specification like this example, an oscilloscope would be connected to the APPS sensors, and the throttle output. The inputs and outputs of the ETC system could then be used to prove that the system is rule compliant, and a goal of the project has been completed. All tests of rule compliance shall be run until the powertrain is in accordance with the Formula SAE Electric rules

Success shall also be measured by placing the operational electric powertrain on TTM’s dynameter table. From this dynameter table, the horsepower and torque of the EV powertrain will be measured to check if the outputted power is comparable to TTM’s IC engine. If the desired numbers are not obtained, re-gearing the motor or upgrading components may be necessary.

Finally, success shall be measured by placing the EV powertrain into a formula SAE style vehicle to test its performance. Using the Upper Cumberland Regional Airport, a road course similar to the Formula SAE dynamic events can be laid out with cones, and the car shall be tested through this course. From this testing, the run time duration can be measured. At the Upper Cumberland Regional Airport, the top speed of the car can also be measured.

# Estimate Resources and Timeline

## Design Cost

Tennessee Tech Motorsports has many parts and materials for us to use, but there will be parts and materials that we will have to purchase. The following table details an itemized list of parts or other materials needed for the completion of the electrical portion of this project:

# Table I – Cost of Materials

| **Item/Material** | **Quantity** | **Cost (USD)** |
| --- | --- | --- |
| Aluminum Motor Plate | 1   | $125 |
| Speed Controller | 1   | $925 |
| 2022 Zero FXE Motorcycle (Battery & Electric Motor) | 1   | $7,050 |
| Fire Blanket | 1   | $120 |
| Buckets to Hold Sand | 3   | $75 |
| DVT Configuration Software and Specialized Cable (For Programming Speed Controller) | 1   | $650 |

## Skills Needed

The skills required for this project are more hardware based than software based. Hardware skills for this project include but are not limited to soldering, circuit design, the ability to understand wiring diagrams, and having knowledge of the parts we are working with. Collaboration with Tennessee Tech Motorsports is necessary for knowing what will be required. Software skills include being able to program a micro controller such as an Arduino to track certain metrics and give a response based on said metrics. There is plenty of documentation online that could be helpful in making progress with this project. Being able to scan through and find relevant information is beneficial as well.

## Timeline

A broad look at the current timeline of events is as follows:

- August – December 2024: Design Project
- January – May 2025: Build project

A more detailed look at the current timeline of events is as follows:

**2024:**

- October 28: Conceptual Design Finished
- November 30: Detailed Design Finished

**2025:**

- January 20: Start putting the project together
- April 11: Have the planned project scope finished and ready for tweaking
- May 2: Project finished and ready to present

![](https://github.com/northsack/F24_Team2_FormulaSAE/blob/project_proposal/Documentation/Other%20Files/Gantt%20Chart.pdf)

# Broader Impacts

When designing the Formula SAE electric vehicle's powertrain and power system, it's not only about following the technical requirements; it also involves considering a much wider approach. For example, the development of electric car technology does considerably lower greenhouse gas emissions. However, battery production and disposal present environmental risks, especially concerning the sourcing of lithium and cobalt. It is our ethical duty as engineers to take research into account when selecting materials to reduce harm to the environment, encourage recycling, and support sustainable practices. The team also needs to recognize the potential unknowns, such as technological limitations or unforeseen environmental impacts, when acquiring new materials.

The team also needs to consider how this technology might impact both society and the economy. While improving electric car technology can promote cleaner energy, it may upend sectors of the economy that depend on internal combustion engines, thus harming livelihoods and jobs. It will be vital to mitigate these effects by retraining workers in electric car technology. To ensure Tennessee Tech Motorsports' design is both innovative and ethically sound, we will evaluate the project based on its ability to create a tractive system that is efficient, effective, and accountable in terms of sustainability and societal impact. For feasibility, we must align the project with specific criteria, including available resources, team skills, and timeline, guaranteeing that the design remains practical and achievable within the Formula SAE constraints.

##### References

1. Formula SAE, “Formula SAE Rules 2024 Version 1.0”, fsaeonline.com, <https://www.fsaeonline.com/cdsweb/gen/DownloadDocument.aspx?DocumentID=369d01c0-589d-4ebe-b8d4-b07544f4a52b> (accessed Sep 14, 2024)
