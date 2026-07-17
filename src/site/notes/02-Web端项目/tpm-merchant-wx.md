---
{"dg-publish":true,"permalink":"/02-web/tpm-merchant-wx/","dg-note-properties":{}}
---

# tpm-merchant-wx

> TPM 商家端后台管理系统 - 经销商积分池与投入规则管理平台

---

## ⚡ 快速启动

```bash
# Node 版本
Node 16.x+（推荐 Node 18）

# 安装依赖
npm install

# 开发环境启动（test 环境）
npm run start

# 生产环境启动（prod_release 环境）
npm run start:prod

# 构建测试环境
npm run build:dev

# 构建生产环境
npm run build
```

**其他常用命令：**
- 代码格式化：`npm run format`
- 项目初始化：`npm run setup`

---

## 📋 项目信息

- **项目名称**：tpm-merchant-wx（TPM 商家端后台）
- **项目类型**：React Web 应用
- **开发状态**：#维护中
- **K8s 应用名**：tpm-pc-manager-merchant
- **K8s 命名空间**：tpm-dev
- **项目路径**：`/Users/dompling/WebstormProjects/Work/tpm-merchant-wx`

---

## 🛠️ 技术栈

### 核心技术

- **框架**：Umi Max 4.0.26（基于 React 18）
- **UI 库**：Ant Design 4.23.6 + Ant Design Pro Components 2.3.24
- **语言**：TypeScript 4.1.2
- **包管理**：npm（cnpm 镜像）
- **构建工具**：Umi Max
- **CI/CD**：Jenkins + Kubernetes

### 主要依赖

**UI 组件：**
- `antd` 4.23.6 - Ant Design UI 组件库
- `@ant-design/pro-components` 2.3.24 - Ant Design Pro 高级组件
- `@ant-design/icons` 4.7.0 - Ant Design 图标库
- `@ant-design/colors` 6.0.0 - Ant Design 色彩系统

**核心框架：**
- `@umijs/max` 4.0.26 - Umi Max 框架
- `@umijs/plugin-layout` 0.18.4 - Umi Layout 插件

**工具库：**
- `moment` 2.29.4 - 时间处理

**代码规范：**
- `prettier` 2.7.1 - 代码格式化
- `prettier-plugin-organize-imports` - 自动排序导入
- `prettier-plugin-packagejson` - package.json 格式化
- `husky` 8.0.1 - Git Hooks 管理
- `lint-staged` 13.0.3 - Git 暂存文件检查

---

## 📂 项目结构

```text
tpm-merchant-wx/
├── config/                  # 配置文件
│   ├── config.ts           # Umi 主配置
│   ├── routes.ts           # 路由配置
│   ├── proxy.ts            # 代理配置
│   └── defaultSettings.ts  # 默认布局设置
├── src/                    # 源代码
│   ├── pages/              # 页面组件
│   │   ├── Home/          # 首页
│   │   ├── Login/         # 登录页
│   │   ├── Account/       # 账户管理（修改密码）
│   │   ├── Dealer/        # 经销商积分池管理
│   │   ├── Integral/      # 积分回收单管理
│   │   ├── Investment/    # 投入规则配置
│   │   └── Abnormal/      # 异常账单监控
│   ├── components/        # 公共组件
│   │   ├── Guide/         # 引导组件
│   │   ├── HeaderDropdown/# 头部下拉菜单
│   │   ├── PanelTitle/    # 面板标题
│   │   └── RightContent/  # 右侧内容（用户信息）
│   ├── services/          # API 服务层
│   │   ├── login/         # 登录服务
│   │   ├── dealer/        # 经销商服务
│   │   ├── investment/    # 投入规则服务
│   │   ├── abnormal/      # 异常监控服务
│   │   ├── config.ts      # 服务配置
│   │   └── index.ts       # 服务统一导出
│   ├── utils/             # 工具函数
│   │   ├── enum.ts        # 枚举定义
│   │   ├── format.ts      # 格式化工具
│   │   ├── request.ts     # 请求封装
│   │   └── index.ts       # 工具函数统一导出
│   ├── models/            # 数据模型（Umi Model）
│   ├── constants/         # 常量定义
│   ├── assets/            # 静态资源
│   │   └── logo.svg       # Logo
│   ├── app.tsx            # 应用入口（运行时配置）
│   ├── access.ts          # 权限控制
│   ├── loading.tsx        # 加载组件
│   └── typings.d.ts       # 类型定义
├── public/                # 公共静态资源
├── mock/                  # Mock 数据
├── nginx/                 # Nginx 配置
├── .husky/                # Git Hooks
├── Jenkinsfile            # Jenkins CI/CD 配置
├── package.json           # 项目依赖
├── tsconfig.json          # TypeScript 配置
├── .prettierrc            # Prettier 配置
├── .eslintrc.js           # ESLint 配置
├── .stylelintrc.js        # StyleLint 配置
└── README.md              # 项目说明
```

---

## 🎯 核心功能模块

### 1. 首页（Home）
- 数据概览和统计看板

### 2. 经销商积分池管理（Dealer/Integral）
- 经销商积分池查询
- 积分池余额管理
- 积分明细查看

### 3. 积分回收单管理（Integral/Recovery）
- 积分回收单列表
- 回收单创建和审批
- 回收单状态跟踪

### 4. 投入规则配置（Investment/Rules）
- 投入规则列表
- 规则创建和编辑
- 规则详情查看
- 规则启用/禁用管理

### 5. 异常账单监控（Abnormal/Dashboard）
- 异常账单统计
- 异常数据预警
- 账单异常分析（需要管理员权限）

### 6. 账户管理（Account）
- 修改密码
- 用户信息查看

---

## 🔧 配置说明

### Umi 配置（config/config.ts）

**核心功能：**
- Hash 路由模式
- Ant Design 集成
- 数据流（Model）
- 初始化状态管理
- 请求封装
- Layout 布局系统
- 国际化（中文）
- 权限控制（Access）
- 点击组件定位源码

**布局配置（defaultSettings.ts）：**
- 主题：light（亮色）
- 主色调：`#1890ff`（拂晓蓝）
- 布局模式：mix（混合布局）
- 内容宽度：Fluid（流式）
- 固定头部和侧边栏
- 标题：商家端后台

**路由配置（routes.ts）：**
- `/` - 重定向到首页
- `/login` - 登录页（无 Layout）
- `/home` - 首页
- `/account/password` - 修改密码（隐藏菜单）
- `/dealer/integral` - 经销商积分池
- `/integral/recovery` - 积分回收单
- `/investment/rules` - 投入规则配置
- `/abnormal/dashboard` - 异常账单监控（需要 admin 权限）

**代理配置（proxy.ts）：**
- `/store` 代理到开发服务器：`http://192.168.21.117:8088/`

### 环境配置

**环境变量（.env）：**
```bash
DID_YOU_KNOW=none
```

**构建环境：**
- `UMI_ENV=test` - 测试环境
- `UMI_ENV=prod_release` - 生产环境

---

## 🔐 权限控制

### 权限配置（src/access.ts）
- 通过 `initialState.currentUser.role` 判断用户角色
- 支持 admin 角色权限控制

### 路由权限
- 异常账单监控页面需要 `admin` 权限

---

## 🌐 网络请求

### 请求配置（src/app.tsx）

**请求拦截器：**
- 自动添加 Authorization Token
- 支持跳过 Token（skipToken 选项）

**响应拦截器：**
- 统一处理错误响应
- 自动跳转登录（401 / -1 错误码）
- 成功消息提示

**错误处理：**
- 网络异常提示
- 401 错误自动清除本地存储并跳转登录
- 请求超时：20 秒

---

## 🎨 UI/UX 设计

### 布局系统
- 使用 Ant Design Pro Layout
- 混合布局模式（顶部 + 侧边栏）
- 固定头部和侧边栏
- PageContainer 包裹页面内容

### 主题配置
- 亮色主题
- 拂晓蓝主色调（`#1890ff`）
- 流式内容宽度

### 右侧内容
- 用户信息展示
- 登出功能

---

## 📦 构建与部署

### Jenkins CI/CD

**配置（Jenkinsfile）：**
- 构建节点：k8s-agent-react
- K8s 命名空间：tpm-dev
- 应用名称：tpm-pc-manager-merchant
- 副本数：1
- 功能分支：dev
- 构建脚本：build:dev

**构建流程：**
1. 代码检出
2. 依赖安装（npm install）
3. 代码构建（npm run build:dev）
4. Docker 镜像构建
5. 部署到 K8s

**构建产物：**
- 输出目录：`build/`
- Hash 文件名（便于缓存）

---

## 🔗 相关项目

- [[待建档项目索引#tpm-admin-web\|tpm-admin-web]] - TPM 管理端后台
- [[待建档项目索引#tpm-dealer-web\|tpm-dealer-web]] - TPM 经销商端

---

## 🐛 常见问题

_暂无记录。遇到问题后会记录在 [[问题记录\|问题记录]] 中。_

---

## 📝 开发规范

### 目录规范

1. **页面组件**：统一放在 `src/pages/` 目录
2. **公共组件**：统一放在 `src/components/` 目录
3. **服务层**：统一放在 `src/services/` 目录
4. **工具函数**：统一放在 `src/utils/` 目录
5. **类型定义**：统一放在 `src/typings.d.ts` 或 `services/API.d.ts`

### 代码规范

1. **使用 TypeScript 严格模式**
2. **API 调用统一封装**在 `services/` 层
3. **使用 Umi Request**：自动处理错误和 Token
4. **遵循 Prettier 格式化规则**：
   - 单引号
   - 80 字符换行
   - 尾随逗号
   - 自动排序导入
5. **使用 ESLint**：保持代码质量
6. **Git Hooks**：提交前自动检查和格式化

### 组件规范

1. **使用 Ant Design Pro Components**：ProTable、ProForm 等
2. **使用函数式组件 + Hooks**
3. **页面组件使用 PageContainer 包裹**
4. **合理使用 Umi Model** 管理状态

### 性能优化

1. **使用 Hash 路由**：便于缓存
2. **按需加载组件**
3. **合理使用 useMemo 和 useCallback**
4. **优化打包体积**

---

## 📅 更新日志

| 日期 | 版本 | 描述 |
|------|------|------|
| 2026-06-16 | - | AI 自动补充完整项目文档 |
| 2026-06-15 | - | 创建知识库文档 |

---

## 🔖 标签

#前端 #Web端 #React-18 #UmiJS-Max #UmiJS-4 #AntDesign-4 #AntDesignPro #TypeScript #TPM系列 #商户管理 #Web应用 #积分管理 #经销商管理 #维护中

---

## 相关链接

- [[01-索引/技术栈索引\|技术栈索引]]
- [[01-索引/项目总览\|项目总览]]
- [[问题记录\|问题记录]]
- [Umi Max 文档](https://umijs.org/docs/max/introduce)
- [Ant Design 文档](https://ant.design/)
- [Ant Design Pro 文档](https://pro.ant.design/)
