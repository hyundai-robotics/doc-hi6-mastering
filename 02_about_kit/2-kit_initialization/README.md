## 2.2 初始设置和连接

#### 2.2.1. 接触传感器初始化
**初始化只需在固定前对一个轴<u>进行一次。</u>**   

请记住

1) 连接后，如果传感器的测量值为图2-3.a所示的`负数`，则`无法进行归零`。  
2) 因此，请在按图2-3.a所示的情况下，按下"预设按钮"的同时"保持传感器"。  
3) 预设后，请检查在传感器被按下时，测量到的值是否为`正值`，如图2-3.c所示。  
4) **在完成每个机器人轴的归零后，需要确保测量值为`正数`。**

<div style="width: 630px;">
  <table style="margin-left: 0; border: none; border-collapse: collapse; width: 630px; table-layout: fixed;">
    <tr>
      <td style="width: 210px; border: none; vertical-align: bottom; padding: 0 5px 0 0;">
        <img src="../../_assets/06_preset.PNG" style="width: 100%; height: 160px; object-fit: cover; display: block;" alt="Negative value">
      </td>
      <td style="width: 210px; border: none; vertical-align: bottom; padding: 0 5px;">
        <img src="../../_assets/09_preset_pressed.PNG" style="width: 100%; height: 160px; object-fit: cover; display: block;" alt="Preset button">
      </td>
      <td style="width: 210px; border: none; vertical-align: bottom; padding: 0 0 0 5px;">
        <img src="../../_assets/07_pressed.PNG" style="width: 100%; height: 160px; object-fit: cover; display: block;" alt="Positive value">
      </td>
    </tr>
    <tr style="font-size: 0.85em; line-height: 1.3;">
      <td style="border: none; padding-top: 10px; vertical-align: top; word-break: keep-all; padding-right: 5px;">
        图 2.2.1. a. 持续传感器时的负值 
      </td>
      <td style="border: none; padding-top: 10px; vertical-align: top; word-break: keep-all; padding-left: 5px;">
        b. 按下预设按钮时
      </td>
      <td style="border: none; padding-top: 10px; vertical-align: top; word-break: keep-all; padding-left: 5px;">
        c. 传感器被按下时的正值
      </td>
    </tr>
  </table>
</div>

<br>

#### 2.2.2. 接触传感器的通信设置  
- 软件包包括归零设置应用程序。请在另一台计算机上安装软件。  
- **<u>如果您使用公司计算机，请注意公司安全政策通常不允许使用"IP搜索"功能。</u>**  
- 在这种情况下，您可以使用个人计算机配置IP设置。  
 - 注册成为会员后，您将能够使用该程序。  
    - 完成通信设置后，请按照[图2-1 b.通信模块](../1-kit_description/README.md)连接硬件（通讯器、以太网电缆）。  
    <div style="width: 630px;">
      <table style="margin-left: 0; border: none; border-collapse: collapse; width: 630px; table-layout: fixed;">
        <tr>
          <td style="border: none; vertical-align: bottom; padding: 0;">
            <img src="../../_assets/08_ip_configuration.PNG" style="max-height: 30vh; max-width: 100%; display: block;" alt="IP configuration">
          </td>
        </tr>
        <tr>
          <td style="border: none; padding-top: 10px; font-size: 0.9em; font-weight: bold;">
            图 2.2.2. <a href="https://www.keyence.co.kr/download/download/confirmation/?dlAssetId=AS_135945&dlSeriesId=&dlModelId=&dlLangId=&dlLangType=en-GB" target="_blank">IP配置器</a>
          </td>
        </tr>
        <tr>
          <td style="border: none; padding-top: 10px; font-size: 0.9em; line-height: 1.5; word-break: keep-all;">
            <ul style="margin: 0; padding-left: 20px; list-style-type: disc;">
              <li><code>网络适配器</code> : 连接计算机的网络适配器信息。</li>
              <li><code>IP搜索范围</code> : 搜索连接设备的IP地址。</li>
              <li><code>IP地址/Mac地址</code> : 连接设备的IP地址和MAC地址。</li>
              <li><code>IP设置/重置</code> : IP设置按钮（编辑）和重置按钮（<u><b>仅用于更改IP设置</b></u>）。</li>
            </ul>
          </td>
        </tr>
      </table>
    </div>
