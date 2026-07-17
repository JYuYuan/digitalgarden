---
{"dg-publish":true,"permalink":"/03/jnc-dms-wx/","dg-note-properties":{}}
---

# jnc-dms-wx

> 剑南春 DMS 多功能微信小程序 - 集成分销、TPM、OMS、物流、宴会等多业务模块

---

## ⚡ 快速启动

```bash
# Node 版本
Node 16.x+（推荐 Node 16-18）

# 安装依赖
npm install

# 开发环境 - 微信小程序
npm run dev:weapp

# 生产环境构建
npm run build:prod

# 生产环境构建并上传
npm run build:upload
```

**AppID:** `wx80c338ba268b3606`

**其他常用命令：**
- 开发环境（真实环境）：`npm run dev:realapp`
- 生产环境监听：`npm run prod:weapp`
- 其他平台：支付宝 `dev:alipay`、字节跳动 `dev:tt`、H5 `dev:h5` 等

---

## 📋 项目信息

- **项目名称**：jnc-dms-wx
- **项目类型**：Taro 3.4.0 多端小程序（主要微信小程序）
- **开发状态**：#维护中
- **构建目录**：`dist/`（编译后输出）
- **小程序基础库版本**：3.11.3
- **项目路径**：`/Users/dompling/WebstormProjects/Work/jnc-dms-wx`

---

## 🛠️ 技术栈

### 核心技术

- **框架**：Taro 3.4.0（React 版）
- **UI 库**：Taro UI 3.0.0-alpha.3
- **语言**：TypeScript 4.1+ / JavaScript ES6+
- **样式**：Sass/SCSS
- **状态管理**：Dva 2.4.1 + Redux + Redux Saga
- **包管理**：npm
- **构建工具**：Taro CLI + Webpack

### 主要依赖

**框架核心：**
- `@tarojs/taro` 3.4.0 - Taro 核心库
- `@tarojs/react` 3.4.0 - Taro React 运行时
- `@tarojs/components` 3.4.0 - Taro 组件库
- `@tarojs/cli` 3.4.0 - Taro 命令行工具

**UI 组件：**
- `taro-ui` 3.0.0-alpha.3 - Taro UI 组件库
- `taro-code` 3.5.2 - 二维码组件

**状态管理：**
- `dva` 2.4.1 - 数据流方案
- `dva-core` 2.0.4 - Dva 核心
- `dva-loading` 3.0.22 - 加载状态管理
- `react-redux` 7.2.2 - React Redux 绑定
- `redux-saga` 1.1.3 - 异步流管理
- `redux-logger` 3.0.6 - Redux 日志中间件

**工具库：**
- `lodash` 4.17.15 - JavaScript 工具库
- `moment` 2.29.1 - 时间处理
- `rc-field-form` 2.2.0 - 表单管理
- `taro-hooks` 2.0.11 - Taro Hooks 工具集

**视频上传：**
- `vod-wx-sdk-v2` 1.1.2 - 腾讯云点播 SDK

**开发工具：**
- `@types/react` 17.0.2 - React 类型定义
- `@types/wechat-miniprogram` 3.4.3 - 微信小程序类型定义
- `typescript` 4.1.0 - TypeScript 编译器
- `eslint` 6.8.0 - 代码检查
- `miniprogram-ci` 1.5.1 - 小程序 CI 工具
- `taro-iconfont-cli` 3.3.0 - 图标字体 CLI

---

## 📂 项目结构

```text
jnc-dms-wx/
├── src/
│   ├── pages/                  # 页面目录（按业务模块分类）
│   │   ├── global/            # 全局页面（登录、密码等）
│   │   ├── dms/               # DMS 分销管理系统页面
│   │   │   ├── index/         # DMS 首页
│   │   │   ├── grade/         # 等级管理
│   │   │   ├── my/            # 个人中心
│   │   │   ├── distributionOrder/  # 配货单管理
│   │   │   ├── returnOrder/   # 退货单管理
│   │   │   ├── orderArrival/  # 订单到货
│   │   │   ├── customWine/    # 定制酒管理
│   │   │   ├── warehouseManagement/ # 仓库管理
│   │   │   ├── terminalOrder/ # 终端订单
│   │   │   ├── storeManage/   # 库存管理
│   │   │   └── ...            # 其他 DMS 业务模块
│   │   ├── tpm/               # TPM 贸易促销管理页面
│   │   ├── tpmA/              # TPM-A 模块（陈列、物料等）
│   │   ├── tpmB/              # TPM-B 模块
│   │   ├── banquet/           # 宴会管理页面
│   │   │   ├── execution/     # 宴会执行
│   │   │   ├── logistics/     # 物流管理
│   │   │   ├── offlineTask/   # 线下任务
│   │   │   └── ...            # 其他宴会模块
│   │   ├── logistics/         # 物流管理页面
│   │   ├── oms/               # OMS 订单管理系统页面
│   │   └── distributor/       # 经销商页面
│   ├── components/            # 公共组件
│   │   ├── global/            # 全局组件
│   │   ├── dms/               # DMS 组件
│   │   ├── tpm/               # TPM 组件
│   │   └── oms/               # OMS 组件
│   ├── config/                # 模块配置
│   │   ├── dms/pages.js       # DMS 页面路由配置
│   │   ├── tpm/pages.js       # TPM 页面路由配置
│   │   ├── oms/pages.js       # OMS 页面路由配置
│   │   ├── logistics/pages.js # 物流页面路由配置
│   │   └── distributor/pages.js # 经销商页面路由配置
│   ├── api/                   # API 接口层
│   │   ├── global/            # 全局 API
│   │   ├── dms/               # DMS API
│   │   ├── tpm/               # TPM API
│   │   └── oms/               # OMS API
│   ├── models/                # Dva 数据模型
│   ├── utils/                 # 工具函数
│   │   ├── global/            # 全局工具
│   │   ├── dms/               # DMS 工具
│   │   ├── tpm/               # TPM 工具
│   │   ├── oms/               # OMS 工具
│   │   └── dva.js             # Dva 实例创建
│   ├── plugins/               # 插件
│   ├── assets/                # 静态资源
│   │   ├── global/            # 全局资源
│   │   ├── dms/               # DMS 资源
│   │   └── oms/               # OMS 资源
│   ├── types/                 # TypeScript 类型定义
│   ├── log/                   # 日志相关
│   ├── cloud/                 # 云函数
│   ├── app.tsx                # 应用入口
│   ├── app.config.ts          # 应用配置
│   └── app.scss               # 全局样式
├── config/                    # 构建配置
│   ├── index.js               # Taro 配置入口
│   ├── dev.js                 # 开发环境配置
│   └── prod.js                # 生产环境配置
├── dist/                      # 编译输出目录
├── scripts/                   # 构建脚本
│   └── deploy-dist.sh         # 部署脚本
├── nginx/                     # Nginx 配置
├── package.json               # 项目依赖配置
├── tsconfig.json              # TypeScript 配置
├── project.config.json        # 小程序项目配置
├── project.private.config.json # 小程序私有配置
├── babel.config.js            # Babel 配置
├── iconfont.json              # 图标字体配置
└── global.d.ts                # 全局类型声明
```

---

## 🎯 核心功能模块

### 1. DMS 分销管理系统（Distribution Management System）

**订单管理：**
- 配货单管理（创建、编辑、详情、分单、上传凭证）
- 退货单管理（创建、详情）
- 终端订单管理
- 订单到货确认
- 退货到货确认

**库存管理：**
- 仓库管理（出库、入库、扫码、物流）
- 经销商库存盘点
- 终端库存管理
- 库存调拨
- 库存审核

**定制酒管理：**
- 定制酒订单（创建、审核、详情）
- 经销商出库
- 库存入库
- 到货确认
- 定制码管理

**促销订单：**
- 促销订单（新版）管理
- 促销库存审核
- 促销订单退货

**经销商管理：**
- 经销商确认管理
- 价格申请管理
- 拉环回收

### 2. TPM 贸易促销管理（Trade Promotion Management）

**TPM-A 模块：**
- 陈列管理（成都天津、德阳、河南、珍藏、剑南春等）
- 物料管理
- 宴席二维码
- 店铺展示管理

**TPM-B 模块：**
- 费用管理
- 促销活动管理
- 贸易促销分析

### 3. 宴会管理（Banquet）

- 宴会申请
- 宴会执行（完整流程）
- 宴会账单管理
- 礼品管理
- VIP 管理
- 线下任务管理
- 宴会物流
- 台卡管理

### 4. OMS 订单管理系统（Order Management System）

- 订单创建和管理
- 订单流程跟踪
- 订单审核

### 5. 物流管理（Logistics）

- 物流跟踪
- 配送管理
- 物流信息查询

### 6. 经销商管理（Distributor）

- 经销商信息管理
- 经销商分包功能

### 7. 全局功能（Global）

- 登录认证（账号登录、企业微信登录）
- 密码管理
- 个人中心
- 等级管理

---

## 🔧 配置说明

### 小程序配置（app.config.ts）

**页面配置：**
- 全局页面：登录、密码、首页等
- 模块化路由：从各模块配置文件动态导入

**分包策略：**
- 按业务模块分包（DMS、TPM、OMS、Logistics、Distributor）
- 每个模块独立分包，按需加载

**权限配置：**
- 位置权限：`scope.userLocation`（用于定位相关功能）
- 隐私接口：`getLocation`、`chooseLocation`

**网络超时：**
- 上传文件：20 分钟（1200000ms）
- 下载文件：20 分钟（1200000ms）

**全局组件：**
- 使用 IconFont 全局图标组件

### 项目配置（project.config.json）

**编译设置：**
- 小程序根目录：`dist/`
- ES6 转 ES5：关闭（由 Taro 处理）
- 代码压缩：开启
- 上传时生成 SourceMap：开启
- 多框架运行时：开启
- API Hook：开启

**云函数：**
- 云函数根目录：`cloud/`

### TypeScript 配置（tsconfig.json）

**路径别名：**
- `@/dms/*` → `src/.../dms/*`（DMS 模块）
- `@/tpm/*` → `src/.../tpm/*`（TPM 模块）
- `@/oms/*` → `src/.../oms/*`（OMS 模块）
- `@/global/*` → `src/.../global/*`（全局模块）
- `@/components/*` → `src/components/*`
- `@/utils/*` → `src/utils/*`
- `@/api/*` → `src/api/*`
- `@/models/*` → `src/models/*`

**编译选项：**
- Target：ES2017
- JSX：Preserve（保留 JSX）
- 严格空检查：开启
- 装饰器支持：开启

---

## 🌍 环境配置

环境配置位于 `config/` 目录：
- `dev.js` - 开发环境配置
- `prod.js` - 生产环境配置
- `index.js` - Taro 构建配置入口

**构建配置包含：**
- API 代理配置
- 环境变量注入
- Webpack 优化配置
- 样式处理配置

---

## 🔗 相关项目

_暂无记录。如有关联项目，会补充在此处。_

---

## 🐛 常见问题

### 1. 企业微信登录

项目支持企业微信和微信小程序两种登录方式：
- 企业微信：通过 `callbackResult.query` 判断入口（isjnc、state、isBanquet 等）
- 小程序跳转：通过 `referrerInfo.extraData` 获取授权数据

### 2. 多模块架构

项目采用模块化架构，各模块相互独立：
- 每个模块有独立的页面配置文件（`config/{module}/pages.js`）
- 每个模块有独立的组件、API、工具目录
- 通过 TypeScript 路径别名实现模块隔离

### 3. 构建 npm

Taro 3.x 项目开发流程：
1. 在项目根目录执行 `npm install`
2. 执行 `npm run dev:weapp` 启动开发模式
3. 使用微信开发者工具打开 `dist/` 目录

---

## 📝 开发规范

### 目录规范

1. **模块隔离**：每个业务模块独立目录结构（pages、components、api、utils）
2. **路径别名**：使用 `@/{module}/*` 别名引用模块内资源
3. **组件命名**：使用 PascalCase（大驼峰）
4. **页面目录**：每个页面一个文件夹，包含 .tsx, .scss, .config.ts

### 代码规范

1. **使用 TypeScript**：优先使用 TypeScript 编写新代码
2. **使用 Hooks**：React 组件优先使用 Hooks
3. **状态管理**：全局状态使用 Dva，局部状态使用 useState/useReducer
4. **API 调用统一封装**：在 `api/` 层统一管理
5. **样式隔离**：使用 SCSS 模块化，避免全局污染

### Taro 开发注意事项

1. **跨平台兼容**：使用 Taro 提供的 API，避免平台特定代码
2. **组件使用**：优先使用 Taro UI 组件库
3. **性能优化**：合理使用分包、懒加载
4. **尺寸单位**：使用 Taro 提供的 `pxTransform` 转换单位

### 性能优化

1. **分包加载**：已按业务模块分包（DMS、TPM、OMS、Logistics）
2. **按需引入**：使用 ES6 模块化，支持 Tree Shaking
3. **图片优化**：使用压缩后的图片，优先使用 webp
4. **减少 setData**：合并多次 setData 调用

---

## 📅 更新日志

| 日期 | 版本 | 描述 |
|------|------|------|
| 2026-06-16 | - | AI 自动补充完整项目文档 |
| 2026-06-15 | - | 创建知识库文档 |

---

## 🔖 标签

#小程序 #微信小程序 #跨端小程序 #React-17 #Taro #TaroUI #TypeScript #DVA #Redux #DMS系列 #TPM #OMS #多业务模块 #剑南春 #企业微信 #维护中

---

## 相关链接

- [[01-索引/技术栈索引\|技术栈索引]]
- [[01-索引/项目总览\|项目总览]]
- [[问题记录\|问题记录]]
- [Taro 官方文档](https://taro-docs.jd.com/)
- [Taro UI 文档](https://taro-ui.jd.com/)
- [React 官方文档](https://react.dev/)
- [Dva 官方文档](https://dvajs.com/)
- [微信小程序官方文档](https://developers.weixin.qq.com/miniprogram/dev/framework/)
