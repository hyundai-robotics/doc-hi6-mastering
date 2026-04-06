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
