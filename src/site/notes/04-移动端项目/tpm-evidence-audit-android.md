---
{"dg-publish":true,"permalink":"/04/tpm-evidence-audit-android/","dg-note-properties":{}}
---

# tpm-evidence-audit-android

> TPM 证据审计 Android 应用 - 原生 Android 开发

---

## ⚡ 快速启动

```bash
# 环境要求
Android Studio 4.0+
JDK 1.8+
Gradle 6.0+

# 打开项目
使用 Android Studio 打开项目根目录

# 构建项目
./gradlew build

# 调试运行
点击 Android Studio 的 Run 按钮

# 打包 APK（Debug）
./gradlew assembleDebug

# 打包 APK（Release）
./gradlew assembleRelease
```

**输出目录：** `app/build/outputs/apk/`

---

## 📋 项目信息

- **项目名称**：tpm-evidence-audit-android
- **应用包名**：com.jnc.audit
- **项目类型**：Android 原生应用
- **开发状态**：#维护中
- **项目路径**：`/Users/dompling/WebstormProjects/Work/tpm-evidence-audit-android`

### 版本信息

- **Min SDK**：根据 `build_versions.min_sdk` 配置
- **Target SDK**：根据 `build_versions.target_sdk` 配置
- **Version Code**：根据 `build_versions.version_code`
- **Version Name**：根据 `build_versions.version_name`

---

## 🛠️ 技术栈

### 核心技术

- **平台**：Android
- **语言**：Java 8
- **构建工具**：Gradle 6.0+
- **架构**：MVVM + DataBinding
- **编译 SDK**：根据 `build_versions.target_sdk`
- **构建工具版本**：根据 `build_versions.build_tools`

### 主要依赖

**Android Jetpack：**
- `androidx.databinding` 4.0.1 - DataBinding
- `androidx.multidex` - 多 Dex 支持
- `lifecycle-common-java8` 2.2.0 - 生命周期组件

**网络请求：**
- `com.android.volley` 1.2.1 - 网络请求
- `retrofit` 2.9.0 - REST API 客户端
- `okhttp3` - HTTP 客户端（通过 Retrofit）

**图片加载：**
- `glide` 4.11.0 - 图片加载框架
- `okhttp3-integration` 4.11.0 - Glide + OkHttp 集成

**腾讯云 SDK：**
- `cos-android-nobeacon` 5.9.17 - 对象存储 COS
- `imsdk-plus` 5.4.666 - 即时通讯 IM
- `LiteAVSDK_TRTC` latest.release - 实时音视频 TRTC
- `TencentLocationSdk` 7.5.3 - 腾讯定位

**UI 组件：**
- `tencent:mmkv` 1.2.10 - 键值存储
- `AutoSize` 1.2.1 - 屏幕适配
- `refresh-layout-kernel` 2.0.6 - 下拉刷新
- `stateful-layout` 1.2.1 - 状态布局
- `iconics-core` 4.0.2 - 图标库
- `vlayout` 1.3.0 - 阿里 VLayout

**视频相关：**
- `camerakit` 0.13.1 - 相机录制
- `exoplayer-core` 2.14.1 - 视频播放
- `exoplayer-ui` 2.14.1 - 播放器 UI

**工具库：**
- `butterknife` - 视图绑定
- `Luban` 1.1.8 - 图片压缩
- `AgentWeb` 1.0.0 - WebView 封装

**插件化：**
- `replugin-plugin-lib` 3.0.0 - 360 插件化框架

**其他：**
- `bugly:crashreport` latest.release - 腾讯 Bugly 崩溃收集
- `umeng` 9.3.8 - 友盟统计
- `walle` 1.1.6 - 美团多渠道打包

---

## 📂 项目结构

```text
tpm-evidence-audit-android/
├── app/                    # 主模块
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/      # Java 源码
│   │   │   │   └── com/jnc/audit/
│   │   │   ├── res/       # 资源文件
│   │   │   └── AndroidManifest.xml
│   │   ├── debug/         # Debug 配置
│   │   └── release/       # Release 配置
│   ├── build.gradle       # 应用级构建配置
│   ├── env_config.yaml    # 环境配置
│   └── debug.jks          # Debug 签名文件
├── xpage-lib/             # 页面框架库
├── xpage-compiler/        # 页面框架编译器
├── build.gradle           # 项目级构建配置
├── versions.gradle        # 版本管理
└── gradle.properties      # Gradle 配置
```

---

## 🎯 核心功能模块

### 1. 证据采集
- 拍照采集（CameraKit）
- 视频录制（ExoPlayer）
- 音频录制
- GPS 定位（腾讯定位 SDK）
- 时间戳水印

### 2. 证据管理
- 证据上传（腾讯云 COS）
- 离线缓存（MMKV）
- 证据列表（VLayout）
- 证据预览
- 批量操作

### 3. 审计流程
- 任务列表
- 任务详情
- 审计提交
- 流程跟踪
- 实时通知（IM）

### 4. 实时通讯
- 即时消息（腾讯 IM SDK）
- 实时音视频（TRTC）
- 推送通知

### 5. 插件化
- RePlugin 插件框架
- 动态加载插件
- 插件独立更新

---

## 🔧 配置说明

### Gradle 配置

**环境配置（env_config.yaml）：**
- `debug` - 调试环境配置
- `release` - 生产环境配置

**配置项：**
- `BASE_URL` - API 基础 URL
- `BUGLY_APP_ID` - Bugly 应用 ID

### 签名配置

**Debug 签名：**
- KeyStore：`debug.jks`
- Password：`123456`
- Alias：`debug`

**Release 签名：**
- 从 `app_release.properties` 读取配置

### 构建类型

**Debug：**
- 可调试
- 不混淆代码
- 使用 Debug 签名

**Release：**
- 代码混淆（ProGuard）
- 资源压缩
- 使用 Release 签名
- 生成文件名：`auditOnline_v{versionCode}_{versionName}.apk`

---

## 🌍 环境配置

**环境变量通过 YAML 配置：**
- `app/env_config.yaml` - 环境配置文件
- `debug` / `release` 环境

---

## 🔗 相关项目

- [[03-小程序项目/tpm-evidence-audit-wxapp\|tpm-evidence-audit-wxapp]] - TPM 证据审计小程序
- [[02-Web端项目/jnc-audit-web\|jnc-audit-web]] - 审计 Web 端
- [[02-Web端项目/tpm-pc-manager\|tpm-pc-manager]] - TPM PC 管理系统

---

## 🔄 与小程序的关联

[[04-移动端项目/tpm-evidence-audit-android\|tpm-evidence-audit-android]] 和 [[03-小程序项目/tpm-evidence-audit-wxapp\|tpm-evidence-audit-wxapp]] 是 TPM 证据审核移动端业务的两个客户端实现。Android 是原生实现，小程序是 Taro/微信容器实现；两端共享直播陪审、现场拍照、转录播、TIM 信令和 TRTC 直播契约。

### Android 关键实现

- `app/src/main/java/com/jnc/audit/http/api/TaskApi.java`：任务、排队、连通性校验、混流、直播配置。
- `app/src/main/java/com/jnc/audit/http/api/LoginApi.java`：登录、修改密码、IM/TRTC 签名。
- `app/src/main/java/com/jnc/audit/http/api/TakePicture.java`：现场拍照配置、提交、详情、文件上传。
- `app/src/main/java/com/jnc/audit/http/api/RecordExecuteApi.java`：VOD 上传签名、录播提交、直播日志。
- `app/src/main/java/com/jnc/audit/fragment/task/ActivityFragment.java`：待执行任务详情、排队、接收 `pushUrl`、进入直播、转录播入口。
- `app/src/main/java/com/jnc/audit/fragment/task/VideoCallCallingFragment.java`：直播间、TIM 信令处理、TRTC 进房、混流、定位回传。
- `app/src/main/java/com/jnc/audit/config/IMConfig.java`：TIM 收发 key。
- `app/src/main/java/com/jnc/audit/utils/tencent/im/IMMessageDispatcher.java`：TIM 消息分发。
- `app/src/main/java/com/jnc/audit/utils/tencent/im/V2TIMInit.java`：TIM SDK 初始化、登录、C2C 文本消息。
- `app/src/main/java/com/jnc/audit/utils/TRTCNetworkManager.java`：TRTC 网络质量监听和码率调整。

### 与小程序页面对应

| Android 模块 | 小程序对应 | 共享点 |
|--------------|------------|--------|
| `ActivityFragment` | `src/pages/liveFollow/task/backlog/index.tsx` | 任务详情、排队、接收 `pushUrl`、进入直播 |
| `VideoCallCallingFragment` | `src/pages/liveFollow/liveVideo/liveRoom.tsx` | 直播间、TIM 信令、TRTC 进房、混流、定位 |
| `TakePhotoFragment` / `ExecutedFragment` | `src/pages/liveFollow/takePicture/` | 现场拍照配置、图片上传、提交执行 |
| `RecordExecuteFragment` / `RecordVideoFragment` | `src/pages/liveFollow/videotape/` | 录播表单、VOD 上传、录播提交 |
| `IMConfig` / `IMMessageDispatcher` | `src/utils/tim.ts` / `src/utils/timEnum.ts` | TIM key 和消息分发 |

### 共享后端接口

- 任务列表/详情：`live/app/v1/task/list/query`、`live/app/v1/task/detail/query`
- 现场拍照：`live/app/v1/scene/{taskCode}`、`live/app/v1/scene/execute`、`live/app/v1/scene/query`、`live/app/v1/file/upload`
- 排队：`live/app/v1/line/up`、`live/app/v1/line/cancel`、`live/app/v1/task/currentLineUpMember/query`
- 直播前校验和签名：`live/app/v1/connected/check/{taskCode}`、`live/app/v1/im/sig/create`
- 混流：`live/web/v1/task/mix/start`、`live/web/v1/task/mix/stop`
- 转录播：`live/app/v1/video/refuse`、`live/app/v1/video/confirm`、`live/app/v1/video/signature/create`、`live/app/v1/video/record/save`
- 日志：`systemDashboard/v1/log/save`

### TIM/TRTC 共享契约

- SDK App ID：`1400380294`
- TRTC 用户 ID：`<当前 appUserCode>_auditUserCode<审核员 appUserCode>`
- TRTC 房间 ID：`taskCode`
- TRTC 流 ID：`taskCode`
- 混流 ID：`mix_<taskCode>_<审核员 appUserCode>`
- 混流参数：`videoFramerate: 15`、`videoBitrate: 550`

共享 TIM key：

- 接收：`pushUrl`、`liveStop`、`checkForm`、`msg`、`queueNumber`、`liveQueueStatus`、`fail`、`liveLine`、`grantVideoStatus`、`taskChange`、`getPushUrl`、`getLocation`、`resetLogin`
- 发送：`msg`、`minxStart`、`playUrl`、`checkForm`、`location`、`windowSize`、`locationDistance`

### 跨端改动检查点

- 改接口、任务状态、TIM key 或 TRTC 参数时，同时检查 [[03-小程序项目/tpm-evidence-audit-wxapp\|tpm-evidence-audit-wxapp]]。
- 改 `pushUrl`、`getLocation`、`getPushUrl`、`checkForm` 或混流 payload 时，先确认两端 JSON 字段一致。
- Android 侧 TIM 分发按 key 全局广播，再由 Fragment 使用 `code == taskCode` 过滤；涉及串单、误消费、重入时重点检查 `IMMessageDispatcher` 和各 Fragment 的 `isInvalidMessage`。
- Android 原生 TRTC 有 `TRTCNetworkManager` 网络质量和码率逻辑；小程序主要依赖 `trtc-wx-sdk` 与 `LivePusher` 回调。调整直播质量策略时需要分别验证两端。

---

## 🐛 常见问题

_暂无记录。遇到问题后会记录在 [[问题记录\|问题记录]] 中。_

**已知注意事项：**

1. **多 Dex 支持**
   - 已启用 `multiDexEnabled true`
   - 方法数超过 65536 自动分包

2. **插件化框架**
   - 使用 360 RePlugin 3.0.0
   - 插件需独立编译和加载

3. **第三方 SDK 版本**
   - 腾讯云 SDK 使用最新版本
   - 注意 API 变更

---

## 📝 开发规范

### 代码规范

1. **MVVM 架构 + DataBinding**
2. **使用 ButterKnife 简化视图绑定**
3. **Retrofit + RxJava 处理网络请求**
4. **ProGuard 混淆规则**

### 资源命名

1. **布局文件**：`activity_*`, `fragment_*`, `item_*`
2. **ID 命名**：驼峰命名
3. **图片资源**：`ic_*`, `bg_*`, `img_*`

---

## 📦 构建与发布

### 多渠道打包

使用美团 Walle 进行多渠道打包：
- 配置文件：`multiple-channel.gradle`
- 快速生成多渠道包

### APK 上传

脚本：`uploadApk.gradle`
- 自动上传到分发平台
- Jenkins 集成

---

## 📅 更新日志

| 日期 | 版本 | 描述 |
|------|------|------|
| 2026-06-18 | - | 补充与小程序的跨端接口、TIM/TRTC 契约和改动检查点 |
| 2026-06-16 | - | AI 自动补充项目文档信息 |
| 2026-06-15 | - | 创建知识库文档 |

---

## 🔖 标签

#移动端 #Android #Java #MVVM #腾讯云 #腾讯云IM #腾讯云TRTC #腾讯云COS #TPM系列 #证据审计 #插件化 #维护中

---

## 相关链接

- [[01-索引/技术栈索引\|技术栈索引]]
- [[01-索引/项目总览\|项目总览]]
- [[问题记录\|问题记录]]
