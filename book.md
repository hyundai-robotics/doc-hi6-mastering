
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
请点击以下 [link](https://hrbook-hrc.web.app/#/view/doc-hi6-operation/en-tp630/README?cont_model=${cont_model}) 以获取有关设置和使用 ${cont_model} 机器人控制器的详细信息。

- [1.1 关于机器人掌握](../01_intro/1-about_mastering/README.md)
    - 1.1.1 关于机器人掌握

<br>

- [1.2 基于传感器的机器人掌握](../01_intro/2-about_contact_based_mastering/README.md)
    - 1.2.1. 掌握设备
    - 1.2.2. 操作模式
    - 1.2.3. 操作概念
    - 1.2.4. 操作描述
[__SOURCE](01_intro/1-about_mastering/README.md)
## 1.1 关于机器人校正

- 校正是通过补偿每个轴的机械零点（原点）位置来提高机器人运动精度的功能。
- 当首次定义机械零点时，必须执行校正。

- 在初始校正后，机械零点可能因 <br>
  轴扭曲、更换驱动组件或机械磨损等因素而改变。
- 在这种情况下，必须重新执行校正以恢复准确的运动控制。

- 校正与标定
    - 校正是建立机械零点的位置，作为坐标计算的参考过程。
    - 标定是在保持已建立的机械零点参考的同时，纠正位置误差的过程。
    - 在完成校正后，必须始终执行标定。

- 本手册使用数字接触传感器进行校正。<br>
  传感器连接到机器人的每个轴，检测V型槽 <br> 在起始点的基础上，从-1.5度移动到+1.5度。<br>
  检测到的V型槽位置被修正为机械原点。<br><div>

<img src="../../_assets/12_mastering_concept_eng.PNG" style="width: 630px"><br>
图1.1. a. 起始点（轴扭曲状态），
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
b. 在校正期间检测到的V型槽
</div>

[__SOURCE](01_intro/2-about_contact_based_mastering/README.md)
## 1.2 基于接触传感器的机器人标定  
本用户手册包含有关`基于接触传感器`的机器人标定功能的信息。  
通过使用该传感器，可以进行更准确的校正。  

<br>

#### 1.2.1. 标定设备  
- **机器人** <br>- 标定设备将连接的地方  
- **${cont_model} 机器人控制器** <br>- 将安装标定应用程序的地方  
- **标定套件** <br>- 电源 + 传感器 + 通信模块  

<br>

#### 1.2.2. 操作模式  
- 机器人操作模式必须设置为`手动模式`。  
- 该程序只能在`电机开启状态`和`启用开关`打开时进行。  

<br>

#### 1.2.3. 操作概念  
- 数字接触传感器扫描固定在机器人每个轴上的标定块的`V型槽`以找到更精确的原点。 ([图 1-1](../1-about_mastering/README.md))  
- 扫描`V型槽`后，将根据检测到的`V型槽`的向量设置新的编码器偏移。  
- 然后计算`已修正编码器 (Corrected encoder)`值。  

<br>

#### 1.2.4. 整体流程  
1. 输入`工程师模式`  
2. 编码器偏移校正 - 通过直接教学  
3. 编码器偏移校正 - 通过使用插件  
    (1) 进入标定插件。  
    (2) 在[待机模式](../../02_about_kit/3-com_initialization/README.md)下，输入关节编号 > `Shift + OK` > `确认 (OK)`  
    (3) 再次进入标定插件。  
    (4) 点击`1.前往编码偏移`按钮。  
    (5) 将传感器安装在关节上。  
    (6) 确保传感器的末端靠近`V型槽`。  
    (7) 点击`2.开始标定`按钮。  
    (8) 完成时点击`确认 (OK)`。  
    (9) 请移除传感器。  
    (10) 如果还有其他需要标定的轴，请从（1）开始再次进行。  
4. 所有轴的标定完成后，移动到更新的编码器原点。  
5. 检查标定后编码器偏移是否已校正。  
[__SOURCE](02_about_kit/README.md)
# 2. 系统配置

- [2.1 启动套件](../02_about_kit/1-kit_description/README.md)
  - 2.1.1 接触传感器组件
  - 2.1.2 接触传感器连接
  - 2.1.3 技术规格

<br>

- [2.2 初始设置和连接](../02_about_kit/2-kit_initialization/README.md)
  - 2.2.1 接触传感器初始化
  - 2.2.2 接触传感器的通信设置
  
<br>

- [2.3 启动应用程序配置](../02_about_kit/3-com_initialization/README.md)
  - 2.3.1 安装启动应用程序
  - 2.3.2 应用程序设置配置
[__SOURCE](02_about_kit/1-kit_description/README.md)
## 2.1 主控工具包

#### 2.1.1 接触传感器组件
- **传感器和电源适配器** 
    <div style="width: 630px;">
      <table style="margin-left: 0; border: none; border-collapse: collapse; width: 630px; table-layout: fixed;">
        <tr>
          <td style="width: 315px; border: none; vertical-align: bottom; padding: 0 0;">
            <img src="../../_assets/02_sensor.PNG" style="width: 100%; height: 200px; object-fit: contain; display: block;" alt="Contact sensor">
          </td>
          <td style="width: 315px; border: none; vertical-align: bottom; padding: 0 0;">
            <img src="../../_assets/03_communication_module.PNG" style="width: 100%; height: 200px; object-fit: contain; display: block;" alt="Communication module">
          </td>
        </tr>
        <tr style="font-size: 0.9em; white-space: nowrap;">
          <td style="border: none; padding-top: 8px;">
            图 2.1.1. a. 接触传感器
          </td>
          <td style="border: none; padding-top: 8px; padding-left: 5px;">
            b. 通信模块
          </td>
        </tr>
      </table>
    </div>
<br>

- **电缆**   
    <div style="width: 630px;">
      <table style="margin-left: 0; border: none; border-collapse: collapse; width: 630px; table-layout: fixed;">
        <tr>
          <td style="width: 315px; border: none; vertical-align: bottom; padding: 0 0;">
            <img src="../../_assets/04_power_adapter.PNG" style="width: 100%; height: 200px; object-fit: contain; display: block;" alt="Power adapter">
          </td>
          <td style="width: 315px; border: none; vertical-align: bottom; padding: 0 0;">
            <img src="../../_assets/05_lan_cable.PNG" style="width: 100%; height: 200px; object-fit: contain; display: block;" alt="Ethernet cable">
          </td>
        </tr>
        <tr style="font-size: 0.9em; white-space: nowrap;">
          <td style="border: none; padding-top: 8px;">
            图 2.1.2.   a. 电源适配器
          </td>
          <td style="border: none; padding-top: 8px; padding-left: 5px;">
            b. 以太网电缆
          </td>
        </tr>
      </table>
    </div>

<br>

- **软件**  
此包包括一个主控应用程序和一个控制器设置程序。

<br>

#### 2.1.2 接触传感器连接
- 按照图 2-1 b 中的照片连接传感器。

<br>

#### 2.1.3 规格
- 主控工具包的接口规格如下。
    <div style="width:fit-content;">

    |特征|细节|
    |:----|:----|
    |`传感器类型 (Sensor Type)`| `Digital contact` |
    |`协议 (Protocol)`| `Ethernet` (TCP/IP) |
    |`周期 (Cycle)`| `5 msec` |

    </div>

<br>
<br>

[__SOURCE](02_about_kit/2-kit_initialization/README.md)
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

[__SOURCE](02_about_kit/3-com_initialization/README.md)
## 2.3 主控应用程序配置

一旦主控应用程序安装成功完成，就可以执行主控功能。  
完成多个主控配置设置后，可以通过几个按钮轻松执行主控操作。  
仅当理解运动的条件和内容时，才能正确执行主控。

<br>

#### 2.3.1 安装主控应用程序
主控功能是通过 ${cont_model} SDK 开发的，必须在 ${cont_model} 控制器上安装此应用程序才能使用。

- `安装位置` 对于 ${cont_model} 控制器  
    - /ata0:2/lib/hi6/apps/mastering
- `安装方法`  
    1) 您可以通过联系 HD 现代机器人软件开发团队下载插件。  
    2) 在以太网连接后，使用 FTP 传输源代码。  
    3) 将源代码保存到 USB 后，连接到 TP。  
    4) 然后通过 TP 的 `5: 文件管理` 功能复制并粘贴源代码。
- `安装注意事项`
    1) 安装后要使用主控应用程序，控制器必须重新启动。  
    2) 如果在这样做后仍然看不到主控应用程序，请重新启动 TP。

<br>

#### 2.3.2 应用程序设置配置
- `应用位置`  
TP : `home` > `系统 (system)` > `4: 应用参数 (4: Application parameter)` > `23: 主控 (Mastering)`

<br>

- `待机模式`
    <div style="width: 630px;">
      <table style="margin-left: 0; border: none; border-collapse: collapse; width: 630px; table-layout: fixed;">
        <tr>
          <td style="border: none; vertical-align: bottom; padding: 0;">
            <img src="../../_assets/10_mastering_app_eng.PNG" style="width: 100%; height: auto; display: block;" alt="Mastering app">
          </td>
        </tr>
        <tr>
          <td style="border: none; padding-top: 10px; font-size: 0.9em; font-weight: bold;">
            图 2.3.1. 主控应用程序图像
          </td>
        </tr>
      </table>
    </div>

- 如果在应用程序中看不到主控应用程序，请重新启动 TP。
    <div style="width: 630px;">
      <table style="margin-left: 0; border: none; border-collapse: collapse; width: 630px; table-layout: fixed;">
        <tr>
          <td style="border: none; padding: 0;">
            <img src="../../_assets/11_standbymode_eng.PNG" style="width: 100%; height: auto; display: block;" alt="Mastering standby mode">
          </td>
        </tr>
        <tr>
          <td style="border: none; padding-top: 10px; font-size: 0.9em; font-weight: bold;">
            图 2.3.2. 主控 <code>待机模式</code> 图像
          </td>
        </tr>
        <tr>
          <td style="border: none; padding-top: 15px; font-size: 0.9em; line-height: 1.6; word-break: keep-all;">
            <ul style="margin: 0; padding-left: 20px; list-style-type: disc;">
              <li><code>IP地址 (IP Address)</code> : 输入主控通信器的 IP 地址。</li>
              <li><code>端口号 (Port Number)</code> : 输入主控通信器的端口号。</li>
              <li><code>关节编号 (Joint Number)</code> : 输入目标关节的编号。</li>
              <li><code>主控状态 (Mastering Status)</code> : 显示主控操作状态。</li>
              <li><code>编码器偏移 (之前 / 之后) (Encoder Offset (Before / After))</code> : 显示当前轴的编码器偏移值 (<code>bit</code>) 在主控之前和之后。</li>
            </ul>
          </td>
        </tr>
      </table>
    </div>

<br>

- 如何保存主控 IP 和端口设置  
    1) 输入预设的 IP 和端口。 -
    [2.2.2. 接触传感器的通信设置](../2-kit_initialization/README.md)  
    2) 通过 `shift` + `确认 (OK)` 将配置保存到 ${cont_model} 控制器。

[__SOURCE](03_operation/README.md)
# 3. 操作掌握

- [3.1. 环境与过程](./1-mastering_step/README.md)
  - 3.1.1 环境
  - 3.1.2 操作过程 - 概述
  - 3.1.3 操作过程 - 详情
  - 3.1.4 结果 - 图像
  - 3.1.5 参考

<br>

- [3.2. 操作掌握的错误代码](./2-error/README.md)
  - 3.2.1 错误图像
  - 3.2.2 错误概要
[__SOURCE](03_operation/1-mastering_step/README.md)
## 3.1. 环境与过程

#### 3.1.1 环境
{% hint style="warning" %}
**在开始掌握之前，`掌握传感器的尖端`必须靠近`V型槽`。  
违背此规定可能会导致`传感器尖端损坏`或返回`ERROR_VAL_THRESHOLD`错误。**
{% endhint %}
- 仅在手动模式下操作，并且电机开启。
- 请在操作结束之前保持使能开关。

<br>

#### 3.1.2 操作过程 - 概述
1. 进入`工程师模式`    
2. 编码器偏移校正 - 通过直接教学  
3. 编码器偏移校正 - 通过使用插件  
    (1) 进入掌握插件。  
    (2) 在[待机模式](../../02_about_kit/3-com_initialization/README.md)中，输入关节编号 > `Shift + OK` > `确认 (OK)`  
    (3) 重新进入掌握插件。   
    (4) 点击`1.进入编码器偏移`按钮。  
    (5) 将传感器安装在关节上。    
    (6) 确保传感器的末端靠近`V型槽`。  
    (7) 点击`2.开始掌握`按钮。  
    (8) 完成时点击`确认 (OK)`。  
    (9) 请移除传感器。  
    (10) 如果还有需要掌握的额外轴，请从(1)重新开始。  
4. 在所有轴的掌握完成后，移动到更新的编码器原点。
5. 检查在掌握后编码器偏移是否已校正。  
    
<br>

#### 3.1.3 操作过程 - 详细信息
1. 编码器偏移校正 - 通过直接教学  
    1-a) 使用教学挂件（TP）挪动机器人对齐附在机器人上的V型槽或刻度条。  
    1-b) 将编码器偏移重置为可视对齐位置，适用于单个或所有关节。  
    - 进入编码器偏移设置页面  
    &rightarrow; `TP` > 进入`工程师模式`（R-按钮 + 314） > `系统 (System)` > `3: 机器人参数 (3: Robot parameter)` > `4: 编码器偏移 (4: Encoder offset)`  
    - 进行编码器偏移初始化  
        (1) 重置单个关节时：  
        → 点击相应关节的`校正编码器`值 > 点击`重置一个 (Reset one)` > `Shift + OK` > `确认 (OK)`   
        (2) 重置所有关节时：  
        → 点击`重置所有 (Reset all)` > `Shift + OK` > `确认 (OK)`  

<br>

<br>

<br>

2. 编码器偏移校正 - 通过使用插件  
    <div style="width: 630px; margin-left: 0; padding-left: 0; line-height: 1.6; word-break: keep-all;">
      (1) 在完成步骤1后，进入掌握插件  
      &nbsp;&nbsp;&nbsp;&nbsp;&rightarrow; <code>TP</code> > <code>系统 (system)</code> > <code>4: 应用参数</code> > <code>掌握</code>  <br>
      (2) 在 <code>Joint Number</code> 中输入关节编号 > 点击 <code>确认 (Confirm)</code>  <br>
      (3) 重新输入主控插件以确保关节设置正确。  <br>
      (4) 如果没问题，<code>电机 开 (motor on)</code> > <code>enable switch on</code> > 点击 <code>Go to the enc offset</code>。  <br>
      &nbsp;&nbsp;&nbsp;&nbsp;&rightarrow; 移动到之前设定的原点位置。  <br>
      (5) 在 (2) 中输入的关节上安装传感器。  

      <div style="margin: 10px 0;">
        <table style="border: none; border-collapse: collapse; width: 630px; table-layout: fixed;">
          <tr>
            <td style="width: 315px; border: none; vertical-align: bottom; padding: 0 5px 0 0;">
              <img src="../../_assets/00_mastering_Vdent_render.png" style="width: 100%; height: 200px; object-fit: cover; display: block;">
            </td>
            <td style="width: 315px; border: none; vertical-align: bottom; padding: 0 0 0 5px;">
              <img src="../../_assets/01_mastering_real_picture.png" style="width: 100%; height: 200px; object-fit: cover; display: block;">
            </td>
          </tr>
          <tr>
            <td colspan="2" style="border: none; padding-top: 8px; font-size: 0.9em;">
              <strong>图 3.1.1.</strong> 主控传感器安装图像（左：渲染图，右：实物图）
            </td>
          </tr>
        </table>
      </div>

      (6) 确保传感器尖端靠近 V 槽。  <br>
      &nbsp;&nbsp;&nbsp;&nbsp;&rightarrow; 如果不在 V 槽内，请移除传感器并重复上述步骤 2。  <br>
      (7) 点击 <code>2. 开始主控 (2. Start Mastering)</code>。  <br>
      (8) 主控完成后，点击 <code>确认 (OK)</code>。  <br>
      (9) 移除传感器。  <br>
      (10) 若有其他关节需主控，请从 (1) 重复进行。
    </div>

<br>

3. 在所有轴的主控完成后，移动到更新的编码器原点。  
- `TP` > `系统 (system)` > `3: 机器人参数 (3: Robot parameter)` > `4: 编码器偏移 (4: Encoder offset)` > `移动中 (Moving)` > `Shift + OK` > `确认 (OK)`  
- `已修正编码器 (Corrected encoder)` 已经更新，因此即使机器人移动到原点，其值也不会改变。  

<br>

4. 主控后检查编码器偏移是否已修正。  
- `TP` > `系统 (system)` > `3: 机器人参数 (3: Robot parameter)` > `4: 编码器偏移 (4: Encoder offset)`  
- 请检查通过主控更新的编码器偏移值是否与 `已修正编码器 (Corrected encoder)` 值相同。  
- 检查每个轴的 `当前编码器 (Current encoder)` 值是否为 `0x400000`。  

<br>
<br>

#### 3.1.4 测试过程 - 状态条日志

<div style="width:fit-content;">

|顺序|主控状态|内容|
|:---:|:---:|:---|
|(1)|待命|进入主控应用时的初始图像。|
|(2)|转到偏移位姿...|按下 '`1.Go to the enc offset`' 按钮时的状态。|
|(3)|已达到偏移位姿。|完成消息，表示 '`1.Go to the enc offset`' 操作后。|
|(4)|开始主控。|按下 '`2.Start mastering`' 按钮时的第一个状态。|
|(5)|移动到 P1。|按下 '`2.Start mastering`' 按钮后，向 p1 方向移动的状态。|
|(6)|移动到 P2。|按下 '`2.Start mastering`' 按钮后，向 p2 方向移动的状态。|
|(7)|应用修正的编码器偏移。|主控完成后，移动到修正原点的状态。|
|(8)|主控结束。|主控完成的状态。|

</div>

<br>
<br>

#### 3.1.5 结果 - 图像
- 编码器偏移值以 `bit(hexa)` 为单位在 `Encoder Offset(Before/After)` 上显示。
  - `左块` : `前`-编码器偏移值 `在掌握之前`。
  - `右块` : `后`-编码器偏移值 `在掌握之后`。
    <div style="width: 630px;">
      <table style="margin-left: 0; border: none; border-collapse: collapse; width: 500px; table-layout: fixed;">
        <tr>
          <td style="border: none; padding: 0;">
            <img src="../../_assets/13_standby_eng.png" style="width: 100%; height: auto; display: block;" alt="Standby mode">
          </td>
        </tr>
        <tr>
          <td style="border: none; padding: 8px 0 20px 0; font-size: 0.9em; line-height: 1.4;">
            <strong>图 3.1.2. a.</strong> 待机模式图像 (Standby mode image)
          </td>
        </tr>
        <tr>
          <td style="border: none; padding: 0;">
            <img src="../../_assets/14_mastering_end_eng.png" style="width: 100%; height: auto; display: block;" alt="Mastering complete">
          </td>
        </tr>
        <tr>
          <td style="border: none; padding: 8px 0 10px 0; font-size: 0.9em; line-height: 1.4;">
            <strong>图 3.1.2. b.</strong> 完成掌握图像 (Mastering complete image)
          </td>
        </tr>
      </table>
    </div>

<br>

#### 3.1.6 参考
- 使用 `bit` 显示编码器偏移值的原因。
  - 在比较掌握结果时显示角度差异是直观的，但小于 0.01 的变化无法评估。
  - 当前掌握过程将原点移动在 -1.5 到 1.5 度之间。
  - 为了传达这些微小的差异，以 bit 单位显示编码器值更加准确。

[__SOURCE](03_operation/2-error/README.md)
## 3.2. 错误代码说明

#### 3.2.1 错误图像
- 在掌控操作过程中，如果发生错误，'掌控进度状态'将输出错误代码。
- 例如) `ERROR_TCP_CONNECT`， `ERROR_MOTOR_ON_CHK`
    <div style="width: 630px;">
      <table style="margin-left: 0; border: none; border-collapse: collapse; width: 500px; table-layout: fixed;">
        <tr>
          <td style="border: none; padding: 0;">
            <img src="../../_assets/15_err_motor_on_eng.png" style="width: 100%; height: auto; display: block;" alt="Error: Motor ON">
          </td>
        </tr>
        <tr>
          <td style="border: none; padding: 8px 0 25px 0; font-size: 0.9em; line-height: 1.4;">
            <strong>图 3.2.1. a.</strong> 错误状态示例：主控时电机必须保持开启 (Motor ON)
          </td>
        </tr>
        <tr>
          <td style="border: none; padding: 0;">
            <img src="../../_assets/16_err_tcp_connect_eng.png" style="width: 100%; height: auto; display: block;" alt="Error: TCP Connection">
          </td>
        </tr>
        <tr>
          <td style="border: none; padding: 8px 0 10px 0; font-size: 0.9em; line-height: 1.4;">
            <strong>图 3.2.1. b.</strong> 错误状态示例：传感器 TCP 连接失败
          </td>
        </tr>
      </table>
    </div>

<br>

#### 3.2.2 错误总结
这是在执行掌控操作时可能出现的错误列表。  

<div style="width:fit-content;">

|错误代码|内容|待办事项|
|:---|:---|:---|
|`ERROR_MOTOR_ON_CHK`|尝试在马达关闭的情况下进行掌控。|在马达开启的情况下执行掌控。|
|`ERROR_MOTOR_OFF_CHK`|在执行掌控时检测到马达关闭。|在执行掌控时，直到功能结束，请不要释放使能开关。返回初始位置并重新执行掌控。|
|`ERROR_VAL_THRESHOLD`|在掌控过程中未检测到`V-groove`。|未检测到V-home。点击按钮1后，将传感器放置在`V-groove`附近并恢复掌控。|
|`ERROR_NO_SENSOR_VALS`|没有记录传感器数据。|返回初始位置并重新执行掌控。如果重复出现问题，请检查插件应用软件。|
|`ERROR_NO_ENC_VALS`|没有记录编码器数据。|返回初始位置并重新执行掌控。如果重复出现问题，请检查插件应用软件。|
|`ERROR_TCP_RES_FAIL`| TCP/IP通信响应失败。 | 检查接触传感器的连接状态和设置环境。 |
|`ERROR_TCP_RES_NULL`| TCP/IP通信响应为null。 | 检查接触传感器的连接状态和设置环境。 |
|`ERROR_TCP_CONNECT` | TCP/IP通信连接失败。 | 检查接触传感器的连接状态和设置环境。 |
|`ERROR_PLAYBACK` | 播放错误。 | 请重启控制器。 |

</div>
