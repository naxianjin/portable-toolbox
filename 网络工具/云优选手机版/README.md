# 云优选手机版 · Android 测试版

当前版本 **0.1.19-test / versionCode 20**，适用于 **Android 8 及以上 / ARM64**。手机本地优选 Cloudflare IP，再按场景预览和发布订阅。

[下载页面](https://github.com/naxianjin/portable-toolbox/releases/tag/yunyouxuan-android-v0.1.19-test) · [直接下载 APK](https://github.com/naxianjin/portable-toolbox/releases/download/yunyouxuan-android-v0.1.19-test/YunYouXuan-Android-arm64-v0.1.19-test.apk) · [SHA256](https://github.com/naxianjin/portable-toolbox/releases/download/yunyouxuan-android-v0.1.19-test/YunYouXuan-Android-arm64-v0.1.19-test.apk.sha256) · [在线订阅器](https://cloudflaresub.naxianjin8.workers.dev/)

## 更新内容

- 0.1.19 订阅页优先展示当前测速场景，过期或时间异常的结果提示重新测速并禁用发布，保留旧订阅复制入口及 24 小时有效期校验。
- 测速顶部圆圈使用运行指示并显示轨道；下方准确数量和阶段进度条继续保留，避免极小进度只显示一个点。

- 保留奶油色、炭灰和陶土橙主题，增加测速按钮与菜单图标形变。
- 日志按钮原位展开为历史面板；0.1.18 固定正文排版，使用绘制层连续改变轮廓、位置和透明度，减少展开时的内容切换。
- 本机保留最近 30 次测速，可查看失败原因、分类统计、过程与启动环境，筛选未成功任务。支持保存或分享所选任务及全部历史的 TXT / JSON。
- 阶段变化即时记录，进度约每 5 秒采样；每次最多 512 条事件，超限标明截断。终态无法确认时明确提示，不据此推断故障根因。日志不含节点、候选地址、订阅链接、凭据或原始异常文字。

## 安装使用

已有版本直接覆盖安装以保留数据。导入自己的 VLESS + WebSocket + TLS 节点，暂停 VPN 后选择当前网络测速；至少 10 个完整节点通过才生成正式结果。发布前预览并确认；若无法访问云端，请恢复可访问 Worker 的网络后重试。四种网络场景独立保存。

加密备份包含节点和管理身份，请勿公开分享。日志分享由用户自行选择应用和接收人。

## 校验与验证范围

APK：`YunYouXuan-Android-arm64-v0.1.19-test.apk`，44,391,790 字节。

SHA256：`b3a3946553adf212901521a97729e40f208af19e7ff3347933923f885917a6b9`。

0.1.19 构建验收记录：120 项 JVM/Robolectric/Compose 测试通过，Lint 0 错误、4 条既有警告；Debug、AndroidTest、签名 Release 构建及签名、16 KB 静态对齐检查通过。桌面逐帧检查不能证明真机帧率。

未完成真机覆盖安装、荣耀 Magic7 Pro / Android 16 长时间前台与锁屏测速、真实节点端到端及设备仪器测试，仍作为测试版发行。Windows 便携版独立保持 v1.3.7。

源码和完整验收记录在作者私有 cloudflare-ip-subscription 仓库；公开工具箱提供同一 APK。Android 实现提交为 `b962bbd289ce0a2c5dfbda5c4fcf1f79a7b325a8`。第三方组件的许可与来源随 APK 保留。
