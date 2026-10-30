# 发布验证

## Android 4.8.3 / build41 — 2026-10-30

正式包名：com.hermes.mytv；最低 Android 5.0，targetSdk 34。此次只发布 APK，Mac 继续使用 v4.8 的既有 DMG。

| 项目 | 结果与验证层级 |
| --- | --- |
| 版本基线 | 本机最新 4.8.3 / code41 源码，未修改播放逻辑；独立发布副本只更新内置使用说明、版本记录与正式构建身份 |
| 构建 | Gradle 8.14.3 / AGP 8.13.0 / JDK21 / SDK36；assembleRelease、lintVitalRelease 通过 |
| 签名 | 原 GitHub 4.8 正式证书；apksigner v1/v2/v3 与 zipalign 校验通过 |
| 正式包设置 | 非 debuggable、非 testOnly、无 instrumentation、allowBackup=false |
| 覆盖升级 | 隔离 Android TV 14 / API34 模拟器；4.8/code30 → 4.8.3/code41 成功；收藏 CCTV1、appId、数据目录、数据 inode、首次安装时间保留 |
| 启动与界面 | 冷启动成功；三层菜单显示正常；关于页显示 4.8.3 (41) 与使用限制；AndroidRuntime 错误日志为空 |
| 安装内容 | 模拟器已安装 APK 回读 SHA-256 与最终发布包一致 |
| 隐私与文档 | 最终 APK 无个人邮箱、开发者 home 路径、明文签名密码、密钥、数据库或日志文件；内置说明和许可与发布资料一致 |
| 频道表 | 600 个频道、817 条 URL；与当前已清理源码表逐字节一致；未恢复带鉴权/会话参数的预置链接 |

### 复用的既有验收与限制

4.8.2 预览版的三层导航/超时验收、4.8.3 build41 的 23 项故障恢复检查，以及电视、手机和平板的安装验收，均为项目已有记录。本次核对记录和预览包哈希后复用；没有重新操作用户设备或重跑这些测试，也没有把预览 APK 与正式 APK 当作同一文件。

本次正式 APK 未做全频道、长时间播放、声音、实体遥控器或真实设备重启验收。凤凰中文/凤凰香港的上游稳定性问题仍未解决，Mac mini 源服务器尚未实现。预览版使用独立包名与调试证书，可与正式版并存，收藏和观看状态不自动迁移。

### 正式 APK 校验

- 文件：`myTV-Android-4.8.3-build41.apk`，4,555,083 字节。
- SHA-256：`16e9de53ee58ce074607bde46f35872cb70ee2d0a2b810146021aa911ca7d267`。
- 签名证书 SHA-256：`dcac58adfe909ca00ba16c2ecda4ca1affdbb09fa35d0deca1772b93e95fd4e2`。

## 4.8 历史发布验证

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
