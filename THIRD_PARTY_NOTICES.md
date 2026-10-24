# 第三方组件与外部数据

## Android

播放器使用 AndroidX Media3 1.4.1（ExoPlayer、HLS、UI）及其传递依赖。Media3 由 Android Open Source Project 贡献者提供，采用 Apache License 2.0；其仓库 LICENSE 另载有部分第三方代码声明，完整上游文本随包保留于 licenses/MEDIA3-LICENSE.txt。

- Media3：https://github.com/androidx/media/tree/1.4.1
- AndroidX：https://developer.android.com/jetpack/androidx
- Apache License 2.0：licenses/Apache-2.0.txt

本产品的非商业、禁止修改条款不限制第三方组件原许可证授予的权利。具体已解析依赖列于 licenses/ANDROID-DEPENDENCIES.txt；另附 Guava、Kotlin 与 JetBrains annotations 的上游许可、Kotlin NOTICE 及 Apache-2.0 全文。

## macOS

使用 Apple 系统提供的 SwiftUI、AppKit、AVKit、AVFoundation、Foundation 和 Combine；未随包复制第三方播放器框架。Apple 名称及商标归其权利人所有，不表示 Apple 为本产品背书。

## 外部频道数据

预置频道数据来自本地既有频道归档；本次仅进行发布清理，没有取得新的内容授权。应用内增量维护会访问以下外部频道表：

- https://github.com/Guovin/iptv-api
- https://github.com/suxuang/myIPTV
- https://github.com/vbskycn/iptv
- https://github.com/iptv-org/iptv
- https://github.com/Kimentanm/aptv
- https://github.com/YanG-1989/m3u

引用地址不是对其可用性、授权范围或安全性的保证。本产品许可不重新授权任何直播内容、频道名称、商标或第三方频道表；相关权利归原权利人所有。请仅观看你有权访问的内容。权利问题请通过官方仓库 Issue 联系，勿公开敏感信息。
