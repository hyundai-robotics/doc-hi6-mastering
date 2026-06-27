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