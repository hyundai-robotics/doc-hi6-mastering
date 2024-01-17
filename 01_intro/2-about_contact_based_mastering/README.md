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
  TP > system > Engineer mode (R: 314) > 3: Robot parameter > 4: Encoder offset > Click the `Corrected encoder` value of current axis > Click the `Reset one` button

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
    > c.1) Move `start-point`: Set `-1.5 degrees` as the start-point and move based on the initial position.  
    > c.2) Setting the `end-point`: Set the end point `+3.0 degrees` based on the start-point as the destination point.  
    > c.3) `Forward` scan: Scan in the direction `start point -> end point`.  
    > c.4) `Reverse` scan: Scan in the direction `end point -> Start point`.  
    > c.5) `Encoder offset correction`: Encoder offset is corrected based on encoder bit of the V-groove detected after scanning.  
    > c.6) `Move to encoder offset`: Move to the newly set encoder offset position (V-groove).  
- 3-d) Saving the corrected encoder offset data to the Hi6COM.  
    > d.1) TP > Engineer mode (R: 314) > system > 3: Robot parameter > 4: Encoder offset  
    > d.2) Click the shift + `OK` button > `OK` button
    > !caution! If this process is omitted, the encoder offset value will disappear when the Hi6COM is rebooted.  

<br>

**4. Check whether encoder offset is corrected after mastering**
- Mastering is the process of recalibrating the current encoder value based on `0x400000` and updating the encoder offset value.
- 따라서 전 축 마스터링 완료 후 엔코더 오프셋 값들로 이동했을 때 하기 두 가지를 확인하면 됩니다.
    1. `현재 엔코더` 값이 `0x400000` 인지 확인.
    2. `엔코더 오프셋` 값이, `마스터링 된 후의 값`인지 확인.
- 확인 과정    
a.1) TP > 엔지니어모드 진입(R: 314) > 2: 시스템 > 3: 로봇 파라미터 > 4: 엔코더 옵셋  
a.2) `로봇이동` 클릭   
a.3) `보정된 엔코더`의 값들이 `마스터링 된 후의 엔코더 오프셋` 값들인지 확인.  
a.4) 그 때의 현재 엔코더 값이 `0x400000` 값으로 설정되어있는지 확인.