---
{"dg-publish":true,"permalink":"/04/xiao-zhi-bo/","dg-note-properties":{}}
---

# XiaoZhiBo

> 腾讯云“小直播”场景化解决方案，包含 iOS 与 Android 双端工程，面向秀场直播、电商直播、企业直播等音视频直播场景。

---

## 项目信息

- **项目名称**：XiaoZhiBo（小直播）
- **项目类型**：移动端直播解决方案
- **平台**：iOS + Android
- **项目版本**：Version 9.3（2021-11-16）
- **开发状态**：#历史项目
- **项目路径**：`<工作区>/XiaoZhiBo`

---

## 技术栈

### iOS

- Swift / Objective-C 混合工程
- CocoaPods
- Xcode 11+
- iOS 13.0+
- 腾讯云直播、IM、美颜等 TUI 组件

### Android

- Android Gradle Plugin 4.2.1
- Kotlin 1.5.31
- 腾讯云 LiteAV SDK
- 腾讯云 IM SDK
- 多 Module 组件化工程

---

## 主要模块

### iOS

- `APP` - 主应用与场景业务
- `TUIPusher` - 推流
- `TUIPlayer` - 拉流
- `TUIBeauty` - 美颜
- `TUIGift` - 礼物
- `TUIBarrage` - 弹幕
- `TUIAudioEffect` - 音效

### Android

- `app` - 主应用
- `showlive` - 直播场景
- `login` - 登录
- `basic` - 基础能力
- `tuipusher` / `tuiplayer` - 推拉流
- `tuibeauty` - 美颜
- `tuibarrage` - 弹幕
- `tuiaudioeffect` - 音效
- `tuigift` - 礼物

---

## iOS 运行方式

```bash
cd XiaoZhiBo/iOS/APP
pod install
```

使用 Xcode 打开生成的 `XiaoZhiBoApp.xcworkspace`，配置腾讯云 License、SDKAppID、SecretKey、播放域名和后台服务地址后运行。

---

## Android 运行方式

使用 Android Studio 打开 `XiaoZhiBo/Android` 工程，同步 Gradle 后运行 `app` 模块。

---

## 配置注意事项

- iOS 主要配置位于 `iOS/APP/Debug/GenerateGlobalConfig.swift` 和 `GenerateTestUserSig.swift`。
- Android 依赖 LiteAV 与 IM SDK，版本和 Maven 配置集中在顶层 `build.gradle`。
- 项目依赖腾讯云直播相关服务，运行前需要准备对应 License 和云服务参数。

---

## 更新日志

| 日期 | 版本 | 描述 |
|------|------|------|
| 2026-09-15 | - | 补充到 Work Projects Wiki |
| 2021-11-16 | 9.3 | Android / iOS 小直播组件化版本 |

---

## 标签

#移动端 #iOS #Android #腾讯云 #直播 #音视频 #历史项目

---

## 相关链接

- [[01-索引/项目总览\|项目总览]]
- [[01-索引/快速导航\|快速导航]]
- [[01-索引/技术栈索引\|技术栈索引]]
