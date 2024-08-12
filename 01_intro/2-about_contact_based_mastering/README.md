## 1.2 Contact sensor-based robot mastering 
This user manual contains information on the `contact sensor-based` robot mastering function.  
More accurate corrections are possible by using this sensor.    

<br>

### 1.2.1. Mastering equipment
- **Robot** <br>- where Mastering device will be connected
- **Hi6 robot controller** <br>- where Mastering-App will be installed
- **Mastering kit** <br>- Power + Sensor + Communication module

<br>

### 1.2.2. Operating mode
- The operation mode of the robot must be set to `manual mode`.
- The procedure can only be carried out with the `motor on status` and the `enable switch` turned on.

<br>

### 1.2.3. Operating concept
- The digital contact sensor scans the `V-groove` of the mastering block mounted to each axis of the robot to locate a more precise origin. ([Fig 1-1](../1-about_mastering/README.md))  
- After scanning the `V-groove`, a new encoder offset will be set relative to the detected vector of `V-groove`.  
- Then calculate the `Corrected encoder` value.  

<br>

### 1.2.4. Overall Process  
1. Encoder offset correction - by direct teaching  
    1-a) Use the teach pendant (TP) to jog the robot to align the V-groove or scale bar attached to the robot.  
    1-b) Resets the encoder offset to a visually aligned position for individual or all joint.  
    - Enter the encoder offset setup page  
    &rightarrow; `TP` > Enter the `Engineer Mode` (R-Button + 314) > `System` > `3: Robot parameter` > `4: Encoder offset`  
    - Proceed with encoder offset initialization  
        (1) When resetting individual joint:  
        → Click `Corrrected encoder` value of the corresponding joint > Click `Reset one` > `Shift + OK` > `OK`   
        (2) When resetting all joint:  
        → Click `Reset all` > `Shift + OK` > `OK`  

<br>

2. Attaching the contact sensor    
    <div>
    <img src="../../_assets/00_mastering_Vdent_render.png" style="max-height: 20vh; max-width: 15vw">
    <img src="../../_assets/01_mastering_real_picture.png" style="max-height: 20vh; max-width: 12.3vw"><br>Fig 1-2. Mastering sensor installation image (left: render image, right: real image)
    </div>

<br>

3. Encoder offset correction - by using plugin  
    (1) After completing the steps in 1, enter the mastering plugin  
        &rightarrow; `TP` > `system` > `4: Application parameter` > `Mastering`  
    (2) Enter the joint number in `Joint Number` > Click `Confirm`  
    (3) Re-enter the mastering plugin to make sure the joint settings are correct.  
    (4) If it's okay, `motor on` > `enable switch on` > Click `Go to the enc offset`.    
        &rightarrow; Move to the origin position of the previously set.  
    (5) Mount the sensor on the joint entered in (2).  
    (6) Make sure the sensor tip is near the V groove.  
        &rightarrow; If it is not located in the V groove, remove the sensor and repeat step 2 above.  
    (7) 2. Click the `2. Start Mastering`.    
    (8) When mastering is complete, click `OK`.  
    (9) Remove the sensor.  
    (10) If there are additional joint to mastering, proceed again from (1).  


<br>

4. ⭐After mastering of all axes is completed, move to the updated encoder origin.⭐  
    - `TP` > `system` > `3: Robot parameter` > `4: Encoder offset` > `Moving` > `Shift + OK` > `OK`  
    - The `Corrected encoder` has already been updated, so its value will not change even if the robot moves to the origin.  

<br>

5. Check whether encoder offset is corrected after mastering.  
    - `TP` > `system` > `3: Robot parameter` > `4: Encoder offset`  
    - Please check whether the encoder offset value updated through mastering is the same as the `Corrected encoder` value.  
    - Check whether the `Current encoder` value for each axis is `0x400000`.  

