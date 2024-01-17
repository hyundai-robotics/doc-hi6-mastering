## 1.2 Contact sensor-based robot mastering 
This user manual contains information on the `contact sensor-based` robot mastering function.  
More accurate corrections are possible by using the corresponding `digital contact sensor`.

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

<br>

### 1.2.4. Full mastering process

**1. Set encoder offset by eye**  
- 1-a) The user jogs with TP based on the V groove or the scale bar mounted on the robot (reference point setting).
- 1-b) Perform encoder offset correction for the visually adjusted position for each axis.
- The way of Encoder offset correction )  
  TP > system > Engineer mode (R: 314) > 3: Robot paramter > 4: Encoder offset > Click the `Corrected encoder` value of current axis > Click the `Reset one` button

<br>

**2. Attach the contact sensor**  
- <div>
    <img src="../../_assets/00_mastering_Vdent_render.png" style="max-height: 20vh; max-width: 15vw">
    <img src="../../_assets/01_mastering_real_picture.png" style="max-height: 20vh; max-width: 12.3vw"><br>Fig 1-2. Mastering kit installation example (left: render image, right: real image)
    </div>

<br>

**3. Mastering-based encoder offset correction**
- 3-a) After completing step 1, enter the mastering plugin and click the `1. Go to the enc offset` button.
- 3-b) Visually check whether the robot is nearby the V groove. Then click the `2. Start mastering` button.
- 3-c) Start mastering
- The sensor moves up and down or side to side passing through the `V-groove`.
- Based on the sensor value that varies as it goes through the `V-groove`, the central location of the groove is determined.
- After identification, encoder offset is performed to correct the origin based on the center point.

