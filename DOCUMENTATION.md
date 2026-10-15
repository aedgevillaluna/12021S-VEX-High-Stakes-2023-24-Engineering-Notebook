# Overview
Game Rules

This year's competition is High stakes, a robotics competition comprised of two alliances made of two robots each. The main objective is to score a colored ring into three different types of stakes. The first scoring stake is the mobile goal, that can be moved around the field and be scored at the same time. A robot is only allowed to possess one Mobile Goal and 2 rings. The second scoring stake is a wall stake, two alliance wall stakes, and two neutral wall stakes where rings can also be scored in. And finally one high stake that sits on the top of a 4 foot tall ladder that can hold one ring. 

Scoring Rules (For Robot Skills Matches)

  - Each ring on Mobile Goal, Alliance stake, or Wall stake is worth +1 Point for that team’s alliance
  - The top most ring of a stake is worth +3 points
  - Only one blue ring is allowed per stake and must be scored on top of a red ring, all other red rings must be scored.
  - Any blue ring not following this criteria will not count toward 
  - Neutral Wall stakes and Mobile Goals can hold 6 rings
  - Alliance Wall stakes can hold 2 rings
  - Rings can be removed from any stake at any time

Mobile goals can be moved to the field corners to add +5 extra points towards the end of the match.

Nearing the end of the match, robots can hang on the rungs of the ladder to earn extra points:

Points for Climbing:

  - Tier 1: 3 points (Robot must not be touching the ground)
  - Tier 2: 6 points (Robot is completely above the first rung)
  - Tier 3: 12 points (Robot is completely above the second rung)

# First Steps

Date: December 11, 2024

As we begin our season, we started by analyzing the High stakes game overview and game manual to fully understand the objectives, scoring system, and rules. We began brainstorming potential robot designs and strategies to determine the most effective approach for this challenge. Our first major goal is to develop an initial prototype and have it ready for testing as soon as possible.

Date: December 19, 2024

A few days into our brainstorming process, we looked into the Hero Starter Bot, Axel, for inspiration and explored ways to improve upon its design. To start, we identified the key components of the robot and analyzed their functions:

  - Drivetrain
    Powered by two 11W motors positioned at the rear of the robot, allowing for independent rotation.

  - Intake
    Operated by two motors that control the movement of the arm and the ability to pick up rings.

While analyzing these functions, we identified several issues affecting performance:

  - Limited Functionality And Efficiency: This robot is only capable of doing two tasks; intake rings, and climb one rung on the ladder.
  
  - Intake Inefficiency: The intake arm does not consistently pick up rings, especially when they are scattered, causing delays in scoring.

We started brainstorming solutions to improve efficiency, reliability, and overall effectiveness in gameplay.

<img width="408" height="528" alt="slide 73  (3)" src="https://github.com/user-attachments/assets/c69abdcd-0d60-4ee3-afba-7451d1eef2ae" />

Because of the inefficiencies we observed in the existing design, we began brainstorming our own solutions to create a more effective and reliable ring manipulation mechanism. Through discussion and analysis, we identified three main configurations for our design. Each design has unique advantages and trade-offs, so we evaluated them based on key factors such as:

  - Functionality: How well does it handle rings?
  
  - Ease of Implementation: How difficult is it to build and integrate?
  
  - Compatibility with Our Drivetrain: Does it work well with our current chassis and movement strategy?

1, Vertically Aligned Claw
  - Concept: This claw would be positioned vertically, allowing it to grab rings from above rather than from the side.

Advantages:
  - The claw could be multi-functional, potentially allowing the robot to climb or hang in addition to manipulating rings.
  - Simple mechanical design with only one pivot point on the arm and a single actuator to control the claw mechanism.

Disadvantages:
  - The robot would require precise vertical positioning to grab rings consistently.
  - The claw’s positioning could interfere with the ring when attempting to push it onto the stake, as it would reach into the middle of the ring.

2, Horizontally Aligned Claw
  - Concept: A side-gripping claw similar to those found in VEX inventory, but scaled up to accommodate the larger rings.

Advantages:
  - The claw would grip the ring from the outside, avoiding interference when placing it onto a stake.
  - Like the Vertical Claw, it maintains a simple design, using only one pivot point and a single actuator.

Disadvantages:
  - The arm would still need precise horizontal positioning to grab rings effectively, which may introduce complexity in programming and driver control.

3, Conveyor System
  - Concept: A continuous intake and transport mechanism that pulls rings in, moves them along a conveyor belt, and then deposits them onto the stake using additional arms.

Advantages:
  - Significantly faster operation compared to a claw, as it eliminates the need for arm acceleration and precise positioning each time a ring is grabbed.
  - Reduces motor strain, since the system would be powered by a continuous belt rotation rather than repeated arm movements.

Disadvantages:
  - More complex construction – Unlike the other two designs, this requires separate subsystems (intake, conveyor, deposit arms), increasing build time and potential points of failure.
  - Requires additional space on the robot, which may affect weight distribution and drivetrain efficiency.

And the drivetrain, which is going to hold our mechanisms, has to be maneuverable and efficient. 

Our Drivetrain:

We considered a drivetrain similar to the Axel robot, but with key modifications to enhance maneuverability and efficiency. Instead of using the standard setup, we decided to place the Omni-wheels at the front of the robot while keeping the powered traction wheels at the rear. This configuration is intended to provide greater control, allowing the robot to easily pivot and navigate spaces while maintaining stability and traction during gameplay.

Next Steps:

Our next step will be to refine these ideas and integrate them into a working prototype. We will first build a prototype of the drivetrain with the adjusted wheel placement and test its maneuverability, speed, and stability.

# Prototyping Drivetrain
<img width="408" height="528" alt="slide 73  (7)" src="https://github.com/user-attachments/assets/7edc1d27-4158-4f0b-84d7-a42ec10ef5f2" />

Date: January 6, 2025

After winter break, we finished brainstorming several ideas to start prototyping the robot. Prototyping a design is the second step of the engineering design process. A prototype usually wouldn’t be the most efficient design, but it provides a rough idea of how it would function. We started working on a prototype drivetrain model that would serve as the chassis of our robot. Here is how we set it up:

  - Chassis Setup:
    We began by using four [2 × 2 × 25] Steel L-Channels arranged in the layout shown, with a [5 × 25] Plate in the middle to serve as the core of our starting chassis. This structure is sturdy and provides a solid foundation for the rest of the robot's components. The steel L-channels offer strength and stability, ensuring that the drivetrain will remain intact during intense gameplay.

  - Omni Wheels Setup:
    For the front of the robot, we chose to place two Omni-Wheels. Omni-wheels are ideal for this application because they allow the robot to move in all four directions without any dragging or resistance from the floor. The unique design of Omni-wheels, with rollers positioned at an angle, enables smooth lateral and diagonal movement, which is essential for maximizing the robot's maneuverability.

    By positioning the Omni-wheels at the front, we also prevent the wheels from rubbing the floor during turns, ensuring that the robot can turn smoothly and efficiently. This setup saves us a motor, as we don’t need to worry about traditional steering mechanisms. Instead, the Omni-wheels allow us to achieve more precise, fluid movements with fewer motors.

  - Rear Wheel Setup:
    At the rear of the robot, we placed two standard VEX wheels. These wheels are motorized and provide the primary drive force for the robot. The rear wheels allow for forward and backward movement, while the Omni-wheels handle the turning and lateral movements. This hybrid drivetrain design, combining Omni-wheels with traditional wheels, is meant to provide the robot with both agility and stability.

  - Smooth Rotation with Hex Nut Retainers:
    To ensure smooth rotation and prevent friction or wear on the drivetrain, we incorporated 1 Post Hex Nut Retainers with Bearing Flats. These components are essential for allowing the standard shafts to rotate smoothly. The bearing flats ensure that the shafts are held securely in place without any friction caused by the square corners of the VEX structure channels. This design improves the efficiency of the drivetrain, reducing wear and tear on the moving parts over time.

Next Steps:

With the basic chassis and drivetrain setup complete, our next step will be to test the prototype. We’ll run tests to evaluate its speed, turning radius, and overall maneuverability. This will help us identify any weaknesses in the drivetrain and make adjustments as necessary. We are particularly interested in how the Omni-wheels perform in tight spaces and how efficiently the robot can transition between different directions. Based on the results of these tests, we will refine the design, possibly adjusting the placement of the wheels or experimenting with different gear ratios to optimize performance.

Date: January 10, 2025

After building our prototype drivetrain, we noticed several problems that need to be addressed before moving forward with the design:

  - Inaccuracy with Omni Wheels:
    One of the first issues we encountered involved the Omni Wheels. While these wheels provide excellent lateral movement, we realized that the smaller wheels, which allow the robot to move horizontally, are not motorized. This creates a significant problem. When the motors turn the robot, the Omni wheels continue rotating even after the motors stop. As a result, the continued movement of these non-motorized wheels creates inaccuracy in the robot's positioning. This becomes especially problematic during the autonomous period of the match, where precise movements are crucial. The unintended movement of the Omni wheels introduces unnecessary variables, making it difficult to achieve accurate, repeatable motions.

  - Lack of Motorization in Omni Wheels:
    Another issue with using Omni Wheels at the front of the robot is that the Omni Wheels are not motorized. As a result, we are unable to utilize a 4-motor drive system, which would provide a significant performance boost in terms of speed and power. With two motors dedicated to the front Omni-wheels, we are left with fewer motors for other functions, such as the intake and lifting mechanisms. In the context of the competition, this is a major limitation because it means we are sacrificing motor resources that could be used for more crucial tasks.

We hope to tackle these issues next week and proceed with adding more functions to the robot.

<img width="408" height="528" alt="slide 73  (10)" src="https://github.com/user-attachments/assets/094a3360-6c3e-4008-a82b-d9acc7231c9e" />

Date: January 15, 2025

To address the issues identified last week with our drivetrain, we began considering potential solutions to resolve the inaccuracy with the Omni wheels and the motorization limitations. After evaluating different approaches, we focused on the possibility of adding chain to the drivetrain as a way to solve several of these problems. One of the solutions is to connect a chain from the rear motorized wheels to the front Omni wheels. This would allow both the front and rear wheels to spin at the same time, effectively motorizing all four wheels of the robot. The benefits of this design include:

  - Synchronizing Wheel Movement: By using a chain to link the front and rear wheels, we can ensure that all four wheels are driven by the motors, providing more consistent movement. This would help to mitigate the issue of the non-motorized Omni wheels continuing to rotate after the motor stops, which had been causing inaccuracies during the autonomous period. With synchronized wheel movement, the robot should be able to execute more precise turns and avoid unintended movement from the Omni wheels.

  - Reducing the Need for Extra Motors: Another key advantage is that connecting the front and rear wheels via a chain reduces the need to use additional motors. Since both the front and rear wheels would be powered by the same set of motors, we can free up motors for other subsystems, such as the intake or any lifting mechanisms. This improves our robot's overall efficiency and ensures that we have the necessary resources to handle multiple tasks during a match.

  - Maintaining Agility and Control: This chain-driven design still maintains the robot's ability to make precise turns and move laterally thanks to the Omni wheels. This design keeps the benefits of the Omni wheels' maneuverability, while ensuring that all wheels are engaged and providing power during movement.

Date: January 16, 2025

Another important function to consider is how to effectively control the robot using a controller. There are multiple ways to set up the controls, and choosing the best configuration will impact the driver's ability to maneuver the robot efficiently during matches. The control scheme should be intuitive, responsive, and optimized for both autonomous and driver-controlled periods.
Here are some potential driving setups we are considering:

  - Tank Drive Control: In a tank drive setup, the left joystick controls the left side of the drivetrain, and the right joystick controls the right side. This setup mimics how a tank moves, where pushing both joysticks forward moves the robot forward, pulling them back moves the robot backward, and pushing one forward while pulling the other back allows the robot to turn in place. This allows the driver to make precise controls and quick turns and smooth adjustments during driving. However, this utilizes both thumbs, which restrict multitasking such as driving while turning on the intake.

  - Arcade Joystick Control: The idea of this setup is a single joystick controls both forward/backward movement and turning. The forward/backward motion is controlled by pushing the joystick up or down, while left/right movement controls turning. This is the most easiest way to drive the robot and only utilizes one thumb while the other can be used to activate other robot functions. However, this setup is not precise, as movement and turning are powered by the same joystick.

  - Split Arcade Drive: This setup is a modification of the Arcade Joystick setup as it utilizes both joysticks instead of one. One joystick handles forward and backward movement, while the other joystick controls turning. This is a hybrid between tank and arcade drive, aiming to provide both precision and simplicity. This setup provides better control over turning compared to a single-stick arcade drive, while allowing the driver to free up one hand for other functions. However, this is more complex than the other two methods and is difficult to make precise movements.

<img width="408" height="528" alt="slide 73  (11)" src="https://github.com/user-attachments/assets/c93196e0-ca3b-4605-a05b-9bf0186dd76f" />

# Prototyping Intake
January 17, 2025

After testing all three options, we settled on using the Tank Drive setup for our controller. This configuration provided the best balance of precision, control, and reliability for our drivetrain. Since each joystick independently controls one side of the drivetrain, it allows for smooth turns and better maneuverability, especially when making fine adjustments.

With our controller configuration finalized, our focus now shifts to the intake system, which will be one of the most frequently used functions of our robot.

Developing the Intake System

Initial Concept: Wheel Ramp System

Our first intake design involved a wheel ramp system, where a front-mounted ramp guides rings upward while motorized wheels positioned above the ramp pull them in. This system aimed to efficiently collect and transport rings from the ground onto the robot.

We started with intake rollers, as we think they provide a good balance of flexibility and grip, ensuring rings are securely pulled in. However, we also considered other wheel types, such as small traction wheels, which might provide more consistent movement without excessive slippage.

<img width="408" height="528" alt="slide 73  (12)" src="https://github.com/user-attachments/assets/169c0c84-eab8-4ff6-90ea-4bbee7149601" />

January 21, 2025

After building a prototype of our design, we found out several problems with our prototype:

The ramp was too steep, which is the easier to fix as we lower the top of the ramp’s height to a less steep angle.

However, the intake rollers, which we thought were the perfect choice of gripiness and flexibility, were not as efficient as we thought it would be. Testing with a motor only moves the ring slightly before the roller slips and loses grip on the ring, which is not what we wanted.

After experimenting with several different wheel types, we found out that the flex wheel had the best combination of grippiness and flexibility that we need. Since we only had a limited amount of flex wheels, we also used intake rollers in the middle that we thought would also provide some gripiness in the center. The spacing of the flex wheels and intake rollers were also important to conserve parts and increase efficiency.

# Prototyping Back Grip

<img width="408" height="528" alt="slide 73  (13)" src="https://github.com/user-attachments/assets/76771d5c-7f52-4c7d-93a6-ae95449d74cc" />

# Solving the Problems

January 29, 2025

After building a prototype of the back grip, we quickly stumbled across several issues:
  - The intake wouldn’t properly deposit the rings into the conveyor chain
  - The motors of conveyor and back grip overheat when overused
  - The back grip motor overheats on some occasions

We decided to solve the intake and conveyor problem first as it felt more important than the back grip.

To solve the conveyor problem, we had several ideas, but among all of them, only one idea was obvious: double the amount of motors used for the conveyor.
The two motors would be grouped together to drive the same axle that also drives the sprocket chain. This way, the strain would be divided between the two motors and wouldn’t overheat that easily.

The reasons why the intake wasn’t working was the following:
  - The intake was too low it doesn't lift up to pick up the rings
  - The intake also wasn’t as efficient as we wanted
  - Even if the ring was picked up by the intake, the conveyor chain would launch the ring off

<img width="408" height="528" alt="slide 73  (14)" src="https://github.com/user-attachments/assets/e9cc3f81-c6d3-4495-a086-5ab60483efbf" />

January 30,  2025

To solve the intake issue, we first started with the efficiency. Since normally VEX plates were too thick when being stacked, we had to get creative and we first started with a 3D printed part as a test. The reason we made the ramp 3D printable was because it was quick and easy to prototype different designs and print and test them at the same time. After a couple iterations, we settled on a design that looks like this. The black part you see on this sketch shows what the 3D Printed part looks like.

Another good reason to use a 3D printed part such as this is because 3D printed parts, with the right filament material, can be durable and long-lasting, especially during the rough conditions on the field.

<img width="408" height="528" alt="slide 73  (15)" src="https://github.com/user-attachments/assets/e9f9c07b-20d8-4928-8f22-73e072c035a9" />

February 3, 2025

After testing and verifying the new 3D part functions efficiently, we then started to work on the second problem of the intake; the conveyor chain. The problem with our current design is it cannot hold onto the rings without them slipping or bouncing off. 

And with this sketch to the right shows what we were thinking, using two bearing flats screwed onto the standoffs. The benefits of these bearing flats would this section to work as a proper “hook” like mechanism. 

After adding these to all the sections of the conveyor chain, we were happy with the new efficiency with the modifications., the hooks perfectly grabbed the rings with ease on most occasions. On some testing scenarios, the entire ring would sit above the hook and that is not what we want when it comes to depositing the ring into a stake. And on rare occasions, the ring would jam the conveyor and we had to manually get the ring out by reversing the conveyor chain.

<img width="408" height="528" alt="slide 73  (16)" src="https://github.com/user-attachments/assets/27b89b5b-1f1e-4d9c-8ffa-b883c6c730b9" />

February 5, 2025

After testing a bunch of other case scenarios, most of the time the ring would get properly picked up by the conveyor.

Tackling the Stake
Even with our back grip, there were a few inconsistencies:
The mobile goal is not held on when it comes to the rotation and left and right movement, which could impact the performance of the robot.
The motor overheats too much, which could impact the strength needed to hold the mobile goal in place, which is what happens when we tested this on the actual field.

We started to brainstorm a fix that would solve both these problems without using pneumatics.
After doing some research, we found that most VEX robots used a bar at the bottom to lift the mobile goal off the ground. This provided a pro and con:
The mobile goal can be held securely since it wouldn’t rub against the floor and cause the stake to move around much.
However, this idea would cause our motor to overheat more since it needs to pull the mobile goal above the bar, which needs more power.

Ignoring the con for now, we added a prototype that looks like this:

<img width="408" height="528" alt="slide 73  (17)" src="https://github.com/user-attachments/assets/5510d6c1-2b54-4829-b272-548548cd37b9" />

February 10, 2025

After trying to get the new modification to work a couple of times, we thought it was just the gripping arm would be the problem.

The problem with the current gripping arm is it doesn’t grip the mobile goal and keep it in place. We redesigned the gripping arm multiple times and each iteration had their pros and cons:

  - This gripping arm modification used pivot gussets at the end, allowing for the mobile goal to easily pick up the mobile goal and pull it in. However, this causes the mobile goal to slip due to its curved structure when it grips the mobile goal.
  - This gripping arm modification used an angle gusset like so. This modification improved slightly, the mobile goal only slipping on some occasions.

After concluding using the second gripping arm modification for now, we plan to also modify the bar at the rear as we think that could also improve the performance.

February 13, 2025

After modifying the arm, we thought we needed to modify the bar too since it could be the reason the modified gripper doesn’t properly grip.

We started with using a 12 inch driveshaft as a starting point, and we used 36 tooth gears to mount the driveshaft. Since this was a prototype, we use these gears as they have holes where screws can enter so we can mount the driveshaft. To give the bar more strength so it doesn’t bend, we added several spacers. These spacers will prevent the bar from bending too much and provide a decent thickness for the gripper to grip on.

After researching more ideas, we stumbled upon one pesky rule in the game manual that immediately caught our attention.

At the beginning of a Match, each Robot must be smaller than a volume of 18” (457.2 mm) long by 18” (457.2 mm) wide by 18” (457.2 mm) tall.

Once we discovered this rule, we quickly had to measure what our length and height of the robot is. Since width was not too much of an issue, we checked for height and length using a tape measure. And as we feared, the robot stood just above 21 inches, and a length measurement of 21 inches, which would immediately get us disqualified if we didn’t fix this issue. 

February 18, 2025

After taking down the robot and making sure pictures were taken to retrace our steps, we remade the robot. 

We think the main issue is coming from the intake that sticks out of the robot, and moving it in would solve most of the problems, and so that is what we did. We used [2 x 2 x 20] L-Channels on the inner two bars so we have room to fit the intake.

We also had to move the wheels, adjust the conveyor chain length, and wiring to ensure efficiency would still remain the same. Changing the wiring meant we moved the brain to a more open side of the robot, in this picture, the right side, and accidentally broke a couple battery holders in the process.

February 21, 2025

After disassembling and reassembling the robot, we finally had the lower part of the robot done. Its length was just underneath 18 inches. To tackle the height part was more interesting. We replaced the two [2 x 2 x 25] L-Channels with two [2 x 2 x 20] L-Channels, which in theory would decrease the robot’s height and allow the robot to mainly get just under 18 inches. We also adjusted the conveyor since the old chain length would not fit, and adjusting the sprockets since changing the sprocket sizes would not change the same ratio. 

We also redid the back grip and bar to accommodate the new height size. The resting bar and the back grip bar are shorter while still maintaining the high strength gear ratio. We also figured out how to take advantage of the tension of the VEX plates to hold the resting bar as shown in the picture, and use shaft collars to keep everything steady. This somewhat improved its performance but the conveyor cannot deposit the rings into the mobile goal.

<img width="408" height="528" alt="slide 73  (18)" src="https://github.com/user-attachments/assets/d3e2b63c-393f-4caa-9f12-85d7282bb816" />

February 21, 2025

After disassembling and reassembling the robot, we finally had the lower part of the robot done. Its length was just underneath 18 inches. To tackle the height part was more interesting. We replaced the two [2 x 2 x 25] L-Channels with two [2 x 2 x 20] L-Channels, which in theory would decrease the robot’s height and allow the robot to mainly get just under 18 inches. We also adjusted the conveyor since the old chain length would not fit, and adjusting the sprockets since changing the sprocket sizes would not change the same ratio. 

We also redid the back grip and resting bar to accommodate the new height size. The resting bar and the back grip bar are shorter while still maintaining the high strength gear ratio. We also figured out how to take advantage of the tension of the VEX plates to hold the resting bar as shown in the picture, and use shaft collars to keep everything steady. This somewhat improved its performance but the conveyor cannot deposit the rings into the mobile goal.

To tackle this issue, we added wheels at the end of the conveyor. This provided a useful benefit:
  - Rings will be able to flip into the mobile stake easier, given the wheels make the rings a little closer to the mobile stake.

# Refining the Details

February 24, 2025

We worked on a back guide to help with alignment when handling the mobile goal. By adding this guide, we aimed to create a more consistent method for securing and controlling the goal during movement.

We also thought of using a parallelogram mechanism that could potentially improve how our intake and gripping systems interact with the mobile goal. This idea would allow for a controlled lifting motion without causing excessive strain on the motors. Further testing and prototyping will be required to determine its feasibility.

<img width="408" height="528" alt="slide 73  (19)" src="https://github.com/user-attachments/assets/1e896031-66d2-4579-afa9-06e3e6267276" />

February 28, 2025

We started integrating a 2D intake system to enhance our ring collection mechanism. This new system uses “banana” like ramps that form a ramp that gradually moves the ring into an angle that the conveyor can pick up.

Another key improvement involved refining the inverse ramp mechanism. The goal was to force the stake to tilt at the right angle to improve the robot’s ability to secure and place rings. While the modifications helped, the ramp still required fine-tuning to prevent inconsistencies. This remains a work in progress, and we plan to conduct further testing and adjustments in the coming days.

March 4, 2025

To improve the stability of the mobile goal during lifting, we added a much thicker support bar for the stake to rest on. This addition ensured that the stake remained in place while the gripper mechanism engaged.

We also worked on refining our gripper system, making adjustments to enhance its ability to hold onto objects securely. The main challenge was ensuring that the gripper could lift the stake without causing excessive force on the robot’s frame.

<img width="408" height="528" alt="slide 73  (20)" src="https://github.com/user-attachments/assets/431a5633-e849-4b20-a985-6c278e450b03" />

March 7, 2025

We decided to make a dunking mechanism. This idea came out of the blue to add rings into the wall stakes so we can at least get some points if the mobile goals fail. This mechanism works by utilizing gear ratio and speed to provide the efficiency and speed we need to place a ring into the mobile goal, hence the name, dunking.

After a couple iterations we successfully completed a working prototype of the dunk mechanism. We conducted multiple test runs to assess the efficiency of the mechanism. While the initial results were promising, we identified a few minor adjustments that could further enhance the system’s stability and consistency.

<img width="408" height="528" alt="slide 73  (21)" src="https://github.com/user-attachments/assets/f1e0d0ef-702e-4373-8a56-0ed06c887169" />

```python
def loadDunk():
   # Loads Ring Into Dunk [R1]
   dunker.set_velocity(75, PERCENT)
   dunker.spin_to_position(dunk_mid_pos, DEGREES)
   conveyor.spin(FORWARD)
   intake.spin(FORWARD)
   optical_2.set_light(LedStateType.ON)
   c = 0
   while not (optical_2.is_near_object() and optical_2.color() == Color.RED):
      
       if c > 600 or killProcesses:
           return
       wait(5, MSEC)
       c+=1
   optical_2.set_light(LedStateType.OFF)
   wait(0.455, SECONDS)
   conveyor.stop()
   intake.stop()
   dunker.set_velocity(30, PERCENT)
   dunker.spin_to_position(10, DEGREES)
   conveyor.set_velocity(30, PERCENT)
   conveyor.spin(REVERSE)
   optical_2.set_light(LedStateType.ON)
   c=0
   while not (optical_2.is_near_object() and (optical_2.color() == Color.RED or optical_2.color()==Color.YELLOW)):
       if killProcesses or c > 40000:
           optical_2.set_light(LedStateType.OFF)
           return
       wait(5, MSEC)
       c+=1
  
   optical_2.set_light(LedStateType.OFF)
   wait(0.1, SECONDS)

   conveyor.stop()
   conveyor.set_velocity(75, PERCENT)
```

March 11, 2025

We redid the dunker area that makes it work more efficiently as shown by the picture as well as the code. We continued refining our 3D-printed gripper, experimenting with different designs to maximize its effectiveness. Our initial tests revealed a major flaw: the gripper lacked a horizontal surface to rest on, which caused excessive force on the arm when lifting objects.

To address this, we redesigned the gripper to include a more stable resting position, allowing it to distribute force more evenly. Additionally, we examined ways to further stabilize the intake system to prevent bending and ensure that all components remained structurally sound during operation. Although today’s modifications showed some improvement, further adjustments will be needed to achieve a fully optimized design.

```python
def finishDunk():
   # Activates Dunk Mechanic [R2]
   dunker.set_velocity(100, PERCENT)
   dunker.spin_to_position(900, DEGREES)
   wait(1, SECONDS)
   if killProcesses:
       return
   dunker.set_velocity(50, PERCENT)
   dunker.spin_to_position(10, DEGREES)
   dunker.stop()
   dunker.set_velocity(100, PERCENT)
```

<img width="408" height="528" alt="slide 73  (22)" src="https://github.com/user-attachments/assets/6428131e-f59f-467a-9c0f-63dee7e483d8" />

March 14, 2025

Our primary focus today was on still iterating the back grip mechanism. Through multiple tests, we experimented with different configurations to determine the most effective design for gripping and lifting the mobile goal.

We tested several variations of the gripping arms, making slight modifications to the shape, grip material, and pressure distribution. While some of these adjustments led to minor improvements, none of the configurations fully resolved the inconsistencies we were experiencing.

As a result, we concluded that a different approach might be necessary, and we plan to explore alternative lifting mechanisms in the coming days.

<img width="816" height="1056" alt="slide 73  (23)" src="https://github.com/user-attachments/assets/c41db48c-71aa-4524-ba63-de50b21bc56b" />

March 17, 2025

After multiple failed attempts with the back grip mechanism, we decided to scrap the idea entirely. Instead, we brainstormed a new two-arm lifting mechanism that would allow the robot to lower its arms and pick up the mobile goal more reliably.

This new design concept aimed to improve stability while reducing strain on the motors. By lowering the arms onto the mobile goal before lifting, we hoped to create a more secure and controlled movement.

We plan to prototype this mechanism next and determine if it offers a viable solution to our gripping issues.

March 19, 2025

After successfully prototyping the back lift mechanism, which replaces the previous gripping system, this new design features two arms that lower onto the mobile goal before lifting, allowing for a more stable grip.

Initial tests showed improved control and reduced slippage, but the mechanism still required some refinements to enhance efficiency. Specifically, we need to adjust the pressure applied by the arms to ensure they hold the mobile goal securely without excessive force.

Moving forward, we will work on fine-tuning the lift mechanism and testing its reliability under different game conditions.

```python
def init_back_lift():
   # Back Lift Initialization [Y]
   global lift_home_pos, lift_up
   lift_up = True
   back_lift_left.spin(REVERSE)
   back_lift_right.spin(REVERSE)

   while not (left_bumper.pressing() or right_bumper.pressing()):
       wait(1, MSEC)
   if (left_bumper.pressing()):
       back_lift_left.stop()
       while not right_bumper.pressing():
           wait(1, MSEC)
       back_lift_right.stop()
   else:      
       back_lift_right.stop()
       while not left_bumper.pressing():
           wait(1, MSEC)
       back_lift_left.stop()
   back_lift_right.set_position(back_lift_left.position(DEGREES)-offset, DEGREES)
   back_lift = MotorGroup(back_lift_left, back_lift_right)
   lift_home_pos = back_lift.position()

def toggle_back_lift():
   # Toggle Grip on Mobile Goal [L2]
   global lift_up
   if lift_up:
       lift_up = False
       back_lift.spin_to_position(lift_home_pos+lift_down_pos, DEGREES, wait=True)
   else:
       lift_up = True
       back_lift.spin_to_position(lift_home_pos+lift_up_pos, DEGREES, wait = True)
   brain.screen.clear_screen()
   brain.screen.set_cursor(1,1)

   brain.screen.print(back_lift.position(DEGREES))
```

March 21, 2025

With the new back lift mechanism in place, we shifted our focus to the coding aspect of the design. Our goal was to integrate the lift system into the robot’s autonomous and driver control modes, ensuring smooth operation.

We ran multiple test sequences to determine how well the lift functioned in practical applications. Some issues arose with timing and motor synchronization, but overall, the system performed better than expected.

We added rotational sensors to detect if the rotation of one side arm is higher than the other, then if so, adjust the higher arm to match the other side.

# Finalizing

March 25, 2025

Today, we made critical adjustments to prevent interference between the sprocket and other moving parts. We identified that improper spacing between the sprocket and wheels caused rubbing issues, which affected the drivetrain overall efficiency.

By carefully modifying the spacing, we eliminated unnecessary friction and improved the robot’s movement. This also helped prevent excessive wear on the drivetrain components, which would have been a major issue in long-term performance.

With these mechanical fixes complete, we will now focus on optimizing the intake system and making final refinements to the autonomous programming.

March 27, 2025

With about 2 days before our competition, we focused on finalizing the autonomous code and playing around with the robot testing if it will hold up to the practical reality of a competition field.

We also did some last minute changes such as adding a barrier to the intake so rings wouldn’t get caught and get stuck, jamming out conveyor, adding a reverse conveyor feature, when pressing button B on our controller, the conveyor will rotate backwards, releasing on rings or stakes if caught. We also added another feature button Y that initializes the back lift, in case the arms weren’t even after some time. Finally, button X is our last resort button, which would kill any active functions of the robot just in case something was caught and we couldn’t stop it from other functions.

<img width="816" height="1056" alt="slide 73  (24)" src="https://github.com/user-attachments/assets/99c3554a-87bc-4e8f-89d5-aa56b192de6c" />
<img width="816" height="1056" alt="slide 73  (25)" src="https://github.com/user-attachments/assets/c09736b5-0677-4cb3-86aa-40ee17866faa" />
<img width="816" height="1056" alt="slide 73  (26)" src="https://github.com/user-attachments/assets/19a63b24-4ceb-460a-b3bc-4a90547b37cc" />
