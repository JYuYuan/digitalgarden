---
{"dg-publish":true,"permalink":"/03/jnc-audit-wx/","dg-note-properties":{}}
---

# jnc-audit-wx

> JNC 审计稽核微信小程序 - 任务管理与稽核系统移动端

---

## ⚡ 快速启动

```bash
# Node 版本
Node 16.x+（推荐 Node 18）

# 安装依赖
npm install

# 开发模式（开发环境）
npm run dev:weapp

# 生产模式（生产环境）
npm run prod:weapp

# 构建生产版本
npm run build:weapp

# 构建并部署
npm run build:prod

# 构建并上传小程序
npm run build:upload
```

**AppID:** `wx941d064c3feabfd2`

**其他常用命令：**
- 编译转换 JSX：`npm run beforeCompile`

---

## 📋 项目信息

- **项目名称**：jnc-audit-wx
- **项目类型**：Taro 3.x 微信小程序
- **开发状态**：#维护中
- **框架版本**：Taro 3.3.11
- **项目路径**：`/Users/dompling/WebstormProjects/Work/jnc-audit-wx`
- **创建日期**：2022-10-18

---

## 🛠️ 技术栈

### 核心技术

- **框架**：Taro 3.3.11（React 17.0.0）
- **状态管理**：DVA 2.4.1 + Redux + Redux Saga
- **UI 库**：Taro UI 3.0.0-alpha.3
- **语言**：TypeScript 4.9.5
- **构建工具**：Taro CLI + Webpack
- **包管理**：npm

### 主要依赖

**UI 组件：**
- `taro-ui` 3.0.0-alpha.3 - Taro UI 组件库
- `@antv/f2` 4.0.35 - 移动端图表库
- `taro-iconfont-cli` 3.3.0 - Iconfont 图标支持

**状态管理：**
- `dva` 2.4.1 + `dva-core` 2.0.4 - 基于 Redux 的状态管理框架
- `dva-loading` 3.0.22 - Loading 状态管理
- `react-redux` 7.2.2 - React Redux 绑定
- `redux-saga` 1.1.3 - 副作用管理
- `redux-logger` 3.0.6 - Redux 日志中间件

**工具库：**
- `moment` 2.29.1 - 时间处理
- `lodash` 4.17.21 - 工具函数库
- `vod-wx-sdk-v2` 1.1.2 - 腾讯云点播 SDK（视频上传）

**开发工具：**
- `@typescript-eslint` - TypeScript 代码检查
- `eslint` + `eslint-config-taro` - 代码规范
- `miniprogram-ci` 1.5.1 - 小程序 CI 工具

---

## 📂 项目结构

```text
jnc-audit-wx/
├── src/                        # 源代码目录
│   ├── pages/                  # 页面目录
│   │   ├── taskTab/            # 任务主页（TabBar）
│   │   ├── discover/           # 发现页（TabBar）
│   │   ├── manageTab/          # 管理页（TabBar）
│   │   ├── me/                 # 我的（TabBar）
│   │   ├── global/             # 全局页面
│   │   │   ├── login/          # 登录页
│   │   │   ├── otherLogin/     # 其他登录方式
│   │   │   ├── password/       # 修改密码
│   │   │   └── searchPage/     # 搜索页
│   │   ├── task/               # 任务分包
│   │   │   ├── taskList/       # 任务列表
│   │   │   ├── taskClock/      # 任务打卡
│   │   │   ├── taskDetail/     # 任务详情
│   │   │   └── messageList/    # 消息列表
│   │   ├── manage/             # 管理分包
│   │   │   ├── dailyReport/    # 日报
│   │   │   ├── dailyReportEdit/# 日报编辑
│   │   │   ├── attendance/     # 考勤
│   │   │   ├── performance/    # 绩效
│   │   │   ├── searchData/     # 数据查询
│   │   │   ├── examineList/    # 审核列表
│   │   │   └── examineEdit/    # 审核编辑
│   │   ├── common/             # 公共页面分包
│   │   │   ├── showImg         # 图片预览
│   │   │   └── uploadFiles     # 文件上传
│   │   └── cusMedia/           # 自定义媒体
│   │       ├── cusVideo/       # 自定义视频录制
│   │       └── cusRecorder/    # 自定义录音
│   ├── components/             # 公共组件
│   │   ├── FormComponent/      # 表单组件（核心动态表单）
│   │   ├── UploadImg/          # 图片上传组件
│   │   ├── DropdownFilter/     # 下拉筛选器
│   │   ├── FileList/           # 文件列表
│   │   ├── MediaPlay/          # 媒体播放器
│   │   ├── Business/           # 业务组件
│   │   │   ├── fileView.tsx    # 文件预览
│   │   │   └── taskInfoRenders.tsx # 任务信息渲染
│   │   ├── navbar/             # 导航栏
│   │   ├── Tabs/               # 标签页
│   │   ├── Panel/              # 面板
│   │   ├── CollapseCard/       # 折叠卡片
│   │   ├── CardTaskSimple/     # 任务卡片
│   │   ├── selectUser/         # 用户选择器
│   │   ├── AtInput/            # 自定义输入框
│   │   ├── FeildDisplay/       # 字段展示
│   │   ├── F2-wx/              # F2 图表组件
│   │   └── tpm/                # TPM 相关组件
│   ├── api/                    # API 服务层
│   │   ├── task/               # 任务相关 API
│   │   ├── manage/             # 管理相关 API
│   │   ├── discover/           # 发现相关 API
│   │   ├── me/                 # 个人中心 API
│   │   ├── message/            # 消息相关 API
│   │   ├── global/             # 全局 API（登录、上传等）
│   │   └── tpm/                # TPM 系统 API
│   ├── models/                 # DVA 数据模型
│   │   └── index.ts            # 模型入口
│   ├── utils/                  # 工具函数
│   │   ├── request.ts          # 网络请求封装
│   │   ├── dva.ts              # DVA 配置
│   │   ├── utils.ts            # 通用工具函数
│   │   ├── storage.ts          # 本地存储封装
│   │   ├── groupStorage.ts     # 分组存储
│   │   ├── apiConfig.ts        # API 配置
│   │   ├── constant.ts         # 常量定义
│   │   ├── buttonConfig.ts     # 按钮配置
│   │   ├── vod.ts              # 视频点播工具
│   │   └── typing.d.ts         # 类型定义
│   ├── hooks/                  # 自定义 Hooks
│   │   ├── useRequest.ts       # 请求 Hook
│   │   ├── useDidUpdateEffect.ts # 更新副作用 Hook
│   │   └── index.ts            # Hooks 入口
│   ├── assets/                 # 静态资源
│   │   └── imagePath.ts        # 图片路径配置
│   ├── plugins/                # 插件
│   │   ├── wxmap/              # 腾讯地图 SDK
│   │   └── cos-auth.js         # 腾讯云 COS 认证
│   ├── cloud/                  # 云函数
│   │   └── getUserInfo/        # 获取用户信息
│   ├── app.tsx                 # 应用入口
│   ├── app.config.ts           # 应用配置
│   └── app.scss                # 全局样式
├── config/                     # Taro 配置
│   ├── index.js                # 基础配置
│   ├── dev.js                  # 开发环境配置
│   └── prod.js                 # 生产环境配置
├── dist/                       # 编译输出目录
├── scripts/                    # 构建脚本
│   └── deploy-dist.sh          # 部署脚本
├── project.config.json         # 小程序项目配置
├── package.json                # 项目依赖配置
└── tsconfig.json               # TypeScript 配置
```

---

## 🎯 核心功能模块

### 1. 任务管理（Task）
- **任务列表**：查看和筛选任务
- **任务详情**：查看任务详细信息、附件、进度
- **任务打卡**：定位打卡、拍照打卡
- **任务消息**：任务相关消息通知

### 2. 管理功能（Manage）
- **日报管理**：日报填写、查看、编辑
- **考勤管理**：考勤记录、统计
- **绩效管理**：绩效数据查看
- **数据查询**：各类数据统计查询
- **审核流程**：审核列表、审核编辑

### 3. 发现（Discover）
- 功能探索和快捷入口

### 4. 个人中心（Me）
- 个人信息管理
- 密码修改
- 系统设置

### 5. 全局功能
- **登录认证**：支持微信登录、企业微信登录
- **文件上传**：图片、视频、文档上传（支持腾讯云 COS）
- **媒体录制**：自定义视频录制、音频录制
- **搜索功能**：全局搜索
- **图片预览**：支持多图预览、缩放

### 6. 动态表单（FormComponent）
- 支持多种字段类型（文本、数字、日期、选择器、文件上传等）
- 表单验证
- 动态显示隐藏
- 表单数据联动

---

## 🔧 配置说明

### 小程序配置（app.config.ts）

**TabBar 配置：**
- 4 个主 Tab：任务、发现、管理、我的
- 主题色：`#2a83f7`（蓝色）

**分包策略：**
- `pages/task/` - 任务相关页面
- `pages/manage/` - 管理相关页面
- `pages/common/` - 公共页面（图片预览、文件上传）

**权限配置：**
- 位置权限：`scope.userLocation`（用于任务打卡、定位）
- 文件上传/下载超时：20 分钟

**全局组件：**
- `f2-wx` - F2 图表组件（全局注册）

### Taro 配置（config/index.js）

**设计稿尺寸：**
- `designWidth: 750`（750px 设计稿）

**路径别名：**
- `@/components` → `src/components`
- `@/utils` → `src/utils`
- `@/api` → `src/api`
- `@/assets` → `src/assets`
- `@/models` → `src/models`
- `@/plugins` → `src/plugins`
- `@/pages` → `src/pages`
- `@/hooks` → `src/hooks`

**CSS Modules：**
- 开启 CSS Modules 支持
- 命名模式：`[name]__[local]___[hash:base64:5]`

**资源处理：**
- 图片转 base64 阈值：1024 字节

### 环境配置

**开发环境（dev.js）：**
- `ENV: "uat"`
- `QY_APP_ID: "audit-wx"`
- `APPID: "wx941d064c3feabfd2"`

**生产环境（prod.js）：**
- `ENV: "uat"`
- 开启主包优化：`optimizeMainPackage: true`

**API 配置（apiConfig.ts）：**
- 权限中心接口：`password-${env}.jncapp.cn`
- SAC 接口：`api-sac-${env}.jncapp.cn`
- TPM v1 接口：`api-tpm-${env}.jncapp.cn`
- TPM v2 接口：`api-tpm-v2-${env}.jncapp.cn`

---

## 🌍 状态管理架构

项目使用 **DVA** 架构进行状态管理：

```typescript
// DVA = React + Redux + Redux Saga

// 特点：
// 1. 简化 Redux 样板代码
// 2. 内置 Redux Saga 处理异步逻辑
// 3. 内置 Loading 状态管理（dva-loading）
// 4. 基于 namespace 的模块化设计
```

**数据流：**
```
用户操作 → dispatch(action) → effects(异步) → reducers(同步) → state 更新 → 视图刷新
```

---

## 🔗 相关项目

- [[03-小程序项目/andromeda-wx\|andromeda-wx]] - Andromeda SFA 销售自动化小程序
- JNC 审计系统后端 API

---

## 🐛 常见问题

### 1. 企业微信与微信小程序兼容
- 项目支持企业微信和微信小程序双端
- 通过 `global.isQy` 判断运行环境
- 企业微信特定逻辑通过 `res.environment` 检测

### 2. 小程序跳转与数据传递
- 支持从其他小程序跳转进入
- 通过 `callbackResult.referrerInfo.extraData` 接收跳转数据
- 默认设置为 DMS 系统数据

### 3. 视频上传
- 使用腾讯云点播 SDK（vod-wx-sdk-v2）
- 支持视频压缩和进度显示

---

## 📝 开发规范

### 目录规范

1. **页面组件**：使用 `.tsx` 扩展名（TypeScript + JSX）
2. **配置文件**：使用 `.config.ts` 扩展名
3. **工具函数**：统一放在 `utils/` 目录，使用 TypeScript
4. **API 服务**：统一放在 `api/` 目录，按业务模块分类
5. **组件命名**：使用 PascalCase（大驼峰）

### 代码规范

1. **使用 TypeScript**：所有新代码使用 TS 编写
2. **API 调用统一封装**在 `api/` 层
3. **使用 Taro Hooks**：优先使用函数组件 + Hooks
4. **DVA 模型管理**：复杂状态使用 DVA models 管理
5. **样式隔离**：使用 CSS Modules 避免样式冲突
6. **图片资源**：统一在 `imagePath.ts` 中管理

### 性能优化

1. **分包加载**：按业务模块分包，减小主包体积
2. **主包优化**：生产环境开启 `optimizeMainPackage`
3. **图片优化**：小图片转 base64，大图片使用 CDN
4. **按需加载**：使用 Taro 动态导入
5. **请求优化**：使用 DVA Loading 统一管理请求状态

---

## 📅 更新日志

| 日期 | 版本 | 描述 |
|------|------|------|
| 2026-06-16 | - | AI 自动生成项目完整文档 |
| 2022-10-18 | - | 项目创建 |

---

## 🔖 标签

#小程序 #微信小程序 #跨端小程序 #React-17 #Taro #TaroUI #TypeScript #DVA #Redux #审计系列 #稽核系统 #任务管理 #维护中

---

## 相关链接

- [[01-索引/技术栈索引\|技术栈索引]]
- [[01-索引/项目总览\|项目总览]]
- [[03-小程序项目/andromeda-wx\|andromeda-wx]]
- [Taro 官方文档](https://taro-docs.jd.com/)
- [Taro UI 文档](https://taro-ui.jd.com/)
- [DVA 官方文档](https://dvajs.com/)
- [React 官方文档](https://react.dev/)
- [微信小程序官方文档](https://developers.weixin.qq.com/miniprogram/dev/framework/)
