---
{"dg-publish":true,"permalink":"/02-web/oms-web/","dg-note-properties":{}}
---

# oms-web

> OMS 订单管理系统 Web 端 - 基于 UmiJS Max 的企业级应用

---

## ⚡ 快速启动

```bash
# Node 版本
Node 16.x+（推荐 Node 18）

# 安装依赖
yarn install
# 或
npm install

# 启动开发服务器（本地环境）
npm run dev
# 或
npm run start

# 其他环境构建
npm run build-dev    # 开发环境构建
npm run build        # 生产环境构建
```

**开发地址：** 本地开发模式，使用 hash 路由

**其他常用命令：**
- 代码格式化：`npm run format`
- 项目设置：`npm run setup`
- Git Hooks 安装：`npm run prepare`（自动执行）

---

## 📋 项目信息

- **项目名称**：oms-web
- **项目类型**：Web 前端应用
- **开发状态**：#维护中
- **作者**：Qj <4433677805@qq.com>
- **项目路径**：`/Users/dompling/WebstormProjects/Work/oms-web`

---

## 🛠️ 技术栈

### 核心技术

- **框架**：UmiJS Max 4.2.13 + React 18.x
- **UI 库**：Ant Design 5.19.1 + Ant Design Pro Components 2.7.10
- **状态管理**：UmiJS Max 内置状态管理（Model）
- **路由**：UmiJS Max 路由系统（Hash 模式）
- **语言**：TypeScript 4.1.2
- **构建工具**：UmiJS Max (Webpack/Vite)
- **包管理**：yarn

### 主要依赖

**Ant Design Pro 组件：**
- `@ant-design/pro-components` 2.7.10 - Pro 系列高级组件集合
  - ProTable - 高级表格
  - ProForm - 高级表单
  - ProLayout - 页面布局
  - ProDescriptions - 描述列表

**UmiJS Max 特性：**
- `@umijs/max` 4.2.13 - UmiJS Max 框架
  - access - 权限管理插件
  - model - 状态管理插件
  - initialState - 初始化状态插件
  - request - 请求管理插件
  - layout - 布局插件

**工具库：**
- `lodash` 4.17.21 - JavaScript 工具函数库
- `@ant-design/icons` 4.7.0 - Ant Design 图标库
- `dayjs` - 时间处理（通过 Ant Design 5）

**开发工具：**
- `cross-env` 7.0.3 - 跨平台环境变量设置
- `husky` 8.0.1 - Git Hooks 管理
- `lint-staged` 13.0.3 - Git 暂存文件检查
- `prettier` 2.7.1 - 代码格式化
- `prettier-plugin-organize-imports` 2.x - 自动组织导入
- `prettier-plugin-packagejson` 2.x - package.json 格式化

---

## 📂 项目结构

```text
oms-web/
├── config/              # UmiJS Max 配置
│   ├── config.ts       # 主配置文件（路由、主题等）
│   ├── config.local.ts # 本地环境配置
│   ├── config.develop.ts # 开发环境配置
│   └── config.production.ts # 生产环境配置
├── mock/                # Mock 数据
├── nginx/               # Nginx 配置
├── public/              # 静态资源
│   └── favicon.ico     # 网站图标
├── src/
│   ├── components/      # 公共组件
│   │   ├── Access/      # 权限组件
│   │   ├── Table/       # 表格组件
│   │   ├── UploadModal/ # 上传模态框
│   │   ├── UseModalForm/ # 模态表单
│   │   ├── Footer/      # 页脚
│   │   └── CopyRight/   # 版权信息
│   ├── constants/       # 常量定义
│   │   └── storage.ts   # 本地存储键名
│   ├── layouts/         # 布局组件
│   │   └── bootstrap/   # 主布局
│   ├── models/          # 全局数据模型
│   ├── pages/           # 页面组件
│   │   ├── Home/        # 首页
│   │   ├── Login/       # 登录页
│   │   ├── BaseInfoManage/   # 基础信息管理
│   │   │   ├── accountManage/         # 账号管理
│   │   │   ├── warehouseInfo/         # 仓库信息
│   │   │   └── specialSprayCodingInfo/ # 特殊喷码信息
│   │   ├── OrderManage/      # 订单管理
│   │   │   ├── orderManage/  # 订单管理
│   │   │   ├── spurtCodeInfo/ # 喷码信息
│   │   │   └── batchImport/  # 批量导入
│   │   ├── OrderExecuteManage/ # 订单执行管理
│   │   │   ├── inStockManage/  # 入库管理
│   │   │   ├── outStockManage/ # 出库管理
│   │   │   └── deliveryManage/ # 配送管理
│   │   ├── DictionaryManage/  # 字典管理
│   │   │   └── blackList/     # 黑名单
│   │   └── 404/         # 404 页面
│   ├── services/        # API 服务
│   │   ├── axios.ts     # Axios 实例配置
│   │   ├── requestService.ts # 请求服务封装
│   │   ├── auth/        # 认证服务
│   │   ├── user/        # 用户服务
│   │   ├── baseInfo/    # 基础信息服务
│   │   ├── orderManage/ # 订单管理服务
│   │   ├── orderExecuteManage/ # 订单执行服务
│   │   ├── dictionaryManage/ # 字典管理服务
│   │   └── global/      # 全局服务
│   ├── utils/           # 工具函数
│   │   └── access.ts    # 权限工具
│   ├── app.tsx          # 运行时配置
│   ├── access.ts        # 权限定义
│   ├── index.less       # 全局样式
│   └── typings.d.ts     # 全局类型定义
├── .env                 # 环境变量
├── .eslintrc.js         # ESLint 配置
├── .prettierrc          # Prettier 配置
├── .prettierignore      # Prettier 忽略配置
├── .stylelintrc.js      # Stylelint 配置
├── .lintstagedrc        # lint-staged 配置
├── .gitignore           # Git 忽略配置
├── Jenkinsfile          # Jenkins 部署配置
├── tsconfig.json        # TypeScript 配置
├── typings.d.ts         # TypeScript 类型声明
└── package.json
```

---

## 🎯 核心功能模块

### 1. 基础信息管理
- **账号管理**：用户账号的增删改查
- **仓库信息**：仓库信息维护
- **特殊喷码信息**：特殊喷码规则配置

### 2. 订单管理
- **订单管理**：订单的创建、查询、详情、处理
- **喷码信息**：产品喷码信息管理
- **批量导入**：订单批量导入功能

### 3. 订单执行管理
- **入库管理**：入库单管理和详情查看
- **出库管理**：出库单管理和详情查看
- **配送管理**：配送单管理和详情查看

### 4. 字典管理
- **黑名单**：黑名单配置和管理

### 5. 权限系统
- 基于菜单的权限控制
- 按钮级别的权限管理
- 动态菜单加载
- 权限路由守卫

---

## 🔧 配置说明

### UmiJS Max 配置

**主要特性：**
- Hash 路由模式
- 代码分割策略：`granularChunks`
- JS 压缩：Terser
- CSS 压缩：cssnano
- 目标浏览器：Chrome 67+

**Ant Design 主题定制：**
```typescript
{
  colorPrimary: '#e0282e',     // 主色调（红色）
  colorInfo: '#e0282e',        // 信息色
  colorBgContainerDisabled: '#f1f1f1',  // 禁用背景色
  colorTextDisabled: '#606060' // 禁用文字色
}
```

**环境变量配置：**
- `UMI_ENV=local` - 本地开发环境
- `UMI_ENV=develop` - 开发环境
- `UMI_ENV=production` - 生产环境

**API 地址配置（本地环境）：**
- SAC_API: `https://api-sac-dev.jncapp.cn`
- OMS_API: `https://api-oms-dev.jncapp.cn`
- PASS_API: `https://password-dev.jncapp.cn`

### 代码规范

- **ESLint**：代码质量检查
- **Prettier**：代码格式化（自动导入排序）
- **Stylelint**：样式检查
- **lint-staged**：提交前自动检查和格式化
- **husky**：Git Hooks 管理

---

## 🌍 多环境管理

**环境配置文件：**
- `config/config.local.ts` - 本地开发环境
- `config/config.develop.ts` - 开发环境
- `config/config.production.ts` - 生产环境

**启动方式：**
```bash
# 本地环境
npm run dev

# 构建开发环境
npm run build-dev

# 构建生产环境
npm run build
```

---

## 🔗 相关项目

- [[待建档项目索引#OMS 后端服务\|OMS 后端服务]] - OMS 订单管理系统后端 API
- [[待建档项目索引#SAC 权限系统\|SAC 权限系统]] - 统一权限管理系统
- [[待建档项目索引#密码管理服务\|密码管理服务]] - 密码服务

---

## 🐛 常见问题

_暂无记录。遇到问题后会记录在 [[问题记录\|问题记录]] 中。_

---

## 📝 开发规范

### 页面开发

1. **配置式路由**：在 `config/config.ts` 中配置路由
2. **使用 Pro 组件**：优先使用 Ant Design Pro Components
3. **数据流管理**：使用 UmiJS Max 的 model 管理全局状态
4. **权限控制**：使用 `access` 插件和自定义权限组件

### 组件开发

- 公共组件放在 `src/components/` 目录
- 页面级组件放在对应的 `pages/` 子目录
- 组件使用函数组件 + Hooks
- 复杂表单使用 `UseModalForm` 封装

### API 服务

- API 服务按模块分类在 `src/services/` 目录
- 使用统一的 Axios 实例（`axios.ts`）
- 使用 `requestService.ts` 封装请求方法
- 统一错误处理和 loading 状态

### 代码风格

- 遵循 UmiJS Max 官方规范
- 使用 TypeScript 类型约束
- 函数组件 + Hooks 优先
- 使用 Prettier 自动格式化
- 提交前自动 lint 检查

---

## 🚀 部署说明

**Jenkins 部署：**
- 配置文件：`Jenkinsfile`
- Nginx 配置：`nginx/` 目录

**构建产物：**
- 输出目录：`dist/`
- Hash 文件名：开启 hash 命名

---

## 📊 项目统计

- **文件数量**：约 135 个 TS/TSX 文件
- **代码行数**：约 6,151 行（页面代码）
- **核心页面**：10+ 个功能模块

---

## 📅 更新日志

| 日期 | 版本 | 描述 |
|------|------|------|
| 2026-06-16 | - | AI 自动生成完整项目文档 |
| 2024-12-11 | - | 更新 Jenkinsfile 配置 |
| 2024-11-27 | - | 更新 package.json 依赖 |

---

## 🔖 标签

#前端 #Web端 #React-18 #UmiJS-Max #UmiJS-4 #AntDesign-5 #AntDesignPro #TypeScript #订单管理系统 #OMS #企业级应用 #权限系统 #维护中

---

## 相关链接

- [[01-索引/技术栈索引\|技术栈索引]]
- [[01-索引/项目总览\|项目总览]]
- [[问题记录\|问题记录]]
- [UmiJS Max 官方文档](https://umijs.org/docs/max/introduce)
- [Ant Design 5 官方文档](https://ant.design/)
- [Ant Design Pro Components](https://procomponents.ant.design/)
