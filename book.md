
[__SOURCE](0-about-this-manual/README.md)
# 关于手册
[__SOURCE](0-about-this-manual/precautions.md)
# 注意事项

{% include file="zh/precautions.md" %}
[__SOURCE](0-about-this-manual/safety-notice.md)
# 安全注意事项

{% include file="zh/safety-notice.md" %}
[__SOURCE](01_intro/README.md)
# 1 介绍

本手册涵盖了机器人掌握功能。  
本指南基于对机器人运行的基本理解。  
请点击以下 [link](https://hrbook-hrc.web.app/#/view/doc-hi6-operation/zh-tp630/README?cont_model=${cont_model}) 获取有关设置和使用 ${cont_model} 机器人控制器的详细信息。

- [1.1 关于机器人掌握](../01_intro/1-about_mastering/README.md)
    - 1.1.1 关于机器人掌握

<br>

- [1.2 基于传感器的机器人掌握](../01_intro/2-about_contact_based_mastering/README.md)
    - 1.2.1. 掌握设备
    - 1.2.2. 操作模式
    - 1.2.3. 操作概念
    - 1.2.4. 操作描述
[__SOURCE](01_intro/1-about_mastering/README.md)
## 1.1 关于机器人掌控

<div style="width: 630px; line-height: 1.5; word-break: keep-all;">
  <ul style="margin: 0; padding-left: 20px;">
    <li>掌控通过补偿每个轴的机械零位置来提高机器人的准确性。</li>
    <li>当第一次定义机械零或由于轴扭曲、组件更换或磨损而发生变化时，必须执行掌控。</li>
    <li><strong>掌控与校准</strong>
      <ul style="list-style-type: circle; padding-left: 20px;">
        <li>掌控：为坐标计算建立机械零参考。</li>
        <li>校准：基于已建立的零纠正位置错误。</li>
        <li>校准必须始终在掌控之后进行。</li>
      </ul>
    </li>
  </ul>

  <br>

  <div style="width: 630px; margin: 10px 0; background-color: #fcfcfc; padding: 5px 0;">
    本手册使用<strong>数字接触传感器</strong>进行掌控。传感器附加在每个轴上，通过在<strong>-1.5°到+1.5°</strong>的范围内移动来检测V形槽。检测到的V形槽位置随后会被修正到机械原点。
  </div>
</div>

<br>

<figure style="text-align: left; width: 100%; margin: 0;">
  <img src="../../_assets/12_mastering_concept_eng.PNG" style="width: 630px; margin-left: 25px;" alt="Mastering Concept">
  
  <figcaption style="font-size: 0.9em; margin-left: 0px; white-space: nowrap;">
    图 1.1. a. 起始点（轴扭曲状态），b. 在掌控期间的V形槽检测
  </figcaption>
</figure>
[__SOURCE](01_intro/2-about_contact_based_mastering/README.md)
## 1.2 基于接触传感器的机器人掌握
本用户手册包含有关`基于接触传感器`的机器人掌握功能的信息。  
通过使用此传感器，可以进行更准确的校正。

#### 1.2.1. 掌握设备
- **机器人** - 将连接掌握设备的地方
- **${cont_model} 机器人控制器** - 将安装掌握应用程序的地方
- **掌握套件** - 电源 + 传感器 + 通信模块

#### 1.2.2. 操作模式
- 机器人的操作模式必须设置为`手动模式`。
- 该过程只能在`电机开启状态`和`启用开关`打开的情况下进行。

#### 1.2.3. 操作概念
- 数字接触传感器扫描安装在机器人各轴上的掌握块的`V型槽`以定位更精确的原点。 ([Fig 1-1](../1-about_mastering/README.md))  
- 扫描完`V型槽`后，将相对于检测到的`V型槽`向量设置新的编码器偏移。  
- 然后计算`校正后编码器 (Corrected encoder)`值。  

#### 1.2.4. 总体过程  
1. 进入`工程师模式`    
2. 编码器偏移校正 - 通过直接教学  
3. 编码器偏移校正 - 通过使用插件  
    (1) 进入掌握插件。  
    (2) 在[待机模式](../../02_about_kit/3-com_initialization/README.md)中，输入关节编号 > `Shift + OK` > `确定 (OK)`  
    (3) 再次进入掌握插件。   
    (4) 点击`1.前往编码偏移`按钮。  
    (5) 将传感器安装在关节上。    
    (6) 确保传感器的末端靠近`V型槽`。  
    (7) 点击`2.开始掌握`按钮。  
    (8) 完成后点击`确定 (OK)`。  
    (9) 请移除传感器。  
    (10) 对于额外的轴，重复进行步骤(1)。
4. 在所有轴的掌握完成后，移动到更新的编码器原点。
5. 在掌握后检查编码器偏移是否已校正。  
[__SOURCE](02_about_kit/README.md)
# 2. 系统配置

- [2.1 精确定位工具包](../02_about_kit/1-kit_description/README.md)
  - 2.1.1 接触传感器组件
  - 2.1.2 接触传感器连接
  - 2.1.3 技术规格

<br>

- [2.2 初始设置和连接](../02_about_kit/2-kit_initialization/README.md)
  - 2.2.1 接触传感器初始化
  - 2.2.2 接触传感器的通信设置
  
<br>

- [2.3 精确定位应用程序配置](../02_about_kit/3-com_initialization/README.md)
  - 2.3.1 安装精确定位应用程序
  - 2.3.2 应用程序设置配置
[__SOURCE](02_about_kit/1-kit_description/README.md)
## 2.1 Mastering Kit

#### 2.1.1 Contact sensor components
- **Sensor & Power adapter** 
    <table style="margin-left: 0; border: none; border-collapse: collapse; width: 430px; table-layout: fixed;">
      <tr>
        <td style="width: 215px; border: none; vertical-align: bottom; padding: 0;">
          <img src="../../_assets/02_sensor.PNG" style="height: 180px;" alt="Contact sensor">
        </td>
        <td style="width: 215px; border: none; vertical-align: bottom; padding: 0;">
          <img src="../../_assets/03_communication_module.PNG" style="height: 180px;" alt="Communication module">
        </td>
      </tr>
      <tr style="white-space: nowrap; font-size: 0.9em;">
        <td style="border: none; padding-top: 5px;">
          Fig 2.1.1.&nbsp;&nbsp;a. 接触传感器
        </td>
        <td style="border: none; padding-top: 5px;">
          b. 通信模块
        </td>
      </tr>
    </table>

- **Cable**   
    <table style="margin-left: 0; border: none; border-collapse: collapse; width: 430px; table-layout: fixed;">
      <tr>
        <td style="width: 215px; border: none; vertical-align: bottom; padding: 0;">
          <img src="../../_assets/04_power_adapter.PNG" style="height: 180px;" alt="power adapter">
        </td>
        <td style="width: 215px; border: none; vertical-align: bottom; padding: 0;">
          <img src="../../_assets/05_lan_cable.PNG" style="height: 180;" alt="ethernet cable">
        </td>
      </tr>
      <tr style="white-space: nowrap; font-size: 0.9em;">
        <td style="border: none; padding-top: 5px;">
          Fig 2.1.2.&nbsp;&nbsp;a. 电源适配器
        </td>
        <td style="border: none; padding-top: 5px;">
          b. 以太网电缆
        </td>
      </tr>
    </table>

- **S/W**  
此包中包含一个掌握应用程序和一个控制器设置程序。

#### 2.1.2 Contact sensor connections
- 按照 Fig 2-1 b 中的照片连接传感器。

#### 2.1.3 Specifications
- 掌握工具包具有以下接口规格。
    <div style="width: fit-content;">

    |feature|detail|
    |:----|:----|
    |`传感器类型 (Sensor Type)`| `Digital contact` |
    |`协议 (Protocol)`| `Ethernet` (TCP/IP) |
    |`Cycle`| `5 msec` |

    </div>

<br>
<br>
[__SOURCE](02_about_kit/2-kit_initialization/README.md)
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
[__SOURCE](02_about_kit/3-com_initialization/README.md)
## 2.3 掌握应用程序配置

一旦成功完成掌握 APP 的安装，就可以执行掌握功能。 
只有在理解运动的条件和内容后，才能正确执行掌握。

#### 2.3.1 安装掌握应用程序
掌握功能是通过 ${cont_model} SDK 开发的，必须安装在控制器上。

- `安装位置` 对于 hi6 控制器  
    - /ata0:2/lib/hi6/apps/mastering (com version <= V60.32)
- `安装方法`  
    1) 您可以通过联系 HD Hyundai Robot SW 开发团队下载插件。  
    2) 在以太网连接后，使用 FTP 传输源代码。  
    3) 将源代码保存到 USB 后，连接到 TP。  
    4) 然后利用 TP 的 `5: 文件管理` 功能复制并粘贴源代码。
- `安装注意事项`
    1) 在安装后，要使用掌握 APP，控制器必须重启。  
    2) 如果在执行此操作后仍然在应用程序中未看到掌握 APP，请重启 TP。

#### 2.3.2 应用程序设置配置
- `应用程序位置`  
TP : `home` > `系统 (system)` > `4: 应用参数 (4: Application parameter)` > `23: 掌握`

<div style="width: 630px;">
  <p>- <code>待机模式</code></p>
  <table style="margin-left: 0; border: none; border-collapse: collapse; width: 530px; table-layout: fixed;">
    <tr>
      <td style="border: none; vertical-align: bottom; padding: 0;">
        <img src="../../_assets/10_mastering_app_eng.PNG" style="width: 100%; height: auto; display: block;" alt="Mastering app">
      </td>
    </tr>
    <tr>
      <td style="border: none; padding-top: 10px; font-size: 0.9em; font-weight: bold;">
        图 2.3.1. 掌握应用程序图像
      </td>
    </tr>
  </table>

  <div style="margin: 8px 0 2px 0;">- 如果看不到 APP，只需重启 TP。</div>

  <table style="margin-left: 0; border: none; border-collapse: collapse; width: 530px; table-layout: fixed;">
    <tr>
      <td style="border: none; vertical-align: bottom; padding: 0;">
        <img src="../../_assets/11_standbymode_eng.PNG" style="width: 100%; height: auto; display: block;" alt="Mastering standby mode">
      </td>
    </tr>
    <tr>
      <td style="border: none; padding-top: 10px; font-size: 0.9em; font-weight: bold;">
        图 2.3.2. 掌握 <code>待机模式</code> 图像
      </td>
    </tr>
    <tr>
      <td style="border: none; padding-top: 15px; font-size: 0.9em; line-height: 1.6;">
        <ul style="margin: 0; padding-left: 20px; list-style-type: disc;">
          <li><code>IP 地址</code> : 输入掌握通信器的 IP 地址。</li>
          <li><code>端口号</code> : 输入掌握通信器的端口号。</li>
          <li><code>关节号</code> : 输入目标关节的数量。</li>
          <li><code>掌握状态</code> : 显示掌握操作状态。</li>
          <li><code>编码器偏移量（之前 / 之后）</code> : 显示当前轴在掌握之前和之后的编码器偏移量值（<code>bit</code>）。</li>
        </ul>
      </td>
    </tr>
  </table>
</div>

如何保存掌握 IP 和端口号设置  
    1. 输入预设的 ip，端口。 - [2.2.2. 接触传感器的通信设置](../2-kit_initialization/README.md)  
    2. 通过 `shift` + `确定 (OK)` 保存配置到 ${cont_model} 控制器。
[__SOURCE](03_operation/README.md)
# 3. 掌握操作

- [3.1. 环境与过程](./1-mastering_step/README.md)
  - 3.1.1 环境
  - 3.1.2 操作过程 - 概要
  - 3.1.3 操作过程 - 详细
  - 3.1.4 结果 - 图像
  - 3.1.5 参考

<br>

- [3.2. 掌握的错误代码](./2-error/README.md)
  - 3.2.1 错误图像
  - 3.2.2 错误摘要
[__SOURCE](03_operation/1-mastering_step/README.md)
## 3.1. Environment & process

#### 3.1.1 Environment
{% hint style="warning" %}
**在开始精确操作之前，`精确传感器的尖端` 必须靠近 `V-槽`。  
违反此规定可能导致 `传感器尖端损坏` 或返回 `ERROR_VAL_THRESHOLD` 错误。**
{% endhint %}
- 仅在手动模式和电动机开启时操作。
- 请保持开启开关，直到操作结束。

<br>

#### 3.1.2 Operation process - summary
1. 进入 `engineer mode`    
2. 编码器偏移校正 - 通过直接教学  
3. 编码器偏移校正 - 通过使用插件  
    (1) 进入精确插件。  
    (2) 在 [standby mode](../../02_about_kit/3-com_initialization/README.md) 中，输入关节编号 > `Shift + OK` > `确定 (OK)`  
    (3) 重新进入精确插件。   
    (4) 点击 `1.Go to the enc offset` 按钮。  
    (5) 将传感器安装在关节上。    
    (6) 确保传感器的末端靠近 `V-槽`。  
    (7) 点击 `2.Start mastering` 按钮。  
    (8) 完成后点击 `确定 (OK)`。  
    (9) 请移走传感器。  
    (10) 如果还有其他轴需要校正，请从 (1) 再次开始。  
4. 所有轴的精确操作完成后，移动到更新的编码器原点。
5. 校正后检查编码器偏移是否正确。  

<br>

#### 3.1.3 Operation process - Details
1. 编码器偏移校正 - 通过直接教学  
    1-a) 控制机器人使其对准 V-槽/刻度条（通过 TP, Teaching Pendant）。  
    1-b) 在对准位置重置各个或所有关节的编码器偏移。  
    - 进入编码器偏移设置页面  
    &rightarrow; `TP` > 进入 `Engineer Mode` (R-Button + 314) > `系统 (System)` > `3: 机器人参数 (3: Robot parameter)` > `4: 编码器偏移 (4: Encoder offset)`  
    - 进行编码器偏移初始化  
        (1) 重置各个关节时：  
        → 点击相应关节的 `Corrrected encoder` 值 > 点击 `应用 (Reset one)` > `Shift + OK` > `确定 (OK)`   
        (2) 重置所有关节时：  
        → 点击 `重置全部 (Reset all)` > `Shift + OK` > `确定 (OK)`  

2. 编码器偏移校正 - 通过使用插件  
    (1) 在完成步骤 1 后，进入精确插件  
        &rightarrow; `TP` > `系统 (system)` > `4: 应用参数 (4: Application parameter)` > `Mastering`  
    (2) 在 `Joint Number` 中输入关节编号 > 点击 `Confirm`  
    (3) 重新进入精确插件以确保关节设置正确。  
    (4) 如果没问题，` (motor on)` > `enable switch on` > 点击 `Go to the enc offset`。    
        &rightarrow; 移动到之前设置的原点位置。  
    (5) 将传感器安装在步骤 (2) 中输入的关节上。  
        <div style="width: 630px;">
          <table style="margin-left: 0; border: none; border-collapse: collapse; width: 630px; table-layout: fixed;">
            <tr>
              <td style="width: 315px; border: none; vertical-align: bottom; padding: 0 5px 0 0;">
                <img src="../../_assets/00_mastering_Vdent_render.png" style="width: 100%; height: 200px; object-fit: cover; display: block;" alt="Render image">
              </td>
              <td style="width: 315px; border: none; vertical-align: bottom; padding: 0 0 0 5px;">
                <img src="../../_assets/01_mastering_real_picture.png" style="width: 100%; height: 200px; object-fit: cover; display: block;" alt="Real image">
              </td>
            </tr>
            <tr>
              <td colspan="2" style="border: none; padding-top: 8px; font-size: 0.9em; white-space: nowrap;">
                图 3.1.1. 精确传感器安装图（左：渲染图，右：真实图）
              </td>
            </tr>
          </table>
        </div>
    (6) 确保传感器尖端靠近 V 槽。  
        &rightarrow; 如果不在 V 槽内，请移走传感器并重复上述步骤 2。  
    (7) 2. 点击 `2. Start Mastering`。    
    (8) 当精确操作完成时，点击 `确定 (OK)`。  
    (9) 移走传感器。  
    (10) 如果有其他关节需要精确操作，请从 (1) 再次开始。  

3. 所有轴的精确操作完成后，移动到更新的编码器原点。
    - `TP` > `系统 (system)` > `3: 机器人参数 (3: Robot parameter)` > `4: 编码器偏移 (4: Encoder offset)` > `机器人移动 (Moving)` > `Shift + OK` > `确定 (OK)`  
    - `校正后编码器 (Corrected encoder)` 已被更新，因此即使机器人移动到原点，其值也不会改变。  

4. 校正后检查编码器偏移是否正确。  
    - `TP` > `系统 (system)` > `3: 机器人参数 (3: Robot parameter)` > `4: 编码器偏移 (4: Encoder offset)`  
    - 请检查通过精确操作更新的编码器偏移值是否与 `校正后编码器 (Corrected encoder)` 的值相同。  
    - 检查每个轴的 `当前编码器 (Current encoder)` 值是否为 `0x400000`。  

<br>

#### 3.1.4 Test Process - Status Bar Log

<div style="width:fit-content;">

|Order|Mastering status|Contents|
|:---:|:---:|:---|
|(1)|Standby|进入精确应用时的初始图像。|
|(2)|go to the offset pose...|按下 '`1.Go to the enc offset`' 按钮时的状态。|
|(3)|reached the offset pose.|完成 '`1.Go to the enc offset`' 操作后的消息。|
|(4)|Start mastering.|按下 '`2.Start mastering`' 按钮时的初始状态。|
|(5)|move to P1.|按下 '`2.Start mastering`' 按钮后向 p1 方向移动的状态。|
|(6)|move to P2.|按下 '`2.Start mastering`' 按钮后向 p2 方向移动的状态。|
|(7)|apply corrected enc offset.|精确操作完成后移动到修改后的原点的状态。|
|(8)|mastering end.|精确操作结束的状态。|

</div>

<br>

#### 3.1.5 Results - image

- 编码器偏移值以 `bit(hexa)` 为单位显示在 `Encoder Offset(Before/After)` 上。
  - `左块` : `Pre`-编码器偏移值 `在精确操作之前`。  
  - `右块` : `Post`-编码器偏移值 `在精确操作之后`。  
    <div style="width: 630px;">
      <table style="margin-left: 0; border: none; border-collapse: collapse; width: 500px; table-layout: fixed;">
        <tr>
          <td style="border: none; padding: 0;">
            <img src="../../_assets/13_standby_eng.png" style="width: 100%; height: auto; display: block;" alt="Standby mode">
          </td>
        </tr>
        <tr>
          <td style="border: none; padding: 8px 0 20px 0; font-size: 0.9em;">
            图 3.1.2. a. 待命模式图像
          </td>
        </tr>
        <tr>
          <td style="border: none; padding: 0;">
            <img src="../../_assets/14_mastering_end_eng.png" style="width: 100%; height: auto; display: block;" alt="Mastering complete">
          </td>
        </tr>
        <tr>
          <td style="border: none; padding: 8px 0 10px 0; font-size: 0.9em;">
            图 3.1.2. b. 精确操作完成图像
          </td>
        </tr>
      </table>
    </div>

#### 3.1.6 Reference
- 使用 `bit` 显示编码器偏移值的原因。
  - 在比较精确结果时，直观地显示角度差异，但变化小于 0.01 的情况无法评估。
  - 当前精确操作过程使原点偏移在 -1.5 到 1.5 度之间。
  - 为了传达这些细微差异，以 bit 单位显示编码器值更为准确。
[__SOURCE](03_operation/2-error/README.md)
## 3.2. 错误代码用于掌控

#### 3.2.1 错误图像
- 如果在掌控操作期间发生错误，会在“掌控进度状态”中输出错误代码。
- 例如) `ERROR_TCP_CONNECT`, `ERROR_MOTOR_ON_CHK`
    <div style="width: 630px;">
      <table style="margin-left: 0; border: none; border-collapse: collapse; width: 500px; table-layout: fixed;">
        <tr>
          <td style="border: none; padding: 0;">
            <img src="../../_assets/15_err_motor_on_eng.png" style="width: 100%; height: auto; display: block;" alt="错误：电机必须开启">
          </td>
        </tr>
        <tr>
          <td style="border: none; padding: 8px 0 25px 0; font-size: 0.9em; line-height: 1.4;">
            图 3.2.1. a. 错误：电机必须开启以进行掌控。
          </td>
        </tr>
        <tr>
          <td style="border: none; padding: 0;">
            <img src="../../_assets/16_err_tcp_connect_eng.png" style="width: 100%; height: auto; display: block;" alt="错误：TCP 连接">
          </td>
        </tr>
        <tr>
          <td style="border: none; padding: 8px 0 10px 0; font-size: 0.9em; line-height: 1.4;">
            图 3.2.1. b. 错误：与传感器的 TCP 连接失败。
          </td>
        </tr>
      </table>
    </div>

<br>

#### 3.2.2 错误摘要
这是在进行掌控操作时可能发生的错误列表。

<div style="width: fit-content;">

|错误代码|内容|待办事项|
|:---|:---|:---|
|`ERROR_MOTOR_ON_CHK`|尝试在电机关闭时进行掌控。|在电机开启时进行掌控。|
|`ERROR_MOTOR_OFF_CHK`|在进行掌控时检测到电机关闭。|在进行掌控时，请勿释放启用开关，直到功能结束。返回初始位置并重新执行掌控。|
|`ERROR_VAL_THRESHOLD`|在掌控过程中未检测到 `V-groove`。|未检测到 V-home。单击按钮 1 后，将传感器放置在 `V-groove` 附近并恢复掌控。|
|`ERROR_NO_SENSOR_VALS`|未记录传感器数据。|返回初始位置并重新执行掌控。如果问题重复发生，请检查插入的 APP 软件。|
|`ERROR_NO_ENC_VALS`|未记录编码器数据。|返回初始位置并重新执行掌控。如果问题重复发生，请检查插入的 APP 软件。|
|`ERROR_TCP_RES_FAIL`| TCP/IP 通信响应失败。 | 检查接触传感器的连接状态和设置环境。 |
|`ERROR_TCP_RES_NULL`| TCP/IP 通信响应为空。 | 检查接触传感器的连接状态和设置环境。 |
|`ERROR_TCP_CONNECT` | TCP/IP 通信连接失败。 | 检查接触传感器的连接状态和设置环境。 |
|`ERROR_PLAYBACK` | 播放错误。 | 请重启控制器。 |

</div>