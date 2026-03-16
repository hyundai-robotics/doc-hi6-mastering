## 3.2. 错误代码说明

#### 3.2.1 错误图像
- 在掌控操作过程中，如果发生错误，'掌控进度状态'将输出错误代码。
- 例如) `ERROR_TCP_CONNECT`， `ERROR_MOTOR_ON_CHK`

    <div>
    <img src="../../_assets/15_err_motor_on_eng.png" style="max-height: 30vh; max-width: 40vw">
    <img src="../../_assets/16_err_tcp_connect_eng.png" style="max-height: 30vh; max-width: 40vw"><br>
    图 3.2.1. 错误状态的示例图像 
    </div>

<br>
<br>

#### 3.2.2 错误总结
这是在执行掌控操作时可能出现的错误列表。  

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