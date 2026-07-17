---
{"dg-publish":true,"permalink":"/02-web/jnc-security-sac-frontend/","dg-note-properties":{}}
---

# jnc-security-sac-frontend

> SAC 权限管理系统前端 - 基于 UmiJS 3.x + Ant Design Pro 的企业级权限管理平台

---
## 文档地址

https://api-sac-dev.jncapp.cn/bigdata-auth-service/doc.html#/2.X%E7%89%88%E6%9C%AC/%E5%B2%97%E4%BD%8D%E7%BB%84%E7%9B%B8%E5%85%B3%E6%8E%A5%E5%8F%A3/pageRoleUsingPOST_1

## ⚡ 快速启动

```bash
# Node 版本
Node 10.x+（推荐 Node 14/16）

# 安装依赖
npm install

# 启动开发服务器（开发环境）
npm run start:dev
# 或
npm run dev

# 其他环境启动
npm run start         # 默认开发环境
npm run start:test    # 测试环境
npm run start:pre     # 预生产环境
npm run start:no-mock # 无 Mock 数据模式

# 构建项目
npm run build         # 生产构建
```

**开发地址：** 本地开发模式，UmiJS 自动打开浏览器

**其他常用命令：**
- 代码检查：`npm run lint`
- 代码修复：`npm run lint:fix`
- 代码格式化：`npm run prettier`
- 测试：`npm test`
- TypeScript 检查：`npm run tsc`

---

## 📋 项目信息

- **项目名称**：jnc-security-sac-frontend
- **项目类型**：Web 前端应用
- **开发状态**：#维护中
- **仓库地址**：`https://gitlab.jncapp.cn/sac/jnc-security-sac-frontend.git`
- **项目路径**：`/Users/dompling/WebstormProjects/Work/jnc-security-sac-frontend`

---

## 🛠️ 技术栈

### 核心技术

- **框架**：UmiJS 3.5.0 + React 17.x
- **UI 库**：Ant Design 4.24.0 + Ant Design Pro Components
- **状态管理**：Dva (UmiJS 内置)
- **路由**：UmiJS 路由系统（约定式 + 配置式）
- **语言**：TypeScript 4.2.2
- **构建工具**：UmiJS (Webpack 5)
- **包管理**：npm

### 主要依赖

**Ant Design Pro 组件：**
- `@ant-design/pro-table` 2.30.8 - 高级表格组件
- `@ant-design/pro-form` 1.62.1 - 高级表单组件
- `@ant-design/pro-layout` 6.15.3 - 页面布局组件
- `@ant-design/pro-descriptions` 1.6.8 - 描述列表组件
- `@ant-design/charts` 1.2.2 - 图表组件库
- `@ant-design/icons` 4.5.0 - 图标库

**工具库：**
- `lodash` 4.17.11 - JavaScript 工具函数库
- `moment` 2.25.3 - 时间处理库
- `classnames` 2.2.6 - CSS 类名处理
- `react-color` 2.19.3 - 颜色选择器
- `react-infinite-scroller` 1.2.4 - 无限滚动组件
- `@dnd-kit/core` 3.1.1 - 拖拽功能库

**UmiJS 插件：**
- `umi-plugin-keep-alive` 0.0.1-beta.31 - 页面缓存插件
- `@umijs/plugin-esbuild` - ESBuild 编译插件

**开发工具：**
- `cross-env` 7.0.0 - 跨平台环境变量设置
- `prettier` 2.3.2 - 代码格式化
- `eslint` 7.1.0 - 代码检查
- `stylelint` 13.0.0 - 样式检查
- `lint-staged` 10.0.0 - Git 暂存文件检查
- `mockjs` 1.0.1-beta3 - Mock 数据

---

## 📂 项目结构

```text
jnc-security-sac-frontend/
├── config/                  # UmiJS 配置
│   ├── config.ts           # 主配置文件
│   ├── config.dev.ts       # 开发环境配置
│   ├── routes.ts           # 路由配置
│   ├── proxy.ts            # 代理配置
│   ├── defaultSettings.ts  # 默认设置
│   └── oneapi.json         # OpenAPI 配置
├── mock/                    # Mock 数据
├── nginx/                   # Nginx 配置
├── public/                  # 静态资源
│   └── icons/              # 图标资源
├── src/
│   ├── assets/             # 静态资源
│   ├── components/         # 公共组件
│   │   ├── Droppable/      # 拖拽组件
│   │   ├── Footer/         # 页脚组件
│   │   ├── HeaderSearch/   # 头部搜索
│   │   ├── LogCompnents/   # 日志组件
│   │   ├── NoticeIcon/     # 通知图标
│   │   ├── RightContent/   # 右侧内容
│   │   ├── SearchSelect/   # 搜索选择器
│   │   ├── SearchTableTransfer/ # 表格穿梭框
│   │   └── TableTransform/ # 表格转换
│   ├── e2e/                # E2E 测试
│   ├── layout/             # 布局组件
│   ├── models/             # 全局数据模型（Dva）
│   ├── pages/              # 页面组件
│   │   ├── home/           # 首页
│   │   ├── user/           # 用户管理
│   │   │   ├── account/    # 账号管理
│   │   │   ├── group/      # 用户组管理
│   │   │   └── login/      # 登录页
│   │   ├── baseSetting/    # 基础设置
│   │   │   ├── DataDictionary/ # 数据字典
│   │   │   └── PostBackup/ # 岗位备份
│   │   ├── dataAuthManager/ # 数据权限管理
│   │   │   ├── AutoRelate/  # 自动关联
│   │   │   ├── DataAuthConfig/ # 数据权限配置
│   │   │   ├── OfficeGroup/ # 组织分组
│   │   │   └── PostGroupAssociation/ # 岗位分组关联
│   │   ├── systemAuthManager/ # 系统权限管理
│   │   │   ├── Client/      # 客户端管理
│   │   │   ├── RedisSync/   # Redis 同步
│   │   │   ├── ResourceRegister/ # 资源注册
│   │   │   ├── ResourceRegister2/ # 资源注册2
│   │   │   ├── Roles/       # 角色管理
│   │   │   └── RolesAuth/   # 角色权限
│   │   └── bigDataAuthManager/ # 大数据权限管理
│   │       ├── MenuRegister/ # 菜单注册
│   │       ├── Roles/       # 角色管理
│   │       └── reportConfig/ # 报表配置
│   ├── services/           # API 服务
│   │   ├── api.d.ts        # API 类型定义
│   │   └── config.ts       # 服务配置
│   ├── utils/              # 工具函数
│   └── .umi/               # UmiJS 临时文件
├── tests/                   # 测试文件
├── .eslintrc.js            # ESLint 配置
├── .prettierrc             # Prettier 配置
├── .stylelintrc            # Stylelint 配置
├── tsconfig.json           # TypeScript 配置
└── package.json
```

---

## 🎯 核心功能模块

### 1. 用户管理
- **账号管理**：用户账号的增删改查、状态管理
- **用户组管理**：用户组织架构、分组管理
- **登录日志**：用户登录历史记录

### 2. 系统权限管理
- **资源注册**：系统资源（菜单、按钮、接口）的注册与管理
- **客户端管理**：OAuth 客户端配置管理
- **角色管理**：系统角色的创建与维护
- **角色权限**：角色与资源的关联配置
- **Redis 同步**：权限数据缓存同步

### 3. 数据权限管理
- **组织分组**：组织架构的分组管理
- **数据权限配置**：数据级别的权限规则配置
- **岗位分组关联**：岗位与组织分组的关联关系
- **自动关联**：权限自动关联规则

### 4. 大数据权限管理
- **角色管理**：大数据平台角色管理
- **报表配置**：报表权限与配置
- **菜单注册**：大数据平台菜单资源注册

### 5. 基础设置
- **数据字典**：系统字典数据维护
- **岗位备份**：岗位数据备份与恢复

### 6. 权限系统特性
- 基于 RBAC（角色-权限）模型
- 支持菜单级、按钮级、数据级权限控制
- 动态菜单加载
- 权限路由守卫（`normalRouteFilter`）
- 多系统权限集成（系统权限 + 大数据权限）

---

## 🔧 配置说明

### UmiJS 配置

**主要特性：**
- Hash 路由模式
- Dva 状态管理（HMR 热更新）
- 动态导入（代码分割）
- Ant Design Pro Layout
- Webpack 5 构建
- MFSU 编译加速
- IE 11 兼容

**主题配置：**
```typescript
{
  title: '权限管理系统',
  primaryColor: '#1890ff',  // 主色调
  layout: {
    siderWidth: 208,        // 侧边栏宽度
    locale: false           // 关闭国际化
  }
}
```

**环境变量配置：**
- `REACT_APP_ENV=dev` - 开发环境
- `REACT_APP_ENV=test` - 测试环境
- `REACT_APP_ENV=pre` - 预生产环境
- `MOCK=none` - 禁用 Mock 数据

### 代码规范

- **ESLint**：代码质量检查（基于 UmiJS Fabric）
- **Prettier**：代码格式化
- **Stylelint**：Less 样式检查
- **lint-staged**：提交前自动检查和格式化
- **TypeScript**：严格类型检查

---

## 🌍 多环境管理

**环境配置：**
- 开发环境：`config/config.dev.ts` + `proxy.ts`
- 通过 `REACT_APP_ENV` 环境变量切换

**启动方式：**
```bash
# 开发环境（使用代理）
npm run start:dev

# 测试环境
npm run start:test

# 预生产环境
npm run start:pre

# 无 Mock 模式
npm run start:no-mock
```

---

## 🔗 相关项目

- [[待建档项目索引#SAC 权限系统后端\|SAC 权限系统后端]] - SAC 权限管理系统后端 API
- [[待建档项目索引#大数据权限平台\|大数据权限平台]] - 大数据平台权限管理
- [[待建档项目索引#统一认证中心\|统一认证中心]] - SSO 单点登录服务

---

## 🐛 常见问题

_暂无记录。遇到问题后会记录在 [[问题记录\|问题记录]] 中。_

---

## 📝 开发规范

### 页面开发

1. **配置式路由**：在 `config/routes.ts` 中配置路由
2. **使用 Pro 组件**：优先使用 Ant Design Pro Components
3. **数据流管理**：使用 Dva model 管理全局状态
4. **权限控制**：使用 `access: 'normalRouteFilter'` 进行路由权限控制

### 组件开发

- 公共组件放在 `src/components/` 目录
- 页面级组件放在对应的 `pages/` 子目录
- 组件使用函数组件 + Hooks（React 17）
- 拖拽功能使用 `@dnd-kit/core`

### API 服务

- API 服务配置在 `src/services/` 目录
- 使用 UmiJS 的 request 进行网络请求
- 支持 OpenAPI 自动生成（配置在 `config/oneapi.json`）
- 使用代理进行跨域处理（`config/proxy.ts`）

### 代码风格

- 遵循 Ant Design Pro 官方规范
- 使用 TypeScript 类型约束
- 函数组件 + Hooks 优先
- 使用 Prettier 自动格式化
- 提交前自动 lint 检查（lint-staged）

---

## 🚀 部署说明

**Nginx 部署：**
- Nginx 配置：`nginx/` 目录
- 支持 Hash 路由模式

**构建产物：**
- 输出目录：`build/`
- Hash 文件名：开启 hash 命名
- 静态资源导出：`exportStatic: {}`

---

## 📊 项目统计

- **代码行数**：约 25,170 行（TS/TSX/JS/JSX）
- **核心页面**：20+ 个功能模块
- **公共组件**：10+ 个可复用组件
- **路由数量**：30+ 个路由配置

---

## 📅 更新日志

| 日期 | 版本 | 描述 |
|------|------|------|
| 2026-06-16 | - | AI 自动生成完整项目文档 |
| 2025-10-30 | - | 更新 config.ts 配置 |
| 2023-08-03 | - | 更新默认设置 |

---

## 🔖 标签

#前端 #Web端 #React-17 #UmiJS-3 #AntDesign-4 #AntDesignPro #TypeScript #权限管理系统 #SAC #企业级应用 #RBAC #Dva #维护中

---

## 相关链接

- [[01-索引/技术栈索引\|技术栈索引]]
- [[01-索引/项目总览\|项目总览]]
- [[问题记录\|问题记录]]
- [UmiJS 3 官方文档](https://v3.umijs.org/)
- [Ant Design 4 官方文档](https://4x.ant.design/)
- [Ant Design Pro 官方文档](https://pro.ant.design/)
