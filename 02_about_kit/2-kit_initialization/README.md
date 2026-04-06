## 2.2 Initial setup and Connection

#### 2.2.1. Contact sensor initialization
**Initialization only needs to be done <u>once for one axis before fixing.</u>**   
Keep in mind
1) After connection, if the sensor's measurement value is a `negative number` as shown in Fig 2.2.1.a, `mastering cannot proceed`.  
2) Therefore, please press the 'preset button' while 'holding the sensor' as shown in Fig 2.2.1.a.  
3) After presetting, check whether a `positive value` is measured `when sensor is pressed`, as shown in Fig 2.2.1.c.  
4) **After finishing mastering each robot axis, you need to ensure that the measured value is `positive`.**

<div style="width: 657px;">
  <table style="margin-left: 0; border: none; border-collapse: collapse; width: 630px; table-layout: fixed;">
    <tr>
      <td style="width: 219px; border: none; vertical-align: bottom; padding: 0 5px 0 0;">
        <img src="../../_assets/06_preset.PNG" style="width: 100%; height: 160px; object-fit: cover; display: block;" alt="Negative value">
      </td>
      <td style="width: 219px; border: none; vertical-align: bottom; padding: 0 5px;">
        <img src="../../_assets/09_preset_pressed.PNG" style="width: 100%; height: 160px; object-fit: cover; display: block;" alt="Preset button">
      </td>
      <td style="width: 219px; border: none; vertical-align: bottom; padding: 0 0 0 5px;">
        <img src="../../_assets/07_pressed.PNG" style="width: 100%; height: 160px; object-fit: cover; display: block;" alt="Positive value">
      </td>
    </tr>
    <tr style="font-size: 0.85em; line-height: 1.3;">
      <td style="border: none; padding-top: 10px; vertical-align: top; word-break: keep-all; padding-right: 5px;">
        Fig 2.2.1. a. Negative value when holding the sensor
      </td>
      <td style="border: none; padding-top: 10px; vertical-align: top; word-break: keep-all; padding: 10px 5px 0 5px;">
        b. when pressing the preset button
      </td>
      <td style="border: none; padding-top: 10px; vertical-align: top; word-break: keep-all; padding-left: 5px;">
        c. Positive value when sensor is pressed
      </td>
    </tr>
  </table>
</div>

#### 2.2.2. Communication settings for contact sensor  
- The software bundle includes the mastering setup application. Install the software on a different computer.  
- **<u>If you utilize a company computer, please note that the 'IP Search' function is generally not permitted by company security policies.</u>**  
- In the case of above, you can set the ip configure by using personal computer.  
 - Following membership registration, you are able to use this program.  
    - After finishing communication setting, please connect the hardwares(communicator, ethernet cable) like [Fig 2.1.1 b.Communication module](../1-kit_description/README.md).

<div style="width: 630px;">
  <table style="margin-left: 0; border: none; border-collapse: collapse; width: 630px; table-layout: fixed;">
    <tr>
      <td style="border: none; vertical-align: bottom; padding: 0;">
        <img src="../../_assets/08_ip_configuration.PNG" style="max-height: 30vh; max-width: 430px; display: block;" alt="IP configuration">
      </td>
    </tr>
    <tr>
      <td style="border: none; padding-top: 10px; font-size: 0.9em; font-weight: bold;">
        Fig 2.2.2. <a href="https://www.keyence.co.kr/download/download/confirmation/?dlAssetId=AS_135945&dlSeriesId=&dlModelId=&dlLangId=&dlLangType=en-GB" target="_blank">IP configurator</a>
      </td>
    </tr>
    <tr>
      <td style="border: none; padding-top: 10px; font-size: 0.9em; line-height: 1.6;">
        <ul style="margin: 0; padding-left: 20px; list-style-type: disc;">
          <li><code>Network Adaptor</code> : Network adaptor info for connected computer.</li>
          <li><code>IP Search Range</code> : Searching for the connected device's IP address.</li>
          <li><code>IP Address/Mac Address</code> : IP address and MAC address of the connected device</li>
          <li><code>IP Setting/Reset</code> : IP settings button (edit) and reset button (<u>only for changing IP settings</u>)</li>
        </ul>
      </td>
    </tr>
  </table>
</div>
