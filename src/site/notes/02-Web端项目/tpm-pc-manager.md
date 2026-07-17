---
{"dg-publish":true,"permalink":"/02-web/tpm-pc-manager/","dg-note-properties":{}}
---

# tpm-pc-manager

> TPM PC 管理系统 - 第三方支付管理平台

---

## ⚡ 快速启动

```bash
# Node 版本
Node 11.x+（推荐 Node 16）

# 安装依赖
npm install

# 启动开发服务器
npm start
# 注意：Windows 环境变量设置，Mac/Linux 需要修改脚本

# 访问地址
http://localhost:3000（默认端口，根据配置可能不同）
```

**其他常用命令：**
- 构建（生产环境）：`npm run build`
- 代码检查：`npm run lint`
- 代码检查并修复：`npm run lint:fix`

---

## 📋 项目信息

- **项目名称**：tpm-pc-manager (内部名: test)
- **项目类型**：Web 前端应用
- **开发状态**：#维护中
- **版本**：v0.1.0
- **项目路径**：`/Users/dompling/WebstormProjects/Work/tpm-pc-manager`

---

## 🛠️ 技术栈

### 核心技术

- **框架**：React 16.13.1
- **UI 库**：Ant Design 4.22.8 + Ant Design Pro 组件
- **状态管理**：Redux 4.0 + Redux Toolkit 2.8.2 + Redux Thunk 2.3.0
- **路由**：React Router 5.1.2
- **语言**：TypeScript 5.5.4
- **构建工具**：Webpack 4.19.1（自定义配置）
- **包管理**：npm / yarn

### 主要依赖

**Ant Design Pro 组件：**
- `@ant-design/pro-card` 1.20.22 - 高级卡片组件
- `@ant-design/pro-form` 1.74.3 - 高级表单组件
- `@ant-design/pro-layout` 5.0.17 - 页面布局组件
- `@ant-design/pro-table` 2.7.4 - 高级表格组件

**腾讯云 SDK：**
- `tim-js-sdk` 2.7.0 - 即时通讯 IM
- `trtc-js-sdk` 4.11.6 - 实时音视频
- `vod-js-sdk-v6` 1.7.1 - 点播服务
- `cos-js-sdk-v5` 0.5.26 - 对象存储 COS

**工具库：**
- `lodash` 4.17.21 - 工具函数库
- `moment` latest - 时间处理
- `axios` 0.18.0 - HTTP 客户端

**地图集成：**
- `rc-bmap` 1.0.5 - 百度地图
- `react-qmap` 0.1.5 + `react-qqmap` 1.0.0 - 腾讯地图

**动画库：**
- `rc-banner-anim` 2.0.8 - 轮播动画
- `rc-queue-anim` 1.8.5 - 队列动画
- `rc-tween-one` 2.7.2 - 补间动画

**其他：**
- `video.js` 7.8.4 - 视频播放器
- `xlsx` 0.18.5 - Excel 处理
- `photoswipe` 4.1.2 + `react-viewer` 2.9.1 - 图片预览
- `react-draggable` 3.0.5 - 拖拽功能
- `react-resizable` 1.10.1 - 可调整大小

---

## 📂 项目结构

```
tpm-pc-manager/
├── config/              # Webpack 配置
├── public/              # 静态资源
├── scripts/             # 构建脚本
│   ├── start.js        # 开发服务器启动脚本
│   └── build.js        # 生产构建脚本
├── src/                 # 源代码
│   ├── components/      # 公共组件
│   ├── pages/           # 页面
│   ├── store/           # Redux store
│   ├── services/        # API 服务
│   ├── utils/           # 工具函数
│   └── ...
├── nginx/               # Nginx 配置
└── package.json
```

---

## 🚀 开发命令

### 启动项目

```bash
# 开发环境（Windows）
npm start

# 注意：脚本中设置了 NODE_ENV=development
```

### 构建项目

```bash
# 生产构建
npm run build
```

### 代码检查

```bash
# 运行 ESLint 并自动修复
npm run lint

# 完整的 lint 检查（包括样式）
npm run lint:fix
```

---

## 🎯 核心功能模块

### 1. 腾讯云集成

#### 即时通讯（TIM）
- SDK：tim-js-sdk@2.7.0
- 功能：聊天、消息推送

#### 实时音视频（TRTC）
- SDK：trtc-js-sdk@4.11.6
- 功能：视频会议、实时通话

#### 点播服务（VOD）
- SDK：vod-js-sdk-v6@1.7.1
- 功能：视频上传、播放

#### 对象存储（COS）
- SDK：cos-js-sdk-v5@0.5.26
- 功能：文件上传下载

### 2. 地图功能

- **百度地图**：rc-bmap@1.0.5
- **腾讯地图**：react-qmap@0.1.5, react-qqmap@1.0.0

### 3. 数据处理

- **Excel 导入导出**：xlsx@0.18.5
- **日期处理**：moment.js

### 4. UI 增强

- **图片预览**：photoswipe, react-viewer
- **视频播放**：video.js
- **拖拽**：react-draggable@3.0.5
- **可调整大小**：react-resizable@1.10.1
- **动画效果**：rc-banner-anim, rc-queue-anim, rc-tween-one

---

## 🔧 配置说明

### Webpack 配置

项目使用自定义 Webpack 配置：
- 位于 `config/` 目录
- 支持 Less/Sass 预处理器
- 配置了 Babel 转译
- 代码分割和优化

### Babel 配置

```json
{
  "presets": ["react-app"],
  "plugins": [
    ["import", {
      "libraryName": "antd",
      "libraryDirectory": "es",
      "style": true
    }]
  ]
}
```

**功能：**
- Ant Design 按需加载
- 自动引入样式文件

### ESLint 配置

- 基于 `eslint-config-react-app`
- TypeScript 支持
- 提交前自动检查（pre-commit hook）

---

## 🌍 环境配置

**环境变量管理：**
- `.env` 文件配置环境变量
- `dotenv@6.0.0` 加载环境变量
- `dotenv-expand@4.2.0` 支持变量扩展

---

## 🔗 相关项目

- [[02-Web端项目/jnc-tpm-web\|jnc-tpm-web]] - TPM Web 端
- [[02-Web端项目/jnc-tpm-react\|jnc-tpm-react]] - TPM React 项目
- [[03-小程序项目/tpm-evidence-audit-wxapp\|tpm-evidence-audit-wxapp]] - TPM 证据审计小程序
- [[04-移动端项目/tpm-evidence-audit-android\|tpm-evidence-audit-android]] - TPM 证据审计 Android

---

## 🐛 常见问题

_暂无记录。遇到问题后会记录在 [[问题记录\|问题记录]] 中。_

**已知注意事项：**

1. **跨平台兼容性问题**
   - `npm start` 脚本使用 Windows 语法 `set NODE_ENV=development`
   - Mac/Linux 需要修改为 `export NODE_ENV=development` 或使用 `cross-env`

2. **依赖版本较老**
   - React 16、Ant Design 4、Webpack 4
   - 升级时需注意破坏性更新

3. **腾讯云 SDK**
   - 升级前查看官方迁移指南
   - 测试所有音视频、即时通讯功能

---

## 📝 开发规范

### 组件开发

1. **函数组件优先**：使用 React Hooks
2. **Props 类型定义**：使用 TypeScript 接口
3. **样式隔离**：使用 CSS Modules 或 Less

### 状态管理

1. **Redux Toolkit**：推荐使用 createSlice
2. **异步操作**：使用 Redux Thunk
3. **状态设计**：遵循范式化原则

### 代码风格

- 使用 ESLint 规则
- 提交前自动检查和修复
- 组件文件使用 PascalCase
- 工具函数使用 camelCase

---

## 📋 技术债务

- [ ] 升级 React 到 18.x
- [ ] 升级 Ant Design 到 5.x
- [ ] 迁移到 Vite 或 Webpack 5
- [ ] 完善 TypeScript 类型定义
- [ ] 添加单元测试
- [ ] 改进构建脚本跨平台支持（使用 cross-env）

---

## 📅 更新日志

| 日期 | 版本 | 描述 |
|------|------|------|
| 2026-06-16 | v0.1.0 | AI 自动补充项目文档信息 |
| 2026-06-15 | - | 创建知识库文档 |

---

## 🔖 标签

#前端 #Web端 #React-16 #Webpack #AntDesign-4 #Redux #TypeScript #腾讯云 #腾讯云IM #腾讯云TRTC #腾讯云COS #腾讯云VOD #TPM系列 #支付管理 #需要升级 #维护中

---

## 相关链接

- [[01-索引/技术栈索引\|技术栈索引]]
- [[01-索引/项目总览\|项目总览]]
- [[问题记录\|问题记录]]
