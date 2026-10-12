# Cloudflare 优选 IP 订阅器 · 网页测速助手

在网页输入自己的 VLESS + WebSocket + TLS 节点，点击按钮，由本机内置 CFST 测量连接延迟和下载速度，再用 Xray 复测完整连接。成功后自动回填 15 个优选 IP，前 10 条均通过复测；核对发布后，客户端更新同一订阅地址即可使用新结果。

## 下载

- [下载 Windows x64 便携包](https://github.com/naxianjin/portable-toolbox/releases/download/cfsub-v1.1.0/Cloudflare-IP-Subscription-Windows-x64.zip)
- [本版发布页与 SHA-256 校验文件](https://github.com/naxianjin/portable-toolbox/releases/tag/cfsub-v1.1.0)
- [PDF 使用指南](使用指南.pdf)
- [在线订阅器](https://cloudflaresub.naxianjin8.workers.dev/)

支持 Windows 10 / 11 64 位，推荐当前版本的 Edge 或 Chrome。包内已有 Node、CFST、官方 IP 列表、Xray 以及必要依赖；不需要安装开发环境、管理员权限或 Cloudflare 账号。

## 第一次使用

1. **完整解压**程序包到可写文件夹，保留“程序”目录；不要直接在压缩软件中运行入口。
2. 双击 **打开订阅器.cmd**。网页自动绑定本机空间，后台助手自动启动。
3. 在网页 **原始节点** 中粘贴自己能连接的 `vless://` 分享链接，点击 **一键测速并填入**。浏览器首次请求访问本地网络时，允许该请求。
4. 等待网页显示测速与完整连接复测进度。成功后自动填入 15 个入口，通过者按下载速度优先排列，前 10 条供订阅使用。
5. 点击 **预览并更新订阅**，核对并确认发布。到 **订阅结果** 复制对应客户端的地址或扫码导入。

无需打开测速窗口、复制 IP 或手动导入 CSV。测速只回填草稿，确认发布后才更新 Cloudflare KV。刷新网页或助手空闲退出后提示未连接时，再次双击“打开订阅器.cmd”即可。

## 测速规则

- 默认选择无探测丢包、连接延迟不超过 200 ms、下载速度至少 0.1 MB/s 的 15 个 IP。
- Xray 对每个入口发起 3 次完整 HTTPS 请求，至少 10 个入口全部请求通过后才回填。
- 发布时优先选用完整复测全部通过的入口，同组按 CFST 下载速度降序排列。
- CFST 最长运行 20 分钟，之后还有完整节点复测。可以取消；失败、取消或数量不足时保留已有入口和订阅。
- CFST 连接延迟、CFST 下载速度和完整 HTTPS 请求耗时是不同指标。实际代理下载速度可在客户端另测。

测速前确认 TUN 或路由器代理没有接管 CFST 流量，否则结果可能反映代理线路。工具使用当前电脑的网络，测速与同步需要联网。

## 节点与设备数据

程序包不提供 VPS 或原始节点，也不包含作者的真实节点。每台电脑建立自己的设备空间；节点、IP、模板、历史和订阅地址分别保存。

网页测速不将原始节点写入本机“我的节点.txt”。确认发布后，节点模板和订阅内容保存到当前设备的 Cloudflare KV 空间。本机长期身份由 Windows DPAPI 加密保存，网页不需要手动填写密钥。

订阅链接本身带有读取权限。继续分享工具时，发送这里下载的干净 ZIP；已经使用过的目录含有设备身份和运行结果，不要重新压缩公开上传。

## 其他入口与常见问题

| 入口 | 用途 |
| --- | --- |
| 打开订阅器.cmd | 推荐入口：自动绑定设备、启动助手并进入网页 |
| 填写原始节点.cmd | 为原命令行流程保存本机节点文件 |
| 开始测速.cmd | 原命令行自动测速、复测和上传流程 |
| 复测节点.cmd | 仅生成完整链路复测报告 |

**网页提示助手未连接**：通过本版“打开订阅器.cmd”进入，允许浏览器访问本地网络；刷新后断开时重新运行该入口。只访问线上网址仍可读取订阅和手动导入 CSV，无法直接运行电脑上的程序。

**找不到 Node 或 Xray**：检查是否完整解压，入口和整个“程序”目录应保留在一起。

**测速不够 15 个或复测通过不足 10 个**：检查原始节点是否可用、网络状态及 CFST 是否被其他代理接管，再重新测速。

**客户端连接**：v2rayN / v2rayNG 使用 Raw；支持 VLESS 的 Clash / Mihomo 使用 Clash 格式；Shadowrocket 使用对应入口。实际使用节点仍需要自己的代理客户端。纯 VLESS 不提供 Surge 导出。

## 来源与许可

[CloudflareSpeedTest](https://github.com/XIU2/CloudflareSpeedTest)、[Xray-core](https://github.com/XTLS/Xray-core)、[Node.js](https://nodejs.org/) 和 Undici 的版本、许可与对应源码资料在包内“程序/许可与源码”中。订阅器基于 [cloudflaresub](https://github.com/InfiCheesy/cloudflaresub) 集成。

[返回网络工具](../README.md) · [返回工具箱](../../README.md)
