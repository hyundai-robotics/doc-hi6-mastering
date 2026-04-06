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
