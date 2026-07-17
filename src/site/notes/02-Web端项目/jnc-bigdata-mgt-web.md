---
{"dg-publish":true,"permalink":"/02-web/jnc-bigdata-mgt-web/","dg-note-properties":{}}
---

# jnc-bigdata-mgt-web

> 数据管理平台 - 基于 UmiJS Max 4 + React 18 + Ant Design 5 构建的企业级数据管理平台

## 📋 项目信息

- **项目名称**：jnc-bigdata-mgt-web
- **项目类型**：Web 前端应用
- **开发状态**：#维护中
- **技术负责人**：dompling
- **项目路径**：`/Users/dompling/WebstormProjects/Work/jnc-bigdata-mgt-web`
- **仓库类型**：私有仓库

---

## 🚀 快速启动

```cardlink
url: /Users/dompling/WebstormProjects/Work/jnc-bigdata-mgt-web
title: 快速启动指南
description: 环境要求 & 开发命令
```

### 环境要求

- Node.js >= 16.x
- 推荐使用 pnpm（项目提交了 `pnpm-lock.yaml`）
- npm 或 pnpm 均可执行脚本

### 安装依赖

```bash
pnpm install
# 或
npm install
```

### 开发命令

| 命令 | 描述 |
|------|------|
| `npm run dev` / `pnpm dev` | 启动开发环境（develop） |
| `npm run uat` / `pnpm uat` | 启动 UAT 测试环境 |
| `npm run prod` / `pnpm prod` | 启动生产环境本地调试 |
| `npm run build` / `pnpm build` | 构建生产环境 |
| `npm run build:dev` | 构建开发环境 |
| `npm run build:uat` | 构建 UAT 环境 |
| `npm run format` | 代码格式化（Prettier） |
| `npm run openapi:big-data` | 更新 Big Data API 接口服务 |

---

## 🛠️ 技术栈

### 核心技术

| 技术 | 版本 | 说明 |
|------|------|------|
| **React** | 18 | UI 框架 |
| **UmiJS Max** | 4.6.47 | 企业级前端应用框架 |
| **TypeScript** | 5.0.3 | 类型安全 |
| **Ant Design** | 5.4.0 | UI 组件库 |
| **@ant-design/pro-components** | 2.4.4 | Pro 高级组件 |
| **ahooks** | 3.9.7 | React Hooks 工具库 |
| **lodash** | 4.17.21 | 工具函数库 |
| **dayjs** | 1.11.20 | 日期处理 |
| **react-activation** | 0.13.4 | Keep Alive 页面缓存 |
| **umi-plugin-keep-alive** | 0.0.1-beta.35 | Umi Keep Alive 插件 |

### 开发工具

- **包管理器**：pnpm（推荐）/ npm
- **代码格式化**：Prettier + prettier-plugin-organize-imports
- **Git Hooks**：Husky + lint-staged
- **环境变量管理**：cross-env
- **API 代码生成**：@umijs/openapi

---

## 📂 项目结构

```
jnc-bigdata-mgt-web/
├── config/                    # Umi 配置
│   ├── config.ts              # 主配置
│   ├── config.develop.ts      # 开发环境配置
│   ├── config.uat.ts          # UAT 环境配置
│   ├── config.product.ts      # 生产环境配置
│   ├── defaultSettings.ts     # 默认设置
│   ├── proxy.ts               # 代理配置
│   └── routes/                # 路由配置
│       └── api-gateway/       # API Gateway 路由
├── src/
│   ├── assets/                # 静态资源
│   ├── components/            # 公共组件
│   │   ├── CopyRight/         # 版权组件
│   │   ├── Guide/             # 引导组件
│   │   ├── Login/             # 登录组件
│   │   ├── ProAuth/           # 权限组件
│   │   ├── ProContainerTabs/  # 容器标签页
│   │   ├── ProTable/          # 增强表格
│   │   ├── ProTabs/           # 标签页组件
│   │   └── TableResize/       # 表格拖拽
│   ├── config/                # 配置文件
│   ├── constants/             # 常量定义
│   ├── hooks/                 # 自定义 Hooks
│   ├── layouts/               # 布局组件
│   ├── models/                # 数据模型（Umi Model）
│   ├── pages/                 # 页面组件
│   │   ├── Home/              # 首页
│   │   └── api-gateway/       # API Gateway 管理
│   │       ├── source/        # 数据源配置
│   │       ├── account/       # 调用方账号管理
│   │       ├── metadata/      # API 接口元数据管理
│   │       └── auth-grant/    # 调用权限管理
│   ├── services/              # API 服务
│   │   ├── big-data/          # 大数据平台接口（自动生成）
│   │   └── config.ts          # 服务配置
│   └── utils/                 # 工具函数
├── scripts/                   # 脚本文件
│   └── openapi/               # OpenAPI 代码生成脚本
├── package.json
├── tsconfig.json
└── README.md
```

---

## 🎯 核心功能模块

### API Gateway 数据网关

API Gateway 前端入口统一挂在 `/api-gateway` 路径下：

#### 1. 数据源配置 (`/api-gateway/source`)
- 数据源连接配置
- 数据源类型管理
- 连接测试与验证

#### 2. 调用方账号管理 (`/api-gateway/account`)
- 调用方账号注册
- 账号信息维护
- 账号状态管理

#### 3. API 接口元数据管理 (`/api-gateway/metadata`)
- API 接口定义
- 接口参数配置
- 接口版本管理
- 接口文档维护

#### 4. 调用权限管理 (`/api-gateway/auth-grant`)
- 权限授权配置
- 调用方权限分配
- 权限审批流程

#### 5. 访问审计看板 (`/api-gateway/kibana-dashboard`)
- 跳转至 Kibana Dashboard：`https://elk.jncapp.com`
- API 调用监控
- 访问日志分析

---

## 🌍 环境配置

### 环境切换

项目通过 `UMI_ENV` 环境变量切换环境：

```bash
UMI_ENV=develop    # 开发环境
UMI_ENV=uat        # UAT 测试环境
UMI_ENV=product    # 生产环境
```

### 环境变量

| 变量 | 说明 |
|------|------|
| `process.env.DOMAIN` | 前端站点域名 |
| `process.env.API` | API Gateway / 大数据平台后端网关前缀 |
| `process.env.LOGIN_PATH` | 统一登录地址 |
| `process.env.SAC_API` | 权限中心接口前缀 |
| `process.env.UMI_ENV` | 当前 Umi 环境标识 |

---

## 🔧 技术特性

### 1. Keep Alive 页面缓存
- 使用 `react-activation` 实现页面状态保持
- 配合 `umi-plugin-keep-alive` 插件
- 支持多标签页切换状态保留

### 2. Pro Components 增强组件
- ProTable：增强表格组件
- ProContainerTabs：容器标签页
- ProAuth：权限控制组件

### 3. OpenAPI 自动生成
- 通过 `@umijs/openapi` 自动生成 API 服务代码
- 自动生成 TypeScript 类型定义
- 命令：`npm run openapi:big-data`

### 4. 代码质量保障
- Husky + lint-staged：提交前自动格式化
- Prettier：统一代码风格
- TypeScript 严格模式：类型安全

---

## 📦 相关文档

- [UmiJS 官方文档](https://umijs.org/)
- [Ant Design 官方文档](https://ant.design/)
- [Ant Design Pro Components 文档](https://procomponents.ant.design/)
- [React 官方文档](https://react.dev/)
- [TypeScript 官方文档](https://www.typescriptlang.org/)

---

## 🔗 相关项目

- [[02-Web端项目/jnc-report-web\|jnc-report-web]] - 报表系统
- [[02-Web端项目/andromeda-web\|andromeda-web]] - 待补充关联

---

## 📅 更新日志

| 日期 | 版本 | 描述 |
|------|------|------|
| 2026-06-16 | - | 完善项目文档，补充技术栈、项目结构、功能模块详情 |
| 2026-06-15 | - | 创建知识库文档 |

---

## 🔖 标签

#前端 #Web端 #React-18 #UmiJS-Max #UmiJS-4 #AntDesign-5 #AntDesignPro #TypeScript #大数据 #数据管理 #API网关 #企业级应用 #维护中

---

## 相关链接

- [[01-索引/技术栈索引\|技术栈索引]]
- [[01-索引/项目总览\|项目总览]]
- [[01-索引/React项目规范\|React项目规范]]
- [[01-索引/Umi项目开发指南\|Umi项目开发指南]]
