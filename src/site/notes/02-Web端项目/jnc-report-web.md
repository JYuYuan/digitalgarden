---
{"dg-publish":true,"permalink":"/02-web/jnc-report-web/","dg-note-properties":{}}
---

# jnc-report-web

> 客情报表系统 - 基于 UmiJS Max 4 + React 18 + Ant Design 5 + AntV 数据可视化的企业级报表分析平台

## 📋 项目信息

- **项目名称**：jnc-report-web
- **项目类型**：Web 前端应用
- **业务领域**：客情报表分析、数据可视化
- **开发状态**：#维护中
- **技术负责人**：dompling
- **项目路径**：`/Users/dompling/WebstormProjects/Work/jnc-report-web`
- **仓库类型**：私有仓库

---

## 🚀 快速启动

```cardlink
url: /Users/dompling/WebstormProjects/Work/jnc-report-web
title: 快速启动指南
description: 环境要求 & 开发命令
```

### 环境要求

- Node.js >= 16.14.2（Jenkinsfile 指定版本）
- 推荐使用 yarn（项目提交了 `yarn.lock`）
- npm 或 yarn 均可执行脚本

### 安装依赖

```bash
yarn install
# 或
npm install
```

### 开发命令

| 命令 | 描述 |
|------|------|
| `npm start` / `yarn start` | 启动开发环境（develop） |
| `npm run dev` / `yarn dev` | 启动开发环境（同 start） |
| `npm run uat` / `yarn uat` | 启动 UAT 测试环境 |
| `npm run build` / `yarn build` | 构建生产环境 |
| `npm run build:dev` | 构建开发环境（带 develop 配置） |
| `npm run build:uat` | 构建 UAT 测试环境 |
| `npm run format` | 代码格式化（Prettier） |
| `npm run setup` / `yarn setup` | UmiJS Max 初始化设置 |

---

## 🛠️ 技术栈

### 核心框架

| 技术 | 版本 | 说明 |
|------|------|------|
| React | 18.x | UI 框架 |
| UmiJS Max |
{ #4}
.4.6 | 企业级前端框架 |
| Ant Design |
{ #5}
.4.0 | UI 组件库 |
| TypeScript |
{ #5}
.0.3 | 类型系统 |
| Less | - | CSS 预处理器 |

### 数据可视化

| 技术 | 版本 | 说明 |
|------|------|------|
| @ant-design/charts | 1.4.3 | Ant Design 图表库 |
| @antv/g2 |
{ #5}
.3.0 | 蚂蚁数据可视化引擎 |
| @antv/s2 |
{ #2}
.3.1 | 多维交叉分析表格 |
| @antv/s2-react |
{ #2}
.2.0 | S2 React 适配层 |

### 路由与状态管理

| 技术 | 说明 |
|------|------|
| UmiJS Model | 基于 hooks 的轻量级状态管理 |
| UmiJS Layout | Pro Layout 布局管理 |
| UmiJS Request | 网络请求封装 |
| react-activation | 页面缓存 / Keep Alive |
| umi-plugin-keep-alive | UmiJS 页面保活插件 |

### UI 增强

| 技术 | 版本 | 说明 |
|------|------|------|
| @ant-design/pro-components |
{ #2}
.4.4 | ProTable/ProForm 等高级组件 |
| framer-motion |
{ #12}
.7.2 | React 动画库 |
| rc-queue-anim |
{ #2}
.0.0 | 列表动画 |
| rc-tween-one |
{ #3}
.0.6 | 单元素动画 |
| react-resizable |
{ #3}
.0.5 | 可调整大小组件 |
| react-viewer |
{ #3}
.2.2 | 图片查看器 |

### 开发工具

| 技术 | 说明 |
|------|------|
| Prettier | 代码格式化 |
| ESLint | 代码规范检查 |
| Stylelint | 样式规范检查 |
| Husky | Git Hooks 管理 |
| lint-staged | 提交前代码检查 |
| cross-env | 跨平台环境变量 |

---

## 📁 项目结构

```
jnc-report-web/
├── build/                    # 构建输出目录
├── config/                   # 配置文件
│   ├── config.ts            # UmiJS 主配置
│   ├── config.develop.ts    # 开发环境配置
│   ├── config.uat.ts        # UAT 环境配置
│   ├── config.product.ts    # 生产环境配置
│   ├── defaultSettings.ts   # 默认布局设置
│   └── routes/              # 路由配置
│       ├── index.ts         # 路由入口
│       ├── login.ts         # 登录路由
│       └── ActivityAnalysis/ # 客情分析路由
├── mock/                    # Mock 数据
├── nginx/                   # Nginx 配置
├── public/                  # 静态资源
├── src/
│   ├── .umi/               # UmiJS 运行时生成文件
│   ├── components/         # 公共组件
│   │   ├── CopyRight/      # 版权信息
│   │   ├── Guide/          # 引导组件
│   │   ├── Login/          # 登录组件
│   │   ├── PictureCard/    # 图片卡片
│   │   ├── ProCard/        # Pro 卡片
│   │   ├── ProCommonExcel/ # 通用 Excel 导出
│   │   ├── ProContainerTabs/ # 容器标签页
│   │   ├── ProEmpty/       # 空状态
│   │   ├── ProScroll/      # 滚动容器
│   │   ├── ProTable/       # Pro 表格
│   │   ├── RedirectLink/   # 重定向链接
│   │   ├── TableResize/    # 可调整表格
│   │   └── TipsContent/    # 提示内容
│   ├── constants/          # 常量定义
│   ├── context/            # React Context
│   ├── layouts/            # 布局组件
│   ├── models/             # 数据模型（UmiJS Model）
│   ├── pages/              # 页面组件
│   │   ├── Home/           # 首页
│   │   ├── components/     # 页面级公共组件
│   │   └── ActivityAnalysis/ # 客情分析模块
│   │       └── CustomerSentimentReport/ # 客情报表
│   │           ├── OverviewReport/      # 客情概览报表
│   │           ├── ProgressReport/      # 客情进展报表
│   │           ├── GrievanceAdjust/     # 客情申诉调差报表
│   │           ├── ValidityReport/      # 客情时效报表
│   │           └── DetailedReport/      # 明细报表
│   │               ├── ApplyDetailed/   # 报备明细
│   │               ├── ExecutionDetailed/ # 执行明细
│   │               └── BillDetailed/    # 账单明细
│   ├── services/           # API 服务
│   │   ├── api.ts          # API 接口定义
│   │   └── config.ts       # 请求配置
│   ├── utils/              # 工具函数
│   │   └── requestRules/   # 请求规则
│   ├── app.tsx             # 运行时配置
│   ├── access.ts           # 权限配置
│   ├── global.less         # 全局样式
│   ├── loading.tsx         # 加载组件
│   ├── 404.tsx             # 404 页面
│   └── typings.d.ts        # 类型定义
├── .env                     # 环境变量
├── .eslintrc.js            # ESLint 配置
├── .gitignore              # Git 忽略文件
├── .prettierrc             # Prettier 配置
├── .prettierignore         # Prettier 忽略文件
├── .stylelintrc.js         # Stylelint 配置
├── .lintstagedrc           # lint-staged 配置
├── .npmrc                  # NPM 配置
├── Jenkinsfile             # Jenkins CI/CD 配置
├── package.json            # 项目依赖
├── tsconfig.json           # TypeScript 配置
├── typings.d.ts            # 全局类型定义
└── yarn.lock               # Yarn 锁文件
```

---

## 🎯 核心功能模块

### 1. 首页 Dashboard
- 路径：`/home`
- 组件：`src/pages/Home`
- 图标：`dashboard`

### 2. 客情报表分析（ActivityAnalysis）

#### 2.1 客情报表（Customer Sentiment Report）

**概览维度：**
- **客情概览报表**：`/activity_analysis/customer_sentiment_report/overview_report`
- **客情进展报表**：`/activity_analysis/customer_sentiment_report/progress_report`
- **客情申诉调差报表**：`/activity_analysis/customer_sentiment_report/grievance_adjust`
- **客情时效报表**：`/activity_analysis/customer_sentiment_report/validity_report`

**明细维度：**
- **报备明细**：`/activity_analysis/customer_sentiment_detailed_report/apply_detailed`
- **执行明细**：`/activity_analysis/customer_sentiment_detailed_report/execution_detailed`
- **账单明细**：`/activity_analysis/customer_sentiment_detailed_report/bill_detailed`

---

## 🏗️ 架构特性

### 1. UmiJS Max 企业级特性
- **约定式路由**：基于文件系统的路由自动生成
- **Layout 布局**：ProLayout 集成，支持侧边栏导航
- **权限管理**：基于 `access.ts` 的权限控制
- **数据流**：基于 hooks 的数据流方案
- **请求封装**：统一的请求拦截与错误处理

### 2. 多环境配置
- **开发环境（develop）**：`config.develop.ts`
  - API: `https://api-bigdata-dev.jncapp.cn`
  - 域名: `https://bigdata-dev.jncapp.cn`
  - 登录: `https://password-dev.jncapp.cn`
- **UAT 环境**：`config.uat.ts`
- **生产环境**：`config.product.ts`

### 3. 主题定制
- 主题色：`#8AA2DE`（柔和蓝紫色）
- 布局模式：Mix（侧边栏 + 顶部导航混合）
- 固定头部：启用
- 侧边栏宽度：200px

### 4. 页面保活（Keep Alive）
- 使用 `umi-plugin-keep-alive` 插件
- 使用 `react-activation` 库
- 支持页面缓存，提升用户体验

### 5. 代码分割与性能优化
- `jsStrategy: 'granularChunks'`：细粒度代码分割
- `hash: true`：文件名哈希，支持长期缓存
- `esbuildMinifyIIFE: true`：IIFE 包裹压缩

---

## 📊 数据可视化能力

### AntV 生态集成
1. **G2 图表引擎**：折线图、柱状图、饼图等基础图表
2. **S2 多维表格**：支持透视表、明细表、多维交叉分析
3. **Ant Design Charts**：开箱即用的图表组件

### 自定义图表组件
- 位置：`src/pages/components/Chart`
- 支持动态配置、主题适配、交互响应

---

## 🔧 自定义组件库

### ProTable（增强表格）
- 基于 Ant Design ProTable 二次封装
- 集成 `react-resizable` 支持列宽拖拽
- 支持虚拟滚动、列固定、自定义渲染

### ProContainerTabs（容器标签页）
- 支持多标签页切换
- 与 Keep Alive 配合实现页面缓存

### ProCommonExcel（通用 Excel 导出）
- 封装 Excel 导出逻辑
- 支持多 Sheet、样式定制

### ProEmpty（空状态）
- 统一的空状态展示
- 支持自定义图标、文案、操作按钮

### RedirectLink（重定向链接）
- 处理跨系统跳转
- 统一鉴权逻辑

---

## 🚀 CI/CD

### Jenkins Pipeline
- **Pipeline 库**：`shared-pipeline-library`
- **Node 版本**：16.14.2
- **K8s 部署**：
  - 命名空间：`bigdata-dev`
  - 应用名称：`jnc-report-web`
  - 副本数：1
- **功能分支**：`dev`
- **构建脚本**：`build:dev`

---

## 📝 开发规范

### 代码质量
- **ESLint**：代码规范检查
- **Prettier**：自动格式化
- **Stylelint**：样式规范
- **Husky + lint-staged**：提交前自动检查

### 组件规范
- 函数式组件 + React Hooks
- TypeScript 严格模式
- ProComponents 优先

### 命名规范
- 组件文件：PascalCase（如 `ProTable.tsx`）
- 工具函数：camelCase（如 `formatDate.ts`）
- 常量：UPPER_SNAKE_CASE（如 `API_BASE_URL`）

---

## 🔗 关联项目

- [[02-Web端项目/jnc-bigdata-mgt-web\|jnc-bigdata-mgt-web]] - 数据管理平台（共享 API 基础设施）
- [[02-Web端项目/jnc-audit-web\|jnc-audit-web]] - 审计系统

---

## 📌 标签

#前端 #Web端 #React-18 #UmiJS-Max #UmiJS-4 #AntDesign-5 #AntDesignPro #TypeScript #AntV #数据可视化 #报表系统 #客情分析 #企业级应用 #维护中

---

## 📅 最后更新

- **文档创建时间**：2026-06-15
- **最后修改时间**：2026-06-16
- **文档维护者**：Claude Code

---

## 💡 备注

1. **项目亮点**：
   - 完整的客情报表分析体系（概览 → 进展 → 申诉 → 时效 → 明细）
   - AntV 生态深度集成，支持多维数据透视
   - 页面保活机制，优化用户体验
   - 多环境配置，支持 dev/uat/prod 部署

2. **技术债务**：
   - `@alita/plugins` 的 `tabs-layout` 和 `keepalive` 功能已注释，可能存在迁移需求
   - README.md 内容过于简单，需补充业务说明

3. **待完善**：
   - 单元测试覆盖率（未发现 `__tests__` 或 `.test.ts` 文件）
   - API 文档（services 仅有 2 个文件，可能需要 OpenAPI 生成）

---

## 🔍 快速查找

- **路由配置**：`config/routes/`
- **API 服务**：`src/services/`
- **公共组件**：`src/components/`
- **页面组件**：`src/pages/`
- **工具函数**：`src/utils/`
- **数据模型**：`src/models/`
