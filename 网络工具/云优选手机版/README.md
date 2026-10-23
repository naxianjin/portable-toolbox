# 云优选手机版 · Android 测试版

在手机当前网络上优选 Cloudflare IP，再按场景预览和发布订阅。当前版本 **0.1.12-test**，适用于 **Android 8 及以上 / ARM64**。真机回测目标包括荣耀 Magic7 Pro / Android 16 与 iQOO；尚未确认荣耀约两分钟停止的唯一原因。

[手机端下载测试地址](https://github.com/naxianjin/portable-toolbox/releases/tag/yunyouxuan-android-v0.1.12-test) · [直接下载 APK](https://github.com/naxianjin/portable-toolbox/releases/download/yunyouxuan-android-v0.1.12-test/YunYouXuan-Android-arm64-v0.1.12-test.apk) · [SHA256 校验文件](https://github.com/naxianjin/portable-toolbox/releases/download/yunyouxuan-android-v0.1.12-test/YunYouXuan-Android-arm64-v0.1.12-test.apk.sha256) · [在线订阅器](https://cloudflaresub.naxianjin8.workers.dev/)

更新时间：2026-10-23（北京时间）。这是测试版，不替代 Windows 便携版；手机测速无需电脑、CMD 或 Termux。

## 安装和使用

1. 下载 APK，在系统提示中允许本次安装；已有云优选可直接覆盖安装，保留应用数据。
2. 在节点管理中导入自己的 VLESS + WebSocket + TLS 原始节点。程序不提供原始节点。
3. 暂停 VPN，选择当前 Wi-Fi/移动数据和 IPv4/IPv6 场景，开始测速。测完先保存到手机。
4. 下载合格至少 10 个才进入完整节点验证，完整节点至少 10 个通过才生成正式结果。可复制或导出节点。
5. 前往订阅页预览并确认发布。**若无法成功发布，请打开 VPN 后重试。** 四种网络场景的结果与订阅独立保存。

本版使用橙色云流图标；侧栏点击后立即切页，修复展开动画期间的点击失灵。遇到下载服务 HTTP 429 时显示冷却，整轮最多恢复一次；仍受限时保留旧结果，稍后再试。

## 校验与已知范围

APK 文件：`YunYouXuan-Android-arm64-v0.1.12-test.apk`，44,325,770 字节。

SHA256：`030040766914f156bb22fcce6c919eebb1af2d067a5ecc647993ab1119cd3c04`。

本轮独立运行84项JVM/Robolectric/Compose测试及额外6项审核测试均通过；签名Release静态验收与16KB对齐通过，Lint 0错误、4警告。以上不代替真机验收，实际测速、系统后台策略和桌面显示仍需设备验证。

完整源码、构建脚本、文档与验收记录保存在作者的私有 `cloudflare-ip-subscription` 仓库；私有仓库发行版也保存相同 APK、校验文件及发布说明。公开工具箱提供下载副本。本轮源码提交与发行验收结果见发布记录。

libXray/Xray-core、AndroidX、Kotlin、OkHttp、ZXing 等第三方组件的许可和来源随 APK 打包；界面历史参考项目的 MIT 许可保留在包内，不改变各组件原许可。

本轮修复网络能力回调同步查询竞态及迟到事件误停；取消先记录协程原因再关闭引擎，停止诊断保留阶段、耗时和进度。独立技术审核未发现确定阻塞产品缺陷，但精确模型与官方路由未独立核验，不能登记为已核验该身份。未进行真机或真实节点测速。
