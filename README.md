Of course! Here is a detailed, step-by-step guide on how to build the basic walker, based on the provided video tutorial.

### **Getting Started: Welcome to the Basic Walker Tutorial**

This guide will walk you through creating a simple, two-legged walker in Trailmakers. The process involves building the leg structure, configuring servos, and setting up logic gates for a repeating walk cycle.

**Note:** The game in the video is not in English, but this guide will follow the English text overlays and visual cues. Be prepared for some trial and error, as getting the timing and balance right is key.

---

### **Part 1: Building the First Leg**

#### **Step 1: The Hip Joint**

1.  Start with a base structure, like the motorcycle seat on a stand.
2.  Go to the **Mechanical** parts tab and select a **Rotary Servo**. Place it on the side of your base structure. This will be the hip joint.
3.  **Configure the Hip Servo:**
    *   Select the servo to open its configuration menu.
    *   Remove any default controls by clicking the 'X' on the assigned buttons.
    *   **Speed:** Set the speed to **0.30**.
    *   **Angle:** Set the rotation angle to **65 degrees**.
    *   *(Optional Tip: Color-code your parts. The video colors the hip servo purple to keep track of it.)*

#### **Step 2: The Upper Leg (Thigh) and Logic Gate**

1.  Build the thigh structure by attaching a long block (like a 2x4 or 1x4) vertically downwards from the servo.
2.  Go to the **Logic/Gadgets** tab and select an **AND-gate**. Place it on your main body.
3.  **Configure the Hip Logic Gate:**
    *   Connect the AND-gate's output to the hip servo's input.
    *   Set the **Output** value of the gate to **-1.00**. This will make the servo rotate upwards, following the red curve in the configuration view.
    *   Assign a control button to the gate's input (the video uses R2). This will be the master "on/off" switch for the walk cycle.

#### **Step 3: Timing the Hip Motion**

1.  Select the hip's AND-gate again to adjust its timing.
2.  **Duration:** Set this to **0.80 seconds**. This needs to be timed with the servo's speed for a smooth motion. If the duration is too long, the leg will pause unnaturally at the top of its swing.
3.  **Pause:** Set this to **1.20 seconds**.
    *   This creates a total cycle time of 2 seconds (0.80 duration + 1.20 pause), which is crucial for synchronizing the second leg later.

#### **Step 4: The Knee Joint and Lower Leg**

1.  At the bottom of the thigh structure, add another **Rotary Servo** for the knee.
2.  Build the lower leg by attaching blocks to this new servo.
3.  **Configure the Knee Servo:**
    *   Remove default controls.
    *   Set the **Speed** to **0.30**.
    *   Set the **Angle** to **70 degrees**.
    *   *(Optional Tip: Color this servo and its logic gate lime green.)*

#### **Step 5: Logic for the Knee**

1.  Add a second **AND-gate** and place it on the main body.
2.  **Configure the Knee Logic Gate:**
    *   Connect this new gate's output to the knee servo.
    *   Leave the **Output** at **1.00**. This makes the knee bend forward, following the green curve.
    *   Assign the same control button as the hip (R2).
    *   **Duration:** Set this to **0.60 seconds**. It needs to be slightly shorter than the hip's duration to create a "scooping" or "kicking" motion.
    *   **Pause:** Set this to **1.40 seconds** to maintain the 2-second total cycle.

#### **Step 6: Adding a Backward Swing**

To make the walk more natural, the leg needs to swing backward as well as forward.

1.  Add a third **AND-gate** to the main body.
2.  Connect this gate's output to the **hip servo** (the first servo you placed).
3.  **Configure the Backward Swing Logic Gate:**
    *   Assign the same control button (R2).
    *   Set the **Output** to **0.80** (you can adjust this for a longer or shorter stride).
    *   Set the **Duration** to **0.80 seconds**.
    *   Set the **Pause** to **1.20 seconds**.
    *   **Delay:** This is the most important part. Set the delay to **1.00 second**. This makes the backward swing happen during the "pause" part of the forward swing cycle.

#### **Step 7: The Ankle and Foot**

1.  At the bottom of the lower leg, add a simple **Hinge** joint.
2.  **Configure the Ankle Hinge:**
    *   Remove controls.
    *   Set the **Angle** to **60 degrees**.
    *   **Strength:** Lower the strength to around **20-25**. This allows the foot to flex when it hits the ground instead of being rigid.
3.  Add a final block or two below the hinge to act as the foot.
4.  Add a **Logic-gate** to control the ankle hinge, setting it to a **Duration** of 0.70 and **Pause** of 1.30.

---

### **Part 2: Creating the Second Leg and Final Assembly**

#### **Step 8: Copy and Flip**

1.  Use the selection tool to copy the entire leg assembly (thigh, servos, lower leg, foot, and all logic gates).
2.  Place the copied leg on the opposite side of the main body. It should be a mirror image.

#### **Step 9: Reconfiguring the Second Leg**

Because the leg is flipped, you must adjust its settings.

1.  **Invert Servo Speeds:**
    *   Select the hip and knee servos on the **new** leg.
    *   Change their **Speed** from 0.30 to **-0.30**.
2.  **Re-wire and Delay the Logic:**
    *   Disconnect the logic gates that were copied over from the old leg.
    *   Go to the **three logic gates for the new leg**.
    *   For each of the three gates, set the **Delay** to **1.00 second**. This makes this leg operate exactly half a cycle behind the first leg, creating an alternating walking motion.
    *   Ensure the logic gates for the new leg are connected to the servos on the new leg.

#### **Step 10: Stability and Traction**

Your walker can now move its legs, but it will likely be unstable and may not move forward.

1.  **Stabilizers:** Add **Gyro Stabilizers** to the main body to prevent it from tipping over. Start with two and add more if needed.
2.  **Suspension:** The legs will slam into the ground. To fix this, add **Springs** to the ankles.
    *   Delete the hinge/foot on each leg.
    *   Place a spring, then the hinge, then the foot. This gives the walker suspension.
3.  **Grip:** The feet may slide. Add **Friction Pads** to the bottom of each foot to give it grip on the ground.
4.  **Turning:** Add two more **Gyros** to the main body, but assign left/right controls to them. This will allow the walker to turn by leaning.

After these steps, your basic walker should be complete and functional! You can continue to tweak the servo speeds, angles, and logic timings to perfect its stride.
