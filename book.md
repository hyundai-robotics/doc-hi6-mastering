
[__SOURCE](01_intro/README.md)
# 1 Introduction

This manual covers the robot mastering function.  
This guidebook is predicated on fundamental understanding robot functioning.  
Please click the following [link](https://hrbook-hrc.web.app/#/view/doc-hi6-operation/en-tp630/README?cont_model=${cont_model}) for details on setting up and using the ${cont_model} robot controller.

- [1.1 About Robot Mastering](../01_intro/1-about_mastering/README.md)
    - 1.1.1 About Robot Mastering

<br>

- [1.2 Contact sensor-based robot mastering](../01_intro/2-about_contact_based_mastering/README.md)
    - 1.2.1. Mastering equipment
    - 1.2.2. Operating mode
    - 1.2.3. Operating concept
    - 1.2.4. Operating description

[__SOURCE](01_intro/1-about_mastering/README.md)
## 1.1 About Robot Mastering

- Mastering is a function used to improve robot motion accuracy by compensating for the mechanical zero (home) position of each axis.
- When the mechanical zero position is defined for the first time, mastering must be performed.

- After initial mastering, the mechanical zero position may change due to <br>
  factors such as axis twisting, replacement of drive components, or mechanical wear.
- In such cases, mastering must be performed again to restore accurate motion control.

- Mastering vs. Calibration
    - Mastering is the process of establishing the mechanical zero position that serves as the reference for coordinate calculations.
    - Calibration is the process of correcting positional errors while maintaining the established mechanical zero reference.
    - Calibration must always be performed after mastering has been completed.

- A digital contact sensor is used to operate the mastering in this manual.<br>
  The sensor is attached to each axis of the robot and detects the V-groove <br> while moving from -1.5 degrees to +1.5 degrees based on the starting point.<br>
  The detected V-groove position is corrected to the mechanical origin.<br><div>
<img src="../../_assets/12_mastering_concept_eng.PNG" style="max-width: 60vw"><br>
Fig 1.1. a. Starting point(axis distortion status), 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
b. V-groove detection during mastering
</div>

[__SOURCE](01_intro/2-about_contact_based_mastering/README.md)
## 1.2 Contact sensor-based robot mastering 
This user manual contains information on the `contact sensor-based` robot mastering function.  
More accurate corrections are possible by using this sensor.    

<br>

#### 1.2.1. Mastering equipment
- **Robot** <br>- where Mastering device will be connected
- **${cont_model} robot controller** <br>- where Mastering-App will be installed
- **Mastering kit** <br>- Power + Sensor + Communication module

<br>

#### 1.2.2. Operating mode
- The operation mode of the robot must be set to `manual mode`.
- The procedure can only be carried out with the `motor on status` and the `enable switch` turned on.

<br>

#### 1.2.3. Operating concept
- The digital contact sensor scans the `V-groove` of the mastering block mounted to each axis of the robot to locate a more precise origin. ([Fig 1-1](../1-about_mastering/README.md))  
- After scanning the `V-groove`, a new encoder offset will be set relative to the detected vector of `V-groove`.  
- Then calculate the `Corrected encoder` value.  

<br>

#### 1.2.4. Overall Process  
1. Enter `engineer mode`    
2. Encoder offset correction - by direct teaching  
3. Encoder offset correction - by using plugin  
    (1) Enter the mastering plugin.  
    (2) In [standby mode](../../02_about_kit/3-com_initialization/README.md), enter the joint number > `Shift + OK` > `OK`  
    (3) Re-entry into the mastering plug-in.   
    (4) Click `1.Go to the enc offset` button.  
    (5) Mount the sensor on the joint.    
    (6) Make sure the end of the sensor is near the `V-groove`.  
    (7) Click the `2.Start mastering` button.  
    (8) Click `OK` when finished.  
    (9) Please remove the sensor.  
    (10) If there are additional axes that need to be mastered, proceed again from (1).  
4. After mastering of all axes is completed, move to the updated encoder origin.
5. Check whether encoder offset is corrected after mastering.  


[__SOURCE](02_about_kit/README.md)
# 2. System configuration

- [2.1 Mastering Kit](../02_about_kit/1-kit_description/README.md)
  - 2.1.1 Contact sensor components
  - 2.1.2 Contact sensor connections
  - 2.1.3 Specifications

<br>

- [2.2 Initial setup and Connection](../02_about_kit/2-kit_initialization/README.md)
  - 2.2.1 Contact sensor initialization
  - 2.2.2 Communication settings for contact sensor
  
<br>

- [2.3 Mastering app configuration](../02_about_kit/3-com_initialization/README.md)
  - 2.3.1 Install Mastering app
  - 2.3.2 App setting configuration
[__SOURCE](02_about_kit/1-kit_description/README.md)
## 2.1 Mastering Kit

#### 2.1.1 Contact sensor components
- **Sensor & Power adapter** 

    <div>
    <img src="../../_assets/02_sensor.PNG" style="max-height: 23vh;max-width: 16vw">
    <img src="../../_assets/03_communication_module.PNG" style="max-height: 23vh; max-width: 25vw">
    </div>
    Fig 2.1.1. a. Contact sensor&nbsp;&nbsp;&nbsp;&nbsp; b. Communication module
<br>

<br>

- **Cable**   
    <div>
    <img src="../../_assets/04_power_adapter.PNG" style="max-height: 30vh; max-width: 35.9vw">
    <img src="../../_assets/05_lan_cable.PNG" style="max-height: 30vh; max-width: 37.02vw"></div>
    Fig 2.1.2.&nbsp;&nbsp; a. power adapter&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;b. ethernet cable
<br>

<br>

- **S/W**  
This package includes a mastering App and a controller setup program.

<br>

#### 2.1.2 Contact sensor connections
- Connect the sensor as shown in the photo on the Fig 2-1 b.

<br>

#### 2.1.3 Specifications
- The mastering kit has the interface specifications below.

    |feature|detail|
    |:----|:----|
    |`Sensor Type`| `Digital contact` |
    |`Protocol`| `Ethernet` (TCP/IP) |
    |`Cycle`| `5 msec` |

<br>
<br>

[__SOURCE](02_about_kit/2-kit_initialization/README.md)
## 2.2 Initial setup and Connection

#### 2.2.1. Contact sensor initialization
**Initialization only needs to be done <u>once for one axis before fixing.</u>**   

Keep in mind

1) After connection, if the sensor's measurement value is a `negative number` as shown in Fig 2-3.a, `mastering cannot proceed`.  
2) Therefore, please press the 'preset button' while 'holding the sensor' as shown in Fig 2-3.a.  
3) After presetting, check whether a `positive value` is measured `when sensor is pressed`, as shown in Fig 2-3.c.  
4) **After finishing mastering each robot axis, you need to ensure that the measured value is `positive`.**

    <div>
    <img src="../../_assets/06_preset.PNG" style="max-height: 30vh; max-width: 32.2vw">
    <img src="../../_assets/09_preset_pressed.PNG" style="max-height: 30vh; max-width: 32vw">
    <img src="../../_assets/07_pressed.PNG" style="max-height: 30vh; max-width: 30vw"><br>
    Fig 2.2.1. a. Negative value when holding the sensor 
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    b. when pressing the preset button
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    c. Positive value when sensor is pressed
    </div>

<br>
<br>

#### 2.2.2. Communication settings for contact sensor
- The software bundle includes the mastering setup application. Install the software on a different computer.
- **<u>If you utilize a company computer, please note that the 'IP Search' function is generally not permitted by company security policies.</u>**
- In the case of above, you can set the ip configure by using personal computer.
- Following membership registration, you are able to use this program.
- After finishing communication setting, please connect the hardwares(communicator, ethernet cable) like [Fig 2-1 b.Communication module](../1-kit_description/README.md).

    <div>
    <img src="../../_assets/08_ip_configuration.PNG" style="max-height: 30vh; max-width: 35vw">

    Fig 2.2.2. [IP configurator](https://www.keyence.co.kr/download/download/confirmation/?dlAssetId=AS_135945&dlSeriesId=&dlModelId=&dlLangId=&dlLangType=en-GB)
    <br>- `Network Adaptor` : Network adaptor info for connected computer.
    <br>- `IP Search Range` : Searching for the connected device's IP address.
    <br>- `IP Address/Mac Address` : IP address and MAC address of the connected device
    <br>- `IP Setting/Reset` : IP settings button (edit) and reset button (<u>**only for changing IP settings**</u>)
    </div>

[__SOURCE](02_about_kit/3-com_initialization/README.md)
## 2.3 Mastering app configuration

Once the mastering APP installation is successfully completed, the mastering function can be performed.  
After finishing several configuration setting for mastering, mastering could be performed easily with few buttons.  
Mastering can be performed correctly only when you understand the conditions and contents of the movement.  

<br>

#### 2.3.1 Install Mastering app
The mastering function was developed through ${cont_model} SDK, and this app must be installed on the ${cont_model} controller to use it.  

- `Install location` for ${cont_model} controller  
    - /ata0:2/lib/hi6/apps/mastering
- `Install method`  
    1) You can download the plugin by contacting the HD Hyundai Robot SW development team.  
    2) After an ethernet connection, transfer the source code using FTP transmission.  
    3) After saving the source code to the USB, connect to the TP.  
    4) Then copy and paste the source code utilizing TP's `5: File Management` function.
- `Installation precautions`
    1) To use the mastering APP after installation, the controller must be restarted.  
    2) Reboot the TP if you still don't see the mastering APP in the application program after doing so.

<br>

#### 2.3.2 App setting configuration
- `App location`  
TP : `home` > `system` > `4: Application parameter` > `23: Mastering`

<br>

- `Standby mode`

    <img src="../../_assets/10_mastering_app_eng.PNG" style="max-width: 60vw"><br>
    Fig 2.3.1. Mastering app image  

- If you do not see the mastering APP in the application program, just reboot the TP.

    <img src="../../_assets/11_standbymode_eng.PNG" style="max-width: 60vw"><br>
    Fig 2.3.2. Mastering `standby mode` image  

    - `IP Address` : Enter the ip address of the mastering communicator.  
    - `Port Number` : Enter the port number of the mastering communicator.  
    - `Joint Number` : Enter the number of target joint.  
    - `Mastering Status` : Display the mastering operation status.  
    - `Encoder Offset (Before / After)` : Display the encoder offset value (`bit`) of the current axis before and after mastering.  

<br>

- How to save mastering IP and port number settings  
    1) Enter the preset ip, port. - 
    [2.2.2. Communication settings for contact sensor](../2-kit_initialization/README.md)  
    2) Save the configuration through the `shift` + `OK` to the ${cont_model} controller.

[__SOURCE](03_operation/README.md)
# 3. Mastering operation

- [3.1. Environment & process](./1-mastering_step/README.md)
  - 3.1.1 Environment
  - 3.1.2 Operation process - summary
  - 3.1.3 Operation process - Details
  - 3.1.4 Results - image
  - 3.1.5 Reference

<br>

- [3.2. Error Code for Mastering](./2-error/README.md)
  - 3.2.1 Error Image
  - 3.2.2 Summary of Errors

[__SOURCE](03_operation/1-mastering_step/README.md)
## 3.1. Environment & process

#### 3.1.1 Environment
{% hint style="warning" %}
**Before starting mastering, `the tip of the mastering sensor` must be nearby `V-groove`.  
Violation of this may result in `damage to the sensor tip` or return an `ERROR_VAL_THRESHOLD` error.**
{% endhint %}
- Operates only in manual mode and motor on.
- Please holding the enable switch until the operation ends.

<br>
<br>

#### 3.1.2 Operation process - summary
1. Enter `engineer mode`    
2. Encoder offset correction - by direct teaching  
3. Encoder offset correction - by using plugin  
    (1) Enter the mastering plugin.  
    (2) In [standby mode](../../02_about_kit/3-com_initialization/README.md), enter the joint number > `Shift + OK` > `OK`  
    (3) Re-entry into the mastering plug-in.   
    (4) Click `1.Go to the enc offset` button.  
    (5) Mount the sensor on the joint.    
    (6) Make sure the end of the sensor is near the `V-groove`.  
    (7) Click the `2.Start mastering` button.  
    (8) Click `OK` when finished.  
    (9) Please remove the sensor.  
    (10) If there are additional axes that need to be mastered, proceed again from (1).  
4. After mastering of all axes is completed, move to the updated encoder origin.
5. Check whether encoder offset is corrected after mastering.  
    
<br>
<br>

#### 3.1.3 Operation process - Details
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

2. Encoder offset correction - by using plugin  
    (1) After completing the steps in 1, enter the mastering plugin  
        &rightarrow; `TP` > `system` > `4: Application parameter` > `Mastering`  
    (2) Enter the joint number in `Joint Number` > Click `Confirm`  
    (3) Re-enter the mastering plugin to make sure the joint settings are correct.  
    (4) If it's okay, `motor on` > `enable switch on` > Click `Go to the enc offset`.    
        &rightarrow; Move to the origin position of the previously set.  
    (5) Mount the sensor on the joint entered in (2).  
        <div>
        <img src="../../_assets/00_mastering_Vdent_render.png" style="max-height: 30vh; max-width: 35vw">
        <img src="../../_assets/01_mastering_real_picture.png" style="max-height: 30vh; max-width: 32.3vw"><br>Fig 3.1.1. Mastering sensor installation image (left: render image, right: real image)
        </div>
    (6) Make sure the sensor tip is near the V groove.  
        &rightarrow; If it is not located in the V groove, remove the sensor and repeat step 2 above.  
    (7) 2. Click the `2. Start Mastering`.    
    (8) When mastering is complete, click `OK`.  
    (9) Remove the sensor.  
    (10) If there are additional joint to mastering, proceed again from (1).  


<br>

3. After mastering of all axes is completed, move to the updated encoder origin.
    - `TP` > `system` > `3: Robot parameter` > `4: Encoder offset` > `Moving` > `Shift + OK` > `OK`  
    - The `Corrected encoder` has already been updated, so its value will not change even if the robot moves to the origin.  

<br>

4. Check whether encoder offset is corrected after mastering.  
    - `TP` > `system` > `3: Robot parameter` > `4: Encoder offset`  
    - Please check whether the encoder offset value updated through mastering is the same as the `Corrected encoder` value.  
    - Check whether the `Current encoder` value for each axis is `0x400000`.  

<br>
<br>

#### 3.1.4 Test Process - Status Bar Log
|Order|Mastering status|Contents|
|:---:|:---:|:---|
|(1)|Standby|Initial image when entering the mastering app.|
|(2)|go to the offset pose...|The state when '`1.Go to the enc offset`' button is pressed.|
|(3)|reached the offset pose.|Complete message after '`1.Go to the enc offset`' operation.|
|(4)|Start mastering.|The first state of '`2.Start mastering`' button is pressed.|
|(5)|move to P1.|The state of moving to p1 direction after '`2.Start mastering`' button is pressed.|
|(6)|move to P2.|The state of moving to p2 direction after '`2.Start mastering`' button is pressed.|
|(7)|apply corrected enc offset.|The state of moving to the modified origin after mastering is completed.|
|(8)|mastering end.|The state of mastering is finished.|

<br>
<br>

#### 3.1.5 Results - image

- The encoder offset value is displayed on the `Encoder Offset(Before/After)` by the unit of `bit(hexa)`.
  - `Left block` : `Pre`-encoder offset value `before mastering`.  
  - `Right block` : `Post`-encoder offset value `after mastering`.  

      <div>
      <img src="../../_assets/13_standby_eng.png" style="max-height: 30vh; max-width: 40vw">
      <img src="../../_assets/14_mastering_end_eng.png" style="max-height: 30vh; max-width: 40vw"><br>
      Fig 3.1.2.&nbsp;&nbsp;&nbsp;&nbsp;a. Standby mode image
      &nbsp;&nbsp;&nbsp;&nbsp;
      b. Mastering complete image
      </div>

<br>
<br>

#### 3.1.6 Reference
- The reason of using `bit` for display encoder offset values.
  - It is intuitive to display angle differences when comparing mastery results, however changes of smaller than 0.01 cannot be assessed.
  - The current mastering process shifts the origin by between -1.5 and 1.5 degrees.
  - It is more accurate to display the encoder value in bit units in order to convey these minute variances.


[__SOURCE](03_operation/2-error/README.md)
## 3.2. Error Code for Mastering

#### 3.2.1 Error Image
- If an error occurs during mastering operation, an error code is output in 'Mastering Progress Status'.
- ex) `ERROR_TCP_CONNECT`, `ERROR_MOTOR_ON_CHK`

    <div>
    <img src="../../_assets/15_err_motor_on_eng.png" style="max-height: 30vh; max-width: 40vw">
    <img src="../../_assets/16_err_tcp_connect_eng.png" style="max-height: 30vh; max-width: 40vw"><br>
    Fig 3.2.1. The example image for error status 
    </div>

<br>
<br>

#### 3.2.2 Summary of Errors
This is a list of errors that can occur while performing mastering operations.  

|Error Code|Contents|Todo List|
|:---|:---|:---|
|`ERROR_MOTOR_ON_CHK`|Try mastering with the motor off.|Perform mastering with the motor on.|
|`ERROR_MOTOR_OFF_CHK`|Motor off detection when performing mastering.|When performing mastering, do not release the Enable SW until the function ends. Return to the initial position and re-execute mastering.|
|`ERROR_VAL_THRESHOLD`|`V-groove` was not detected during mastering.|V-home was not detected. After clicking button 1, place the sensor near the `V-groove` and resume mastering.|
|`ERROR_NO_SENSOR_VALS`|There is no sensor data recorded.|Return to the initial position and re-execute mastering. If repeated problems occur, check the plug-in APP software.|
|`ERROR_NO_ENC_VALS`|There is no encoder data recorded.|Return to the initial position and re-execute mastering. If repeated problems occur, check the plug-in APP software.|
|`ERROR_TCP_RES_FAIL`| TCP/IP communication response fail. | Check the connection status and setting environment of the contact sensor. |
|`ERROR_TCP_RES_NULL`| TCP/IP communication response null. | Check the connection status and setting environment of the contact sensor. |
|`ERROR_TCP_CONNECT` | TCP/IP communication connection fail. | Check the connection status and setting environment of the contact sensor. |
|`ERROR_PLAYBACK` | Playback Error. | Please restart the controller. |
