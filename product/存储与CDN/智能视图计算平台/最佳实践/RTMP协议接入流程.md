本文将介绍设备如何通过 GB28181协议接入智能视图计算平台，以 IPC 配置为例。

## 接入配置流程

### 1. 创建设备

1. 登录 [智能视图计算平台控制台](https://console.cloud.tencent.com/iss)。
2. 在左侧导航栏中，选择**设备接入**功能。
3. 先左侧自定义**设备组织**。
4. 随后选择对应的设备组织，单击**添加设备**（可选择**手动添加**或**批量导入**，下文以手动添加为例讲解操作）。
   ![](https://qcloudimg.tencent-cloud.cn/raw/43c9abe13d9d8024066d63cc44de4850.png)
5. 完善弹窗中信息并单击**确定**，完成设备创建。
   ![](https://qcloudimg.tencent-cloud.cn/raw/95420848825a642e7abf2c1529a7941a.png)
6. 设备创建成功后初始状态为**未注册**。                                                        
   ![](https://qcloudimg.tencent-cloud.cn/raw/1f863369a066be59fd554bf705cf116b.png)

### 2. 获取设备国标配置信息

单击设备名称进入**设备详情**页面，查看并记录我们为设备生成的配置信息（ 如下图红框处）。
![](https://qcloudimg.tencent-cloud.cn/raw/ebb35c343d702ca4d5c2de2bf83e942e.png)

>?可使用**导出设备信息**功能,批量导出设备配置信息。

![](https://qcloudimg.tencent-cloud.cn/raw/b7acb3c0aec9dd916e3d5fb2fa9f5f6a.png)

### 3. 登陆设备 Web 端进行配置

1. 海康威视设备配置示范（以 IPC 为例，NVR 配置过程类似，不再赘述）
![](https://qcloudimg.tencent-cloud.cn/raw/0cddbabf537b42d9c1f007dea6cb096d.png)

<table>
	<tr><th>配置参数</th><th>配置说明</th></tr>
	<tr><td>传输协议</td><td>此处指信令的传输协议，建议选择 <b>UDP</b>。</td></tr>
	<tr><td>协议版本</td><td>选择  <b> GB/T28181-2016</b>。</td></tr>
	<tr><td>SIP 服务器 ID</td><td>填写步骤2平台生成的 SIP 服务器ID。</td></tr>
	<tr><td>SIP 服务器域</td><td>填写步骤2平台生成的 SIP 服务器域（为 SIP 服务器ID的前10位）。</td></tr>
	<tr><td>SIP 服务器地址</td><td>填写步骤2平台生成的 SIP 服务器IP。</td></tr>
	<tr><td>SIP 服务器端口</td><td>填写步骤2平台生成的 SIP 服务器端口号。</td></tr>
	<tr><td>SIP 用户名与 SIP 用户认证 ID</td><td>填写步骤2平台生成的设备 ID。</td></tr>
	<tr><td>密码&密码确认</td><td>填写步骤2中的设备密码（即创建设备时输入的密码）。</td></tr>
	<tr><td>注册有效期</td><td>设备注册到平台的有效期限。建议采用默认值3600s。</td></tr>
	<tr><td>心跳周期</td><td>设备发送心跳信息的时间间隔。建议采用默认值60s。</td></tr>
  <tr><td>最大超时次数</td><td>心跳连续超时达到“最大超时次数”，则认为设备无法与平台建立连接。建议采用默认值3次。</td></tr>
	<tr><td>视频通道编码 ID</td><td>可自行设置20位编码，不重复即可，11-13位可填132。（NVR 设备配置此处时类似）。</td></tr>
  <tr><td><strong>本地 SIP 服务器端口</strong></td><td><strong>部分海康设备若有此项配置（一般设备默认的本地 SIP 端口号为5060,可能会被局域网屏蔽），建议修改为5061、5062等其他端口号。</strong></td></tr>
</table>


2. 大华设备配置示范（以 IPC 为例，NVR 配置过程类似，不再赘述）
![](https://qcloudimg.tencent-cloud.cn/raw/2966287e228fb177f9e872fd784778f7.png)

<table>
	<tr><th>配置参数</th><th>配置说明</th></tr>
	<tr><td>SIP 服务器编号</td><td>填写步骤2平台生成的 SIP 服务器 ID。</td></tr>
	<tr><td>SIP 服务器域</td><td>填写步骤2平台生成的 SIP 服务器域（为 SIP 服务器 ID 的前10位）。</td></tr>
	<tr><td>SIP 服务器 IP</td><td>填写步骤2平台生成的 SIP 服务器IP。</td></tr>
	<tr><td>SIP 服务器端口</td><td>填写步骤2平台生成的 SIP 服务器端口号。</td></tr>
	<tr><td>设备编号</td><td>填写步骤2平台生成的设备 ID。</td></tr>
	<tr><td>注册密码</td><td>填写步骤2中的设备密码（即创建设备时输入的密码）。</td></tr>
  <tr><td>本地 SIP 服务器端口</td><td>一般设备默认的本地 SIP 端口号为5060,可能会被局域网屏蔽，建议修改为5061、5062等其他端口号。</td></tr>
	<tr><td>注册有效期</td><td>设备注册到平台的有效期限。建议采用默认值3600s。</td></tr>
	<tr><td>心跳周期</td><td>设备发送心跳信息的时间间隔。建议采用默认值60s。</td></tr>
  <tr><td>最大超时次数</td><td>心跳连续超时达到“最大超时次数”，则认为设备无法与平台建立连接。建议采用默认值3次。</td></tr>
	<tr><td>通道编号</td><td>可自行设置20位编码，不重复即可，11-13位可填132。（NVR 设备配置此处时类似）</td></tr>
</table>


### 4. 完成配置

完成上述配置流程后，切换至 [智能视图计算平台控制台](https://console.cloud.tencent.com/iss)，刷新**设备接入**页面。此时设备状态显示为”在线“，表示设备成功注册且已上线。
![](https://qcloudimg.tencent-cloud.cn/raw/bc255daa383ea4bc0a12f76dec5b2092.png)

## 音视频配置注意事项

同一个网络，往往由于网络资源不足/波动大导致出现视频卡顿或实况失败的现象，建议按照如下配置视音频参数。

>!
- 不要开启厂商的任何私有编码,以及 smart264、smart265、SVC 等，否则无法成功注册！
- 某些厂商设备，在 NVR 配置页面修改其下摄像头的配置极有可能不生效，强烈建议登陆到 IPC 设备端配置！

### 1. IPC 音视频配置规范

下图以海康威视 IPC 为例，其他厂商设备类似。
![](https://qcloudimg.tencent-cloud.cn/raw/d410d87c38a50854c9ef3a6ef35f4a6b.png)
![](https://qcloudimg.tencent-cloud.cn/raw/86f4b6195605324b53b7e7b72558a6ed.png)

### 2. NVR 视音频配置规范

下图以海康威视 NVR 为例，其他厂商设备类似。
![](https://qcloudimg.tencent-cloud.cn/raw/8407c8e0b7a69c6f9da844b19b22e0ff.png)

