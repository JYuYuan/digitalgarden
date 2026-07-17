---
{"dg-publish":true,"permalink":"/02-web/jnc-audit-web/","dg-note-properties":{}}
---

# jnc-audit-web

> 剑南春稽核系统 Web 端 - 基于 UmiJS 的企业级应用

---

## ⚡ 快速启动

```bash
# Node 版本
Node 10.x+（推荐 Node 16）

# 安装依赖
npm install

# 启动开发服务器（开发环境）
npm run start:dev
# 端口：3100

# 其他环境启动
npm run start:test  # 测试环境
npm run start:pre   # 预生产环境
npm run start       # 默认启动（端口 3100）
```

**访问地址：** `http://localhost:3100`

**其他常用命令：**
- 构建：`npm run build`
- 代码检查：`npm run lint`
- 代码修复：`npm run lint:fix`
- 类型检查：`npm run tsc`
- 运行测试：`npm test`

---

## 📋 项目信息

- **项目名称**：jnc-audit-web (内部名: ant-design-pro)
- **项目类型**：Web 前端应用
- **开发状态**：#维护中
- **版本**：v5.0.0-beta.0
- **项目路径**：`/Users/dompling/WebstormProjects/Work/jnc-audit-web`
- **系统名称**：剑南春稽核系统

---

## 🛠️ 技术栈

### 核心技术

- **框架**：UmiJS 3.5.0 + React 16.8.6
- **UI 库**：Ant Design 4.24.7 + Ant Design Pro 组件
- **状态管理**：Dva (UmiJS 内置) + UmiJS Model
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

**文件处理：**
- `cos-js-sdk-v5` 1.3.9 - 腾讯云对象存储 COS
- `aws-sdk` 2.940.0 - AWS SDK（可能用于 S3）
- `xlsx` 0.18.5 - Excel 处理
- `js-export-excel` 1.1.4 - Excel 导出

**工具库：**
- `lodash` 4.17.11 - 工具函数库
- `moment` 2.29.1 - 时间处理
- `qs` 6.9.0 - 查询字符串处理
- `umi-request` 1.0.8 - HTTP 请求库
- `@umijs/hooks` 1.9.3 - React Hooks 库
- `rxjs` 7.1.0 - 响应式编程

**代码编辑器：**
- `jsoneditor` 9.10.2 - JSON 编辑器
- `react-json-editor-ajrm` 2.5.14 - React JSON 编辑器

**其他：**
- `crypto-js` 4.1.1 - 加密库
- `swiper` 7.2.0 - 轮播组件
- `react-viewer` 3.2.2 - 图片查看器
- `react-activation` 0.11.2 - 页面缓存
- `umi-plugin-keep-alive` 0.0.1-beta.31 - 路由缓存
- `@dnd-kit/core` 5.0.1 - 拖拽功能
- `@dnd-kit/sortable` 6.0.0 - 拖拽排序

---

## 📂 项目结构

```text
jnc-audit-web/
├── config/              # UmiJS 配置
│   ├── config.ts       # 主配置文件
│   ├── routes/         # 路由配置
│   ├── defaultSettings.ts  # 默认配置
│   └── proxy.ts        # 代理配置
├── public/              # 静态资源
├── src/
│   ├── assets/          # 资源文件
│   ├── components/      # 公共组件
│   │   ├── Business/           # 业务组件
│   │   ├── FormComponent/      # 表单组件
│   │   ├── ProExcel/           # Excel 组件
│   │   ├── ProUploadTable/     # 上传表格
│   │   ├── SettlementTable/    # 结算表格
│   │   ├── TPMProExcel/        # TPM Excel 组件
│   │   ├── VideoAndImg/        # 视频图片组件
│   │   └── ...                 # 其他公共组件
│   ├── config/          # 配置文件
│   ├── layouts/         # 布局组件
│   ├── models/          # 数据模型（UmiJS 数据流）
│   ├── pages/           # 页面组件
│   │   ├── ActivityCenter/     # 活动中心
│   │   ├── ViolationManager/   # 违规管理
│   │   ├── TaskManager/        # 任务管理
│   │   ├── DataReport/         # 数据报表
│   │   ├── DataSearch/         # 数据查询
│   │   ├── SystemManager/      # 系统管理
│   │   ├── AdministrationManager/  # 行政管理
│   │   ├── BasePage/           # 基础页面
│   │   ├── user/               # 用户相关
│   │   └── Welcome.tsx         # 欢迎页
│   ├── services/        # API 服务
│   │   ├── audit-service/      # 稽核服务
│   │   ├── tpm-banquet-activity-service/  # TPM 宴席活动服务
│   │   ├── tpm-complain-center-sevice/    # TPM 投诉中心服务
│   │   ├── tpm-policy-center-service/     # TPM 政策中心服务
│   │   └── common/             # 公共服务
│   ├── utils/           # 工具函数
│   ├── app.tsx          # 运行时配置
│   └── global.less      # 全局样式
├── tests/               # 测试文件
├── .eslintrc.js         # ESLint 配置
├── .stylelintrc.js      # Stylelint 配置
├── jest.config.js       # Jest 配置
└── package.json
```

---

## 🎯 核心功能模块

### 1. 活动中心 (ActivityCenter)
- 活动管理 (ActivityManage) - 活动创建、编辑、查看
- 推送配置 (PushConfig) - 接口配置、公司列表、配置编辑
- 字典管理 (DictionaryManage) - 字典维护
- 规则管理 (RuleManage) - 业绩列表、逾期列表

### 2. 违规管理 (ViolationManager)
- 违规类型 (ViolationType) - 违规类型定义
- 违规规则 (ViolationRule) - 违规规则配置
- 违规汇总 (ViolationSummarize) - 违规数据汇总
- 违规通知 (ViolationNotification) - 违规通知管理

### 3. 任务管理 (TaskManager)
- 任务列表 (TaskList) - 任务查看管理
- 任务池 (TaskPool) - 任务分配池
- 任务导入 (TaskImport) - 批量导入任务
- 任务审核 (TaskExamine) - 任务审批
- 申诉管理 (AppealManage) - 申诉处理
- 任务申诉 (TaskAppeal) - 任务申诉提交
- 执行列表 (ExecutionList) - 任务执行跟踪
- 归档 (Archive) - 任务归档

### 4. 数据报表 (DataReport)
- VIP 列表 (VipList) - VIP 数据统计
- 执行列表 (ExecutionList) - 执行数据报表
- 活动列表 (ActivityList) - 活动数据统计
- 投诉列表 (ComplainList) - 投诉数据分析
- 申请列表 (ApplyList) - 申请数据汇总
- 礼品列表 (GiftList) - 礼品发放统计

### 5. 数据查询 (DataSearch)
- 多维度数据查询
- 数据导出功能

### 6. 系统管理 (SystemManager)
- 系统配置
- 权限管理
- 用户管理

### 7. 行政管理 (AdministrationManager)
- 行政事务管理

---

## 🔧 配置说明

### UmiJS 配置

**特性：**
- 约定式路由
- Dva 状态管理
- 插件化架构
- 按需加载
- Keep-Alive 路由缓存

**环境变量：**
- `REACT_APP_ENV` - 运行环境（dev/test/pre）
- `PORT` - 开发服务器端口（默认 3100）
- `MOCK` - Mock 数据开关

**布局配置：**
- 系统名称：剑南春稽核系统
- 使用 Ant Design Pro Layout

### 代码规范

- ESLint：基于 `@umijs/fabric`
- Prettier：代码格式化
- Stylelint：样式检查（Less）
- lint-staged：提交前检查

---

## 🌍 环境配置

**多环境支持：**
- `start:dev` - 开发环境
- `start:test` - 测试环境
- `start:pre` - 预生产环境
- `start` - 默认启动（端口 3100）

---

## 🔗 相关项目

- [[02-Web端项目/jnc-tpm-web\|jnc-tpm-web]] - 剑南春 TPM Web 系统
- [[03-小程序项目/jnc-audit-wx\|jnc-audit-wx]] - 审计微信小程序
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
4. **页面缓存**：使用 react-activation 和 umi-plugin-keep-alive

### 代码风格

- 遵循 UmiJS 官方规范
- 使用 TypeScript 严格模式
- 函数组件 + Hooks
- 提交前自动检查（lint-staged）

### 组件开发

- 业务组件放在 `src/components/Business`
- 通用组件独立目录
- 表单组件使用 ProForm
- 表格组件使用 ProTable

---

## 📅 更新日志

| 日期 | 版本 | 描述 |
|------|------|------|
| 2026-06-16 | v5.0.0-beta.0 | AI 自动补充完整项目文档信息 |
| 2026-06-15 | - | 创建知识库文档 |

---

## 🔖 标签

#前端 #Web端 #React-16 #UmiJS #AntDesign-4 #AntDesignPro #TypeScript #腾讯云COS #审计系列 #稽核系统 #违规管理 #任务管理 #需要升级 #维护中

---

## 相关链接

- [[01-索引/技术栈索引\|技术栈索引]]
- [[01-索引/项目总览\|项目总览]]
- [[问题记录\|问题记录]]
- [UmiJS 官方文档](https://umijs.org/)
- [Ant Design Pro 官方文档](https://pro.ant.design/)
