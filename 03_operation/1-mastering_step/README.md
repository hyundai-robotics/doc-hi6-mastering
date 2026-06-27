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