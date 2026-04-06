## 2.3 Mastering app configuration

Once the mastering APP installation is successfully completed, the mastering function can be performed. 
Mastering can be performed correctly only when you understand the conditions and contents of the movement.

#### 2.3.1 Install Mastering app
The mastering function was developed through ${cont_model} SDK and must be installed on the controller.

- `Install location` for hi6 controller  
    - /ata0:2/lib/hi6/apps/mastering (com version <= V60.32)
- `Install method`  
    1) You can download the plugin by contacting the HD Hyundai Robot SW development team.  
    2) After an ethernet connection, transfer the source code using FTP transmission.  
    3) After saving the source code to the USB, connect to the TP.  
    4) Then copy and paste the source code utilizing TP's `5: File Management` function.
- `Installation precautions`
    1) To use the mastering APP after installation, the controller must be restarted.  
    2) Reboot the TP if you still don't see the mastering APP in the application program after doing so.

#### 2.3.2 App setting configuration
- `App location`  
TP : `home` > `system` > `4: Application parameter` > `23: Mastering`

<div style="width: 630px;">
  <p>- <code>Standby mode</code></p>
  <table style="margin-left: 0; border: none; border-collapse: collapse; width: 530px; table-layout: fixed;">
    <tr>
      <td style="border: none; vertical-align: bottom; padding: 0;">
        <img src="../../_assets/10_mastering_app_eng.PNG" style="width: 100%; height: auto; display: block;" alt="Mastering app">
      </td>
    </tr>
    <tr>
      <td style="border: none; padding-top: 10px; font-size: 0.9em; font-weight: bold;">
        Fig 2.3.1. Mastering app image
      </td>
    </tr>
  </table>

  <div style="margin: 8px 0 2px 0;">- If you do not see the APP, just reboot the TP.</div>

  <table style="margin-left: 0; border: none; border-collapse: collapse; width: 530px; table-layout: fixed;">
    <tr>
      <td style="border: none; vertical-align: bottom; padding: 0;">
        <img src="../../_assets/11_standbymode_eng.PNG" style="width: 100%; height: auto; display: block;" alt="Mastering standby mode">
      </td>
    </tr>
    <tr>
      <td style="border: none; padding-top: 10px; font-size: 0.9em; font-weight: bold;">
        Fig 2.3.2. Mastering <code>standby mode</code> image
      </td>
    </tr>
    <tr>
      <td style="border: none; padding-top: 15px; font-size: 0.9em; line-height: 1.6;">
        <ul style="margin: 0; padding-left: 20px; list-style-type: disc;">
          <li><code>IP Address</code> : Enter the ip address of the mastering communicator.</li>
          <li><code>Port Number</code> : Enter the port number of the mastering communicator.</li>
          <li><code>Joint Number</code> : Enter the number of target joint.</li>
          <li><code>Mastering Status</code> : Display the mastering operation status.</li>
          <li><code>Encoder Offset (Before / After)</code> : Display the encoder offset value (<code>bit</code>) of the current axis before and after mastering.</li>
        </ul>
      </td>
    </tr>
  </table>
</div>

How to save mastering IP and port number settings  
    1. Enter the preset ip, port. - [2.2.2. Communication settings for contact sensor](../2-kit_initialization/README.md)  
    2. Save the configuration through the `shift` + `OK` to the ${cont_model} controller.
