# myTV 安装包校验

## 4.9.22

| 文件 | SHA-256 |
| --- | --- |
| myTV-Android-4.9.22-build66.apk | `2100419cf0930120527557964d31e7ba2eb71aeaffb4ed2ef810e3f0f145e877` |
| myTV-macOS-4.9.22-build22-arm64.dmg | `ea7a9ac136e709e083d7965652e833aa016cc7b9b97bb65cefa1bd2fee7e59e5` |

## 4.9.21

| 文件 | SHA-256 |
| --- | --- |
| myTV-Android-4.9.21-build65.apk | `8f57bc94993a6b4e1f4406b97b6debcfca31bd7fcc0b7d5129ecf5cc13e09816` |
| myTV-macOS-4.9.21-build21-arm64.dmg | `42c52b1a2e349493a735ffdd555504c35a3fbc1ac1303515182886013d767174` |

## 4.9.20 历史验证

## 安装与实测

Android Build 62 沿用正式签名。已实测从 4.9.19 覆盖升级并保留安装记录。Mac Build 19 适用于 Apple Silicon 和 macOS 13 及以上。App 与 DMG 已用 Developer ID 签名，尚未取得 Apple 公证。

北京联通直连下，Android 正式包的 CCTV-1、CCTV-6、CCTV-13 和六个卫视频道逐台持续播放 65–67 秒。Mac 的翡翠台与 TVB Plus 分别观察 70.1 秒和 70.1 秒，实际视频时间分别推进 69.9 秒和 67.9 秒。翡翠台排在广东目录前两位的线路均通过长播。第三条 HEVC 备用线路在复测中出现 4.0 秒画面间隔，本轮未达标。 CCTV-1 在 Mac 上首轮出现 3.2 秒画面间隔，复测在源2连续观看 70 秒。广东用户在本地网络上的实际长播成功率仍需新版回报。

Mac 故障测试中，首路播到约 8 秒后断流，或画面冻结但声音继续，两种情况都自动换到了源2，备用线路随后连续播放约 70 秒。Android 4.0.4 和 4.4.4 模拟设备分别连续观看标清 66.0 秒和 66.2 秒。旧系统测试使用测试端转换的 320×180 信号，4.4.4 使用系统标准软件解码器。

[下载六页图文升级说明](https://github.com/maxleolee-eng/myTV/releases/download/v4.9.20/myTV-4.9.20-Upgrade-Guide.pdf)。包含启动、央视、国内主要卫视、旧版安卓和两端选源操作的实拍截图。

## 下载文件的 SHA-256

| 文件 | SHA-256 |
| --- | --- |
| myTV-Android-4.9.20-build62.apk | `71fc0cf4254eb220445b1c57f9e9113c384f98207b7d6c6e0cbedd912c460622` |
| myTV-macOS-4.9.20-build19-arm64.dmg | `7357a66a9bca965d06d970aae04c0f0debc858bb637a7a9cb19b8171d7a5987b` |
| myTV-4.9.20-Upgrade-Guide.pdf | `bb249a608d8e194513e6db8a743749061ab44ad48e65980718604e826c8b8d4c` |

Android 4.0.0–4.0.2 未做实播。先前一份 4.0.3 固件能启动，直播未通过。4.0.3 真机尚未验收新版。
