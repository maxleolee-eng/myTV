# 4.8 发布验证

日期：2026-10-24。

| 项目 | 结果与验证层级 |
| --- | --- |
| Android 构建 | AGP 8.13.0、Gradle 8.14.3、JDK 17；assembleRelease / lintVitalRelease 通过 |
| Android 签名 | apksigner 验证 v1/v2/v3 通过，证书与 4.7 一致 |
| Android 安装与界面 | Android 16.1 无窗口模拟器；4.7 安装后覆盖升级 4.8 成功，关于页与内置文档弹窗可读，无 AndroidRuntime 异常 |
| Android 隐私设置 | 发布包非 debuggable，allowBackup=false；无通讯录、定位、相机、麦克风、共享存储权限 |
| Mac 构建与签名 | arm64、最低 macOS 13；App 和 DMG 使用 Developer ID 签名，挂载后严格签名校验通过 |
| Mac 路径 | 资源由 Bundle 定位，用户状态由系统当前用户目录定位；最终二进制无开发者 home 路径，动态库仅依赖系统路径 |
| Mac 新界面 | 关于页与使用说明正文离屏渲染并人工检查；未在前台完整操作应用窗口 |
| 最终安装包 | APK 与 DMG 中全部内置产品文档、许可文件逐字节比对通过；频道表一致，600 频道 / 817 URL |
| 敏感数据 | 未发现个人邮箱、开发者 home 路径、明文构建密码、私钥/keystore、日志或用户数据文件；带鉴权/会话参数的 70 条预置 URL 已移除 |
| DMG 完整性 | hdiutil verify、只读静默挂载、App 与镜像签名验证通过；只含 myTV.app 与 Applications 安装链接 |

## 边界

Mac **未完成 Apple 公证**，Gatekeeper 评估为 `Unnotarized Developer ID`。签名有效不代表 Apple 公证通过，其他 Mac 下载后可能需要在系统“隐私与安全性”中确认来源。不提供 Intel 构建。

本次未重复全量播放测试，未操作用户实际手机或电视，未验证全频道实时播放；原 4.7 在 2026-10-21 的解码记录仅作为历史基线。电视遥控器兼容性、Mac 完整窗口交互和更早 Android 系统的实际安装仍有待设备验证。软件使用限制不代替第三方源及节目授权。

## 安装包 SHA-256

- `myTV-Android-4.8-build30.apk`（4,546,891 字节）：`836143f3ffd44368270c1c3f189d2fe4b2fc5a40fcb83efb7e883be675c55442`
- `myTV-macOS-4.8-arm64.dmg`（2,578,276 字节）：`a462d144dff6f5f62f4c700758577bd537bb98b18fa03af397b203fa08963a3c`
