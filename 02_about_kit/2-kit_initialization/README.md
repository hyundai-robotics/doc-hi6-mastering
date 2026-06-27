## 2.2 初始设置和连接

#### 2.2.1. 接触传感器初始化
**初始化仅需在固定之前为一个轴<u>执行一次</u>。**  
请注意
1) 连接后，如果传感器的测量值为如图 2.2.1.a 所示的 `负数`， `无法进行掌握`。  
2) 因此，请按下“预设按钮”，同时如图 2.2.1.a 所示“握住传感器”。  
3) 预设完成后，请检查`当传感器被按下时`是否测得`正值`，如图 2.2.1.c 所示。  
4) **在完成每个机器人轴的掌握后，您需要确保测得的值为`正值`。**

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
        Fig 2.2.1. a. 握住传感器时的负值
      </td>
      <td style="border: none; padding-top: 10px; vertical-align: top; word-break: keep-all; padding: 10px 5px 0 5px;">
        b. 按下预设按钮时
      </td>
      <td style="border: none; padding-top: 10px; vertical-align: top; word-break: keep-all; padding-left: 5px;">
        c. 按下传感器时的正值
      </td>
    </tr>
  </table>
</div>

#### 2.2.2. 接触传感器的通信设置  
- 软件包包括掌握设置应用程序。请在另一台计算机上安装该软件。  
- **<u>如果您使用公司电脑，请注意，'IP 搜索'功能通常不符合公司安全政策。</u>**  
- 在这种情况下，您可以使用个人计算机进行 IP 配置。  
 - 在会员注册后，您可以使用此程序。  
    - 在完成通信设置后，请根据如[图 2.1.1 b. 通信模块](../1-kit_description/README.md)所示连接硬件(通信器、以太网电缆)。

<div style="width: 630px;">
  <table style="margin-left: 0; border: none; border-collapse: collapse; width: 630px; table-layout: fixed;">
    <tr>
      <td style="border: none; vertical-align: bottom; padding: 0;">
        <img src="../../_assets/08_ip_configuration.PNG" style="max-height: 30vh; max-width: 430px; display: block;" alt="IP configuration">
      </td>
    </tr>
    <tr>
      <td style="border: none; padding-top: 10px; font-size: 0.9em; font-weight: bold;">
        Fig 2.2.2. <a href="https://www.keyence.co.kr/download/download/confirmation/?dlAssetId=AS_135945&dlSeriesId=&dlModelId=&dlLangId=&dlLangType=en-GB" target="_blank">IP 配置工具</a>
      </td>
    </tr>
    <tr>
      <td style="border: none; padding-top: 10px; font-size: 0.9em; line-height: 1.6;">
        <ul style="margin: 0; padding-left: 20px; list-style-type: disc;">
          <li><code>网络适配器</code> : 连接计算机的网络适配器信息。</li>
          <li><code>IP 搜索范围</code> : 搜索连接设备的 IP 地址。</li>
          <li><code>IP 地址/Mac 地址</code> : 连接设备的 IP 地址和 MAC 地址</li>
          <li><code>IP 设置/重置</code> : IP 设置按钮 (编辑) 和重置按钮 (<u>仅用于更改 IP 设置</u>)</li>
        </ul>
      </td>
    </tr>
  </table>
</div>