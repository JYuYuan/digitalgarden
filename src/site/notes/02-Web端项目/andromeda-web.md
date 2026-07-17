---
{"dg-publish":true,"permalink":"/02-web/andromeda-web/","dg-note-properties":{}}
---

# andromeda-web

> Andromeda Web 管理后台 - SFA 销售自动化系统

---

## ⚡ 快速启动

```bash
# Node 版本
Node 20.x

# 安装依赖
npm install

# 启动开发服务器
npm run dev

# 访问地址
http://localhost:8000  # 默认端口根据 .env.development 配置
```

**其他常用命令：**
- 构建（开发环境）：`npm run build:dev`
- 构建（测试环境）：`npm run build:test`
- 构建（生产环境）：`npm run build:pro`
- 代码检查：`npm run lint`
- 代码修复：`npm run lint:fix`
- 样式检查：`npm run stylelint`

---

## 📋 项目信息

- **项目名称**：andromeda-web
- **项目类型**：Web 前端应用
- **开发状态**：#维护中
- **版本**：v0.4.3
- **项目路径**：`/Users/dompling/WebstormProjects/Work/andromeda-web`

---

## 🛠️ 技术栈

### 核心技术

- **框架**：React 18.3.1 + Vite 5.2.12
- **UI 库**：Ant Design 4.24.12 + Ant Design 5.x（双版本共存）
- **状态管理**：Zustand 4.5.2
- **路由**：React Router DOM 6.23.1
- **语言**：TypeScript 5.4.5
- **构建工具**：Vite
- **包管理**：npm（使用 pnpm lock）

### 主要依赖

**数据请求：**
- `swr` 2.2.5 - 数据请求和缓存
- `@tanstack/react-query` 5.56.2 - 异步状态管理
- `axios` 1.7.2 - HTTP 客户端

**工具库：**
- `ahooks` 3.8.0 - React Hooks 库
- `lodash` 4.17.21 - 工具函数库
- `dayjs` 1.11.12 - 时间处理
- `number-precision` 1.6.0 - 科学计算

**业务组件：**
- `bpmn-js` 17.11.0 - 流程图编辑器
- `@wangeditor/editor` 5.1.23 - 富文本编辑器
- `form-render` + `@xrenders/schema-builder` - 动态表单
- `xlsx` + `xlsx-js-style` - Excel 导入导出

**加密和安全：**
- `crypto-js` 4.2.0 - 加密库
- `js-md5` 0.8.3 - MD5 加密
- `jsencrypt` 3.3.2 - RSA 加密

---

## 📂 项目结构

```text
andromeda-web/
├── src/
│   ├── assets/          # 静态资源文件
│   ├── components/      # 全局组件
│   ├── enums/           # 项目枚举
│   ├── hooks/           # 常用 Hooks
│   ├── layouts/         # 框架布局
│   ├── pages/           # 业务页面
│   ├── routers/         # 路由管理
│   ├── servers/         # API 接口
│   ├── stores/          # Zustand 状态管理
│   ├── typings/         # 全局 TS 类型声明
│   ├── utils/           # 工具库
│   ├── App.tsx          # 入口页面
│   └── main.tsx         # 入口文件
├── public/              # 静态资源（不打包）
├── .env                 # Vite 通用配置
├── .env.development     # 开发环境配置
├── .env.test            # 测试环境配置
├── .env.production      # 生产环境配置
├── vite.config.mts      # Vite 配置
└── package.json         # 依赖管理
```

---

## 🌍 环境配置

### 环境变量

项目使用 `.env.*` 文件管理不同环境配置：

- `.env` - 通用配置
- `.env.development` - 开发环境（默认）
- `.env.test` - 测试环境
- `.env.production` - 生产环境

**关键配置项：**
- `VITE_API_URL` - 后端 API 地址
- `VITE_JNC_URL` - 剑南春门户登录地址
- `VITE_PORT` - 开发服务器端口
- `VITE_RSA_PUBLIC_KEY` / `VITE_RSA_PRIVATE_KEY` - RSA 加密密钥

### 代理配置

开发环境配置了多个后端服务代理（见 `vite.config.mts`）：
- `/sfa` → 主 API 服务
- `/LMQ`, `/1LMQ`, `/LJ`, `/WCY`, `/LHR`, `/ZJ`, `/USERZJ` → 不同开发者后端服务

---

## 🎯 核心功能模块

- 销售自动化管理（SFA）
- 流程审批（基于 BPMN 2.0）
- 动态表单（xRender）
- 数据报表和图表
- 权限管理
- 富文本编辑
- Excel 导入导出

---

## 🔧 配置说明

### 代码规范

- **ESLint**：`eslint-config-alloy` + TypeScript 规则
- **Prettier**：统一代码格式化
- **Stylelint**：样式规范检查
- **CommitLint**：Git 提交信息规范

### Git Hooks

项目使用 Husky 配置了 Git Hooks：
- `pre-commit`：提交前执行 lint-staged（自动格式化和 lint）
- `commit-msg`：提交信息规范检查

---

## 🔗 相关项目

- [[03-小程序项目/andromeda-wx\|andromeda-wx]] - Andromeda 微信小程序

---

## 🐛 常见问题

_暂无记录。遇到问题后会记录在 [[问题记录\|问题记录]] 中。_

---

## 📅 更新日志

| 日期 | 版本 | 描述 |
|------|------|------|
| 2026-06-16 | v0.4.3 | AI 自动补充项目文档信息 |
| 2026-06-15 | - | 创建知识库文档 |

---

## 🔖 标签

#前端 #Web端 #React-18 #Vite #AntDesign-4 #AntDesign-5 #TypeScript #Zustand #Andromeda系列 #SFA销售自动化 #高优先级 #维护中

---

## 相关链接

- [[01-索引/技术栈索引\|技术栈索引]]
- [[01-索引/项目总览\|项目总览]]
- [[问题记录\|问题记录]]
