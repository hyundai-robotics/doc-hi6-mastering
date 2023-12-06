# Hi6 Mastering Function Manual

{% hint style="warning" %} 
The information provided in this product manual is the property of Hyundai Robotics.

It cannot be reproduced or redistributed in part or whole without written consent from Hyundai Robotics, and it cannot be provided to third parties or used for other purposes.

The manual can change without prior notification.


**Copyright ⓒ 2023 by HD Hyundai Robotics**
{% endhint %}# 1 Introduction

This manual covers the robot mastering function.  
This guidebook is predicated on fundamental understanding robot functioning.  
Please click the following [link](https://hrbook-hrc.web.app/#/view/doc-hi6-operation/english-tp630/README) for details on setting up and using the Hi6 robot controller.

- [1.1 About Robot Mastering](../01_intro/1-about_mastering/README.md)
    - 1.1.1 About Robot Mastering

<br>

- [1.2 Contact sensor-based robot mastering](../01_intro/2-about_contact_based_mastering/README.md)
    - 1.2.1. Mastering equipment
    - 1.2.2. Operating mode
    - 1.2.3. Operating concept
    - 1.2.4. Operating description
## 1.1 About Robot Mastering

- The robot's mechanical origin could vary if situations like axis distortion or drive source replacement take occurred during shipping or in the field. The mastering function is required at this time.
- The mastering function is used to improve the precision of robot motion and repair the mechanical origin.
- A digital contact sensor is used to operate the mastering in this manual.<br>
  The sensor is attached to each axis of the robot and detects the V-groove <br> while moving from -1.5 degrees to +1.5 degrees based on the starting point.<br>
  The detected V-groove position is corrected to the mechanical origin.<div>
<img src="../../_assets/12_mastering_concept_eng.PNG" style="max-height: 25vh; max-width: 38.5vw"><br>
Fig 1-1. a. Starting point(axis distortion status), 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
b. V-groove detection during mastering
</div>## 1.2 Contact sensor-based robot mastering 
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

### 1.2.4. Operating description
- Contact sensors are attached in the following manner 

    <div>
    <img src="../../_assets/00_mastering_Vdent_render.png" style="max-height: 20vh; max-width: 15vw">
    <img src="../../_assets/01_mastering_real_picture.png" style="max-height: 20vh; max-width: 12.3vw"><br>Fig 1-2. Mastering kit installation example (left: render image, right: real image)
    </div>
<br>

- The sensor moves up and down or side to side passing through the `V-groove`.
- Based on the sensor value that varies as it goes through the `V-groove`, the central location of the groove is determined.
- After identification, encoder offset is performed to correct the origin based on the center point.

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
  - 2.3.2 App setting configuration## 2.1 Mastering Kit
### 2.1.1 Contact sensor components
- **Sensor & Power adapter** 

    <div>
    <img src="../../_assets/02_sensor.PNG" style="max-height: 23vh;max-width: 16vw">
    <img src="../../_assets/03_communication_module.PNG" style="max-height: 23vh; max-width: 25vw">
    </div>
    Fig 2-1. a. Contact sensor&nbsp;&nbsp;&nbsp;&nbsp; b. Communication module
<br>

<br>

- **Cable**   
    <div>
    <img src="../../_assets/04_power_adapter.PNG" style="max-height: 20vh; max-width: 15.9vw">
    <img src="../../_assets/05_lan_cable.PNG" style="max-height: 20vh; max-width: 17.02vw"></div>
    Fig 2-2.&nbsp;&nbsp; a. power adapter&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;b. ethernet cable
<br>

<br>

- **S/W**  
This package includes a mastering App and a controller setup program.

<br>

### 2.1.2 Contact sensor connections
- Connect the sensor as shown in the photo on the Fig 2-1 b.

<br>

### 2.1.3 Specifications
- The mastering kit has the interface specifications below.

    |feature|detail|
    |:----|:----|
    |`Sensor Type`| `Digital contact` |
    |`Protocol`| `Ethernet` (TCP/IP) |
    |`Cycle`| `5 msec` |

<br>
<br>## 2.2 Initial setup and Connection
### 2.2.1. Contact sensor initialization
**Initialization only needs to be done <u>once for one axis before fixing.</u>**   

Keep in mind

1) After connection, if the sensor's measurement value is a `negative number` as shown in Fig 2-3.a, `mastering cannot proceed`.  
2) Therefore, please press the ‘preset button’ while ‘holding the sensor’ as shown in Fig 2-3.a.  
3) After presetting, check whether a `positive value` is measured `when sensor is pressed`, as shown in Fig 2-3.c.  
4) **After finishing mastering each robot axis, you need to ensure that the measured value is `positive`.**

    <div>
    <img src="../../_assets/06_preset.PNG" style="max-height: 20vh; max-width: 22.2vw">
    <img src="../../_assets/09_preset_pressed.PNG" style="max-height: 20vh; max-width: 22vw">
    <img src="../../_assets/07_pressed.PNG" style="max-height: 20vh; max-width: 20vw"><br>
    Fig 2-3. a. Negative value when holding the sensor 
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    b. when pressing the preset button
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    c. Positive value when sensor is pressed
    </div>

<br>
<br>

### 2.2.2. Communication settings for contact sensor
- The software bundle includes the mastering setup application. Install the software on a different computer.
- **<u>If you utilize a company computer, please note that the 'IP Search' function is generally not permitted by company security policies.</u>**
- In the case of above, you can set the ip configure by using personal computer.
- Following membership registration, you are able to use this program.
- After finishing communication setting, please connect the hardwares(communicator, ethernet cable) like [Fig 2-1 b.Communication module](../1-kit_description/README.md).

    <div>
    <img src="../../_assets/08_ip_configuration.PNG" style="max-height: 30vh; max-width: 35vw">

    Fig 2-4. [IP configurator](https://www.keyence.co.kr/download/download/confirmation/?dlAssetId=AS_135945&dlSeriesId=&dlModelId=&dlLangId=&dlLangType=en-GB)
    <br>- `Network Adaptor` : Network adaptor info for connected computer.
    <br>- `IP Search Range` : Searching for the connected device's IP address.
    <br>- `IP Address/Mac Address` : IP address and MAC address of the connected device
    <br>- `IP Setting/Reset` : IP settings button (edit) and reset button (<u>**only for changing IP settings**</u>)
    </div>## 2.3 Mastering app configuration
Once the mastering APP installation is successfully completed, the mastering function can be performed.  
After finishing several configuration setting for mastering, mastering could be performed easily with few buttons.  
Mastering can be performed correctly only when you understand the conditions and contents of the movement.  

<br>

### 2.3.1 Install Mastering app
The mastering function was developed through Hi6 SDK, and this app must be installed on the Hi6 controller to use it.  

- `Install location` for hi6 controller  
/ata0:2/lib/hi6/apps/mastering

- `Install method`  
1) After an ethernet connection, transfer the source code using FTP transmission.  
2) After saving the source code to the USB, connect to the TP. Then copy and paste the source code utilizing TP's `5: File Management` function.

- `Installation precautions`  
To use the mastering APP after installation, the controller must be restarted.  
Reboot the TP if you still don't see the mastering APP in the application program after doing so.

<br>

### 2.3.2 App setting configuration
- `App location`  
TP : `home` > `system` > `4: Application parameter` > `23: Mastering`

<br>

- `Standby mode`

    <img src="../../_assets/10_mastering_app_eng.PNG" style="max-height: 30vh; max-width: 39vw"><br>
    Fig 2-5. Mastering app image  

- If you do not see the mastering APP in the application program, just reboot the TP.

    <img src="../../_assets/11_standbymode_eng.PNG" style="max-height: 30vh; max-width: 39vw"><br>
    Fig 2-6. Mastering `standby mode` image  

    - `IP Address` : Enter the ip address of the mastering communicator.  
    - `Port Number` : Enter the port number of the mastering communicator.  
    - `Joint Number` : Enter the number of target joint.  
    - `Mastering Status` : Display the mastering operation status.  
    - `Encoder Offset (Before / After)` : Display the encoder offset value (`bit`) of the current axis before and after mastering.  

<br>

- How to save mastering IP and port number settings  
    1) Enter the preset ip, port. - 
    [2.2.2. Communication settings for contact sensor](../2-kit_initialization/README.md)  
    2) Save the configuration through the `shift` + `OK` to the hi6 controller.
### 3. Mastering operation

- [3.1. Environment & process](./1-mastering_step/README.md)
  - 3.1.1 Environment
  - 3.1.2 Operation process - summary
  - 3.1.3 Operation process - Details
  - 3.1.4 Results - image
  - 3.1.5 Reference

<br>

- [3.2. Error Code for Mastering](./2-error/README.md)
  - 3.2.1 Error Image
  - 3.2.2 Summary of Errors## 3.1. Environment & process
### 3.1.1 Environment
- Before mastering is performed, the mastering kit must be installed near the `V-groove`.
<br>Otherwise, an `'ERROR_VAL_THRESHOLD'` error may be returned.
- Operates only in manual mode and motor on.
- Please holding the enable switch until the operation ends.

<br>
<br>

### 3.1.2 Operation process - summary
1. In [Standby mode](../../02_about_kit/3-com_initialization/README.md), enter the joint number then press the '`shift + OK`' for saving configuration.
2. Click the '`1.Go to the enc offset`' button.
3. After step 2., click the '`2.Start mastering`' button.
4. After step 3., enter the next target joint number, do step 2. again.
5. After completing the mastering process for all joints, save the corrected encoder offset values using the procedures listed below.
   - `home` > `supervisor mode(R button + 314)` > `system` > `3: Robot parameter` > `4: Encoder offset` > `shift + OK` > `OK`

<br>
<br>

### 3.1.3 Operation process - Details
- Each joint follows below procedures.
- Procedure status will be displayed on the mastering status block.
  
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

- After completing (1) to (8) for current joint, enter the next joint number then press the '`shift + OK`' to update joint info.
- After updating the joint status, repeat the steps from (2) to (8) above.
- After completing the mastering process for all joints, save the corrected encoder offset values using the procedures listed below.
   - `home` > `supervisor mode(R button + 314)` > `system` > `3: Robot parameter` > `4: Encoder offset` > `shift + OK` > `OK`

<br>
<br>

### 3.1.4 Results - image

- The encoder offset value is displayed on the `Encoder Offset(Before/After)` by the unit of `bit(hexa)`.
  - `Left block` : `Pre`-encoder offset value `before mastering`.  
  - `Right block` : `Post`-encoder offset value `after mastering`.  

      <div>
      <img src="../../_assets/13_standby_eng.png" style="max-height: 30vh; max-width: 34vw">
      <img src="../../_assets/14_mastering_end_eng.png" style="max-height: 30vh; max-width: 34vw"><br>
      Fig 3-1.&nbsp;&nbsp;&nbsp;&nbsp;a. Standby mode image
      &nbsp;&nbsp;&nbsp;&nbsp;
      b. Mastering complete image
      </div>

<br>
<br>

### 3.1.5 Reference
- The reason of using `bit` for display encoder offset values.
  - It is intuitive to display angle differences when comparing mastery results, however changes of smaller than 0.01 cannot be assessed.
  - The current mastering process shifts the origin by between -1.5 and 1.5 degrees.
  - It is more accurate to display the encoder value in bit units in order to convey these minute variances.

## 3.2. Error Code for Mastering
---
### 3.2.1 Error Image
- If an error occurs during mastering operation, an error code is output in ‘Mastering Progress Status’.
- ex) `ERROR_TCP_CONNECT`, `ERROR_MOTOR_ON_CHK`

    <div>
    <img src="../../_assets/15_err_motor_on_eng.png" style="max-height: 28vh; max-width: 32vw">
    <img src="../../_assets/16_err_tcp_connect_eng.png" style="max-height: 28vh; max-width: 32vw"><br>
    Fig 3-2. The example image for error status 
    </div>

<br>
<br>

### 3.2.2 Summary of Errors
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
