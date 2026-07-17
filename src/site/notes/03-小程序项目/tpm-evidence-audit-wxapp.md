---
{"dg-publish":true,"permalink":"/03/tpm-evidence-audit-wxapp/","dg-note-properties":{}}
---

# tpm-evidence-audit-wxapp

> TPM 证据审计微信小程序 - 基于 Taro 的跨端应用

---

## ⚡ 快速启动

```bash
# Node 版本
Node 12.x+（推荐 Node 16）

# 安装依赖
npm install

# 微信小程序开发
npm run dev:weapp

# 生产环境编译
npm run realy_dev:weapp

# 构建微信小程序
npm run build:weapp

# 构建并上传（需配置）
npm run build:upload
```

**打开项目：**
使用微信开发者工具打开 `dist/` 目录

---

## 📋 项目信息

- **项目名称**：tpm-evidence-audit-wxapp (内部名: live-miniapp)
- **项目类型**：Taro 跨端小程序
- **开发状态**：#维护中
- **版本**：v1.0.0
- **支持平台**：微信小程序（主）、支付宝、百度、字节跳动等
- **项目路径**：`/Users/dompling/WebstormProjects/Work/tpm-evidence-audit-wxapp`

---

## 🛠️ 技术栈

### 核心技术

- **框架**：Taro 3.5.3 + React 17.0.0
- **UI 库**：Taro UI 3.1.0-beta.4
- **状态管理**：Redux 4.1.0 + Redux Thunk 2.3.0 + React Redux 7.2.4
- **语言**：TypeScript 4.1.0
- **样式**：Less
- **构建工具**：Taro CLI 3.5.3
- **包管理**：npm

### 主要依赖

**Taro 核心：**
- `@tarojs/taro` 3.5.3 - Taro 运行时
- `@tarojs/react` 3.5.3 - React 支持
- `@tarojs/components` 3.5.3 - 跨端组件库
- `@tarojs/redux` 2.2.10 - Redux 支持

**腾讯云 SDK（小程序版）：**
- `cos-wx-sdk-v5` 1.0.10 - 对象存储 COS（小程序）
- `tim-wx-sdk` 2.13.1 - 即时通讯 IM（小程序）
- `trtc-wx-sdk` 1.0.4 - 实时音视频（小程序）
- `vod-js-sdk-v6` 1.7.1-beta.1 - 点播服务
- `wx-server-sdk` 2.5.3 - 云开发 SDK

**工具库：**
- `lodash` 4.17.21 - 工具函数库
- `md5-node` 1.0.1 - MD5 加密
- `rc-field-form` 2.2.1 - 表单管理

---

## 📂 项目结构

```text
tpm-evidence-audit-wxapp/
├── config/              # Taro 配置
│   ├── dev.js          # 开发环境配置
│   └── prod.js         # 生产环境配置
├── src/
│   ├── pages/          # 页面
│   ├── components/     # 组件
│   ├── store/          # Redux store
│   ├── services/       # API 服务
│   ├── utils/          # 工具函数
│   ├── app.tsx         # 入口文件
│   ├── app.config.ts   # 应用配置
│   └── app.less        # 全局样式
├── dist/               # 编译产物
├── scripts/            # 构建脚本
│   └── deploy-dist.sh  # 部署脚本
└── package.json
```

---

## 🎯 核心功能模块

### 1. 证据采集
- 拍照采集
- 录像采集
- 音频录制
- 位置信息采集

### 2. 证据管理
- 证据上传（腾讯云 COS）
- 证据列表
- 证据详情查看
- 离线缓存

### 3. 审计流程
- 审计任务列表
- 审计进度跟踪
- 审计结果提交
- 实时通知（IM）

### 4. 实时通讯
- 即时消息（TIM）
- 实时音视频（TRTC）
- 在线客服

---

## 🔧 配置说明

### Taro 配置

**支持平台：**
- 微信小程序（主要）
- 支付宝小程序
- 百度智能小程序
- 字节跳动小程序
- QQ 小程序
- 京东小程序
- 快应用

**编译配置：**
- Mini Runner：小程序端编译
- Webpack Runner：H5 端编译

### 跨端适配

Taro 3.x 采用 React 语法，统一编译到各小程序平台：
- 使用 Taro 组件库保证跨端一致性
- 平台差异通过 `process.env.TARO_ENV` 判断

---

## 🌍 环境配置

**环境变量：**
- `NODE_ENV` - 构建环境（development/production）
- `TARO_ENV` - 目标平台（weapp/alipay/swan 等）

---

## 🔗 相关项目

- [[04-移动端项目/tpm-evidence-audit-android\|tpm-evidence-audit-android]] - TPM 证据审计 Android
- [[02-Web端项目/jnc-audit-web\|jnc-audit-web]] - 审计 Web 端
- [[02-Web端项目/jnc-tpm-web\|jnc-tpm-web]] - TPM Web 端

---

## 🔄 与 Android App 的关联

[[03-小程序项目/tpm-evidence-audit-wxapp\|tpm-evidence-audit-wxapp]] 和 [[04-移动端项目/tpm-evidence-audit-android\|tpm-evidence-audit-android]] 是 TPM 证据审核移动端业务的两个客户端实现。两端重点共享 `liveFollow` 直播陪审、现场拍照、转录播、TIM 信令和 TRTC 直播流程。

### 业务流程对应

| 小程序流程 | Android 对应 | 共享点 |
|------------|--------------|--------|
| `pages/liveFollow/index/index` 任务列表 | `HomeListFragment` / `HomeFragment` | 任务列表和状态刷新 |
| `pages/liveFollow/task/backlog/index` 待执行详情 | `ActivityFragment` | 任务详情、排队、接收 `pushUrl`、进入直播 |
| `pages/liveFollow/takePicture` 现场拍照 | `TakePhotoFragment` / `ExecutedFragment` | 拍照配置、图片上传、现场执行提交 |
| `pages/liveFollow/liveVideo/liveRoom` 直播间 | `VideoCallCallingFragment` | TIM 信令、TRTC 进房、混流、定位回传 |
| `pages/liveFollow/videotape` 录播 | `RecordExecuteFragment` / `RecordVideoFragment` | VOD 上传签名、录播提交 |

### 共享后端接口

两端使用同一批 TPM 直播审核接口：

- 任务列表/详情：`live/app/v1/task/list/query`、`live/app/v1/task/detail/query`
- 现场拍照：`live/app/v1/scene/{taskCode}`、`live/app/v1/scene/execute`、`live/app/v1/scene/query`、`live/app/v1/file/upload`
- 排队：`live/app/v1/line/up`、`live/app/v1/line/cancel`、`live/app/v1/task/currentLineUpMember/query`
- 直播前校验和签名：`live/app/v1/connected/check/{taskCode}`、`live/app/v1/im/sig/create`
- 混流：`live/web/v1/task/mix/start`、`live/web/v1/task/mix/stop`
- 转录播：`live/app/v1/video/refuse`、`live/app/v1/video/confirm`、`live/app/v1/video/signature/create`、`live/app/v1/video/record/save`
- 日志：`systemDashboard/v1/log/save`

小程序接口主要在 `src/services/task.ts`、`src/services/live.ts`、`src/services/videotape.ts`、`src/services/api.ts`；Android 对应在 `app/src/main/java/com/jnc/audit/http/api/TaskApi.java`、`LoginApi.java`、`TakePicture.java`、`RecordExecuteApi.java`。

### TIM/TRTC 共享契约

- SDK App ID：`1400380294`
- TRTC 用户 ID：`<当前 appUserCode>_auditUserCode<审核员 appUserCode>`
- TRTC 房间 ID：`taskCode`
- TRTC 流 ID：`taskCode`
- 混流 ID：`mix_<taskCode>_<审核员 appUserCode>`
- 混流参数：`videoFramerate: 15`、`videoBitrate: 550`

两端共享 TIM key：

- 接收：`pushUrl`、`liveStop`、`checkForm`、`msg`、`queueNumber`、`liveQueueStatus`、`fail`、`liveLine`、`grantVideoStatus`、`taskChange`、`getPushUrl`、`getLocation`、`resetLogin`
- 发送：`msg`、`minxStart`、`playUrl`、`checkForm`、`location`、`windowSize`、`locationDistance`

### 实现差异

- 小程序通过 `trtc-wx-sdk` 生成微信原生 `LivePusher` 参数；Android 使用腾讯原生 `TRTCCloud` 和 `TXCloudVideoView`。
- 小程序 TIM 分发通过 `Taro.getApp()[key]` 加 `setTIMListener(route, code)` 约束页面和任务；Android `IMMessageDispatcher` 按 key 全局分发，再由 Fragment 用 `code == taskCode` 过滤。
- 小程序直播上下文依赖 `Taro.getApp().liveJson`、`photoGPS`、`reportLocation`、`trtcConfig`；Android 使用 `TaskInfo.pushMessage`、`TrtcConfig`、`LocationHelper` 和 `currentTask`。
- Android 额外通过 `TRTCNetworkManager` 监听网络质量并调整码率；小程序主要依赖 TRTC-WX/LivePusher 事件回调。

### 跨端改动检查点

- 改接口、任务状态、TIM key 或 TRTC 参数时，同时检查 [[04-移动端项目/tpm-evidence-audit-android\|tpm-evidence-audit-android]]。
- 改 `pushUrl`、`getLocation`、`getPushUrl`、`checkForm` 或混流 payload 时，先确认两端 JSON 字段一致。
- 修复任务号误消费、跨页面消息串扰或直播重入时，小程序查 `src/utils/tim.ts` 和页面 `setTIMListener`，Android 查 `IMMessageDispatcher` 和各 Fragment 的 `isInvalidMessage`。
- 调整直播画面、音频、混流或断网策略时，小程序查 `src/components/trtc-room/index.tsx` 和 `liveRoom.tsx`，Android 查 `VideoCallCallingFragment` 和 `TRTCNetworkManager`。

---

## 🐛 常见问题

_暂无记录。遇到问题后会记录在 [[问题记录\|问题记录]] 中。_

**已知注意事项：**

1. **腾讯云 SDK 版本**
   - 必须使用小程序版 SDK（`-wx` 后缀）
   - 与 Web 版 SDK API 有差异

2. **Taro 3.x 限制**
   - 部分 React API 不支持
   - 小程序原生 API 需通过 `Taro.xxx` 调用

---

## 📝 开发规范

### 组件开发

1. **使用 React Hooks**
2. **Taro UI 组件优先**
3. **样式使用 Less**
4. **遵循 Taro 最佳实践**

### 跨端开发

1. **使用 Taro 组件**，避免平台特定组件
2. **条件编译**：`process.env.TARO_ENV === 'weapp'`
3. **API 兼容**：使用 Taro 封装的 API

---

## 📅 更新日志

| 日期 | 版本 | 描述 |
|------|------|------|
| 2026-06-18 | - | 补充与 Android App 的跨端接口、TIM/TRTC 契约和改动检查点 |
| 2026-06-16 | v1.0.0 | AI 自动补充项目文档信息 |
| 2026-06-15 | - | 创建知识库文档 |

---

## 🔖 标签

#小程序 #微信小程序 #跨端小程序 #React-17 #Taro #TaroUI #Redux #TypeScript #腾讯云 #腾讯云IM #腾讯云TRTC #腾讯云COS #TPM系列 #证据审计 #维护中

---

## 相关链接

- [[01-索引/技术栈索引\|技术栈索引]]
- [[01-索引/项目总览\|项目总览]]
- [[问题记录\|问题记录]]
- [Taro 官方文档](https://taro-docs.jd.com/)
- [Taro UI 文档](https://taro-ui.jd.com/)
