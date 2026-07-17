---
{"dg-publish":true,"permalink":"/02-web/jnc-tpm-web/","dg-note-properties":{}}
---

# jnc-tpm-web

> TPM Web 端 - 基于 UmiJS 的企业级应用

---

## ⚡ 快速启动

```bash
# Node 版本
Node 10.x+（推荐 Node 16）

# 安装依赖
npm install

# 启动开发服务器（开发环境）
npm run start:dev
# 端口：3090

# 其他环境启动
npm run start:uat   # UAT 环境
npm run start:test  # 测试环境
npm run start:prod  # 生产环境
```

**访问地址：** `http://localhost:3090`

**其他常用命令：**
- 构建：`npm run build`
- 代码检查：`npm run lint`
- 代码修复：`npm run lint:fix`
- 类型检查：`npm run tsc`
- 运行测试：`npm test`

---

## 📋 项目信息

- **项目名称**：jnc-tpm-web (内部名: ant-design-pro)
- **项目类型**：Web 前端应用
- **开发状态**：#维护中
- **版本**：v5.0.0-beta.0
- **项目路径**：`/Users/dompling/WebstormProjects/Work/jnc-tpm-web`

---

## 🛠️ 技术栈

### 核心技术

- **框架**：UmiJS 3.5.0 + React 16.14.0
- **UI 库**：Ant Design 4.24.12 + Ant Design Pro 组件
- **状态管理**：UmiJS 内置状态管理 + Redux
- **路由**：UmiJS 约定式路由
- **语言**：TypeScript 4.1.2
- **构建工具**：UmiJS (Webpack)
- **包管理**：npm

### 主要依赖

**Ant Design Pro 组件：**
- `@ant-design/pro-card` 1.18.31 - 高级卡片
- `@ant-design/pro-form` 1.67.3 - 高级表单
- `@ant-design/pro-layout` 6.26.0 - 页面布局
- `@ant-design/pro-table` 3.1.0 - 高级表格
- `@ant-design/pro-descriptions` 1.9.6 - 描述列表
- `@ant-design/charts` 1.4.2 - 图表库

**腾讯云 SDK：**
- `cos-js-sdk-v5` 1.3.9 - 对象存储 COS
- `tim-js-sdk`（未在依赖中，可能通过其他方式引入）

**工具库：**
- `lodash` 4.17.11 - 工具函数库
- `moment` 2.29.1 - 时间处理
- `qs` 6.9.0 - 查询字符串处理
- `axios`（通过 umi-request）
- `ahooks` 3.7.11 - React Hooks 库
- `rxjs` 7.1.0 - 响应式编程

**地图组件：**
- `@map-component/react-tmap` 0.1.4 - 腾讯地图

**代码编辑器：**
- `ace-builds` 1.24.0 - Ace 编辑器
- `react-ace` 10.1.0 - React Ace 封装
- `jsoneditor` 9.10.2 - JSON 编辑器

**其他：**
- `xlsx` 0.18.5 - Excel 处理
- `swiper` 6.8.4 - 轮播组件
- `html2canvas` 1.4.1 - HTML 转图片
- `react-viewer` 3.2.2 - 图片查看器
- `react-to-print` 3.0.5 - 打印功能
- `crypto-js` 4.1.1 - 加密库
- `react-activation` 0.11.2 - 页面缓存
- `umi-plugin-keep-alive` 0.0.1-beta.31 - 路由缓存

---

## 📂 项目结构

```text
jnc-tpm-web/
├── config/              # UmiJS 配置
│   ├── config.ts       # 主配置文件
│   └── routes.ts       # 路由配置
├── public/              # 静态资源
├── src/
│   ├── assets/          # 资源文件
│   ├── components/      # 公共组件
│   ├── layouts/         # 布局组件
│   ├── models/          # 数据模型（UmiJS 数据流）
│   ├── pages/           # 页面组件
│   ├── services/        # API 服务
│   ├── utils/           # 工具函数
│   ├── app.tsx          # 运行时配置
│   └── global.less      # 全局样式
├── .umirc.ts            # UmiJS 配置（简单项目）
└── package.json
```

---

## 🎯 核心功能模块

### 1. TPM 管理
- 第三方支付管理
- 商户管理
- 交易监控

### 2. 数据可视化
- Ant Design Charts 图表
- 实时数据监控
- 数据报表

### 3. 文档处理
- Excel 导入导出
- 文件预览
- 打印功能

### 4. 代码编辑
- JSON 编辑器
- Ace 代码编辑器
- 语法高亮

---

## 🔧 配置说明

### UmiJS 配置

**特性：**
- 约定式路由
- 内置状态管理
- 插件化架构
- 按需加载

**环境变量：**
- `REACT_APP_ENV` - 运行环境（dev/uat/test/prod）
- `PORT` - 开发服务器端口（默认 3090）
- `MOCK` - Mock 数据开关

### 代码规范

- ESLint：基于 `@umijs/fabric`
- Prettier：代码格式化
- Stylelint：样式检查
- lint-staged：提交前检查

---

## 🌍 环境配置

**多环境支持：**
- `start:dev` - 开发环境
- `start:uat` - UAT 环境
- `start:test` - 测试环境
- `start:prod` - 生产环境

---

## 🔗 相关项目

- [[02-Web端项目/tpm-pc-manager\|tpm-pc-manager]] - TPM PC 管理系统
- [[02-Web端项目/jnc-tpm-react\|jnc-tpm-react]] - TPM React 项目
- [[03-小程序项目/tpm-evidence-audit-wxapp\|tpm-evidence-audit-wxapp]] - TPM 证据审计小程序
- [[04-移动端项目/tpm-evidence-audit-android\|tpm-evidence-audit-android]] - TPM 证据审计 Android

---

## 🐛 常见问题

_暂无记录。遇到问题后会记录在 [[问题记录\|问题记录]] 中。_

---

## 📝 开发规范

### 页面开发

1. **约定式路由**：文件结构即路由结构
2. **使用 Pro 组件**：优先使用 Ant Design Pro 组件
3. **数据流**：使用 UmiJS 的 model 管理状态

### 代码风格

- 遵循 UmiJS 官方规范
- 使用 TypeScript 严格模式
- 函数组件 + Hooks
- 提交前自动检查（lint-staged）

---

## 📅 更新日志

| 日期 | 版本 | 描述 |
|------|------|------|
| 2026-06-16 | v5.0.0-beta.0 | AI 自动补充项目文档信息 |
| 2026-06-15 | - | 创建知识库文档 |

---

## 🔖 标签

#前端 #Web端 #React-16 #UmiJS-3 #AntDesign-4 #AntDesignPro #TypeScript #腾讯云 #腾讯云COS #TPM系列 #支付管理 #需要升级 #维护中

---

## 相关链接

- [[01-索引/技术栈索引\|技术栈索引]]
- [[01-索引/项目总览\|项目总览]]
- [[问题记录\|问题记录]]
- [UmiJS 官方文档](https://umijs.org/)
- [Ant Design Pro 官方文档](https://pro.ant.design/)
