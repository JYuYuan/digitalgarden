---
{"dg-publish":true,"permalink":"/02-web/jnc-dms-web/","dg-note-properties":{}}
---

# jnc-dms-web

> JNC DMS Web 管理后台 - 基于 React 的分销管理系统（Distribution Management System）

---

## ⚡ 快速启动

```bash
# Node 版本
Node 16.x+

# 安装依赖
npm install
# 或使用 yarn（推荐）
yarn

# 启动开发服务器
npm start
# 或
yarn start

# 访问地址
http://localhost:3000
```

**其他常用命令：**
- 构建生产版本：`npm run build` / `yarn build`
- 预览构建结果：`npm run preview` / `yarn preview`
- 代码检查：`npm run lint` / `yarn lint`
- 代码修复：`npm run lint:fix` / `yarn lint:fix`
- 生成自定义主题：`npm run theme` / `yarn theme`

---

## 📋 项目信息

- **项目名称**：jnc-dms-web
- **项目类型**：Web 前端应用
- **开发状态**：#维护中
- **版本**：v0.1.0
- **项目路径**：`/Users/dompling/WebstormProjects/Work/jnc-dms-web`

---

## 🛠️ 技术栈

### 核心技术

- **框架**：React 16.13.1 + Vite 4.5.5
- **UI 库**：Ant Design 4.24.15 + Ant Design Pro Components 2.6.42
- **状态管理**：Redux 4.0.0 + Redux Thunk 2.3.0
- **路由**：React Router DOM 4.3.1
- **语言**：JavaScript (ES6+) + TypeScript 5.5.4（部分使用）
- **构建工具**：Vite
- **包管理**：npm/yarn

### 主要依赖

**数据请求：**
- `axios` 0.18.0 - HTTP 客户端

**工具库：**
- `@umijs/hooks` 1.9.0 - React Hooks 工具集
- `lodash` 4.17.15 - 工具函数库
- `dayjs` 1.11.10 - 时间处理
- `moment` 2.30.1 - 时间处理（兼容旧代码）
- `classnames` 2.2.6 - 动态类名工具

**业务组件：**
- `echarts` 4.2.0-rc.1 + `echarts-for-react` 2.0.15 - 可视化图表
- `recharts` 1.3.3 - 另一个图表库
- `react-draft-wysiwyg` 1.12.13 + `draft-js` 0.11.7 - 富文本编辑器
- `react-loadable` 5.5.0 - 代码拆分和按需加载
- `@loadable/component` 5.16.4 - 组件懒加载
- `react-activation` 0.13.4 - Keep-Alive 路由缓存
- `react-to-print` 2.7.0 - 打印组件

**UI 增强：**
- `nprogress` 0.2.0 - 顶部加载进度条
- `screenfull` 3.3.3 - 全屏插件
- `photoswipe` 4.1.2 - 图片预览插件
- `react-draggable` 3.0.5 - 拖拽组件
- `rc-banner-anim` 2.0.8 + `rc-tween-one` 3.0.6 - 动画组件
- `react-color` 2.14.1 - 颜色选择器
- `react-qmap` 0.1.5 - 腾讯地图组件

**云存储：**
- `aws-sdk` 2.831.0 - AWS S3 云存储

---

## 📂 项目结构

```text
jnc-dms-web/
├── src/
│   ├── action/           # Redux Actions
│   ├── api/              # API 接口定义
│   │   ├── Ajax.js       # 主接口
│   │   ├── AjaxSAC.js    # SAC 系统接口
│   │   ├── AjaxV3.js     # V3 版本接口
│   │   ├── oms/          # 订单管理系统接口
│   │   ├── mdm.js        # 主数据管理接口
│   │   ├── order.js      # 订单接口
│   │   ├── policy.js     # 政策接口
│   │   ├── promotion.js  # 促销接口
│   │   ├── stock.js      # 库存接口
│   │   ├── system.js     # 系统接口
│   │   └── ...           # 其他业务接口
│   ├── axios/            # HTTP 请求封装
│   ├── commons/          # 公共工具
│   │   ├── constant.js   # 常量定义
│   │   ├── request.js    # 请求封装
│   │   ├── filters/      # 过滤器（字符串、日期）
│   │   └── rules/        # 表单验证规则
│   ├── components/       # 全局组件
│   │   ├── Access/       # 权限控制
│   │   ├── BasicLayout/  # 基础布局
│   │   ├── JNCTable/     # JNC 通用表格
│   │   ├── ProTable/     # Pro 高级表格
│   │   ├── ProUpload/    # 文件上传组件
│   │   ├── auth/         # 认证组件
│   │   ├── common/       # 通用组件
│   │   ├── dashboard/    # 仪表盘组件
│   │   ├── forms/        # 表单组件
│   │   ├── tables/       # 表格组件
│   │   ├── ui/           # UI 组件
│   │   ├── charts/       # 图表组件
│   │   ├── region/       # 地区选择
│   │   ├── widget/       # 小部件
│   │   ├── HeaderCustom.jsx    # 顶部导航
│   │   ├── SideCustom.jsx      # 侧边菜单
│   │   └── BreadcrumbCustom.jsx # 面包屑
│   ├── views/            # 业务页面视图
│   │   ├── custom/           # 自定义页面
│   │   ├── directDistribution/ # 直分销
│   │   ├── distribution/     # 分销管理
│   │   ├── mdm/             # 主数据管理
│   │   ├── order/           # 订单管理
│   │   ├── orderCenter/     # 订单中心
│   │   ├── policy/          # 政策管理
│   │   ├── promotion/       # 促销管理
│   │   ├── stock/           # 库存管理
│   │   └── system/          # 系统管理
│   ├── routes/           # 路由配置
│   │   ├── index.jsx     # 路由入口
│   │   └── routes.js     # 路由表
│   ├── reducer/          # Redux Reducers
│   ├── plugins/          # 插件
│   ├── polyfills/        # Polyfills
│   ├── style/            # 样式文件（Less）
│   ├── utils/            # 工具函数
│   ├── App.jsx           # 应用入口组件
│   ├── Page.jsx          # 页面容器
│   └── index.jsx         # 入口文件
├── public/               # 静态资源（不打包）
├── vite.config.mjs       # Vite 配置
├── theme.js              # Ant Design 主题生成器
└── package.json          # 依赖管理
```

---

## 🌍 环境配置

### Vite 配置

项目使用 Vite 作为构建工具，配置文件为 `vite.config.mjs`：

**关键配置：**
- 开发服务器端口：`3000`
- 构建输出目录：`build/`
- 路径别名：`@` → `src/`
- 支持 JSX 和装饰器语法
- Less 预处理器支持
- AWS SDK 单独打包

**Babel 插件：**
- `@babel/plugin-proposal-decorators` - 装饰器语法（legacy mode）
- `@babel/plugin-proposal-class-properties` - 类属性语法（loose mode）

---

## 🎯 核心功能模块

### 业务模块

1. **主数据管理（MDM）**
   - 商品管理
   - 客户管理
   - 组织架构
   - 基础数据维护

2. **订单管理（Order）**
   - 订单创建和编辑
   - 订单审核流程
   - 订单中心
   - 退货管理

3. **库存管理（Stock）**
   - 库存查询
   - 库存调拨
   - 库存预警

4. **分销管理（Distribution）**
   - 直分销管理
   - 经销商管理
   - 分销政策

5. **政策管理（Policy）**
   - 价格政策
   - 促销政策
   - 返利政策

6. **促销管理（Promotion）**
   - 促销活动
   - 促销规则
   - 促销效果分析

7. **系统管理（System）**
   - 用户管理
   - 权限管理
   - 菜单配置
   - 系统设置

### UI 功能特性

- ✅ 顶部导航（菜单伸缩、全屏、换肤）
- ✅ 左侧菜单（滚动条、路由 Active 状态）
- ✅ 面包屑导航
- ✅ 路由缓存（Keep-Alive）
- ✅ 富文本编辑器
- ✅ 图表可视化（ECharts + Recharts）
- ✅ 文件上传（S3）
- ✅ 图片预览
- ✅ 拖拽功能
- ✅ 打印功能
- ✅ 动画效果
- ✅ 权限控制（基于 Redux）
- ✅ 响应式布局

---

## 🔧 配置说明

### 代码规范

- **ESLint**：自定义配置（`.eslintrc`）
- **Babel**：支持装饰器和类属性语法

### Ant Design 主题定制

项目使用 `antd-theme-generator` 生成自定义主题：
- 运行 `npm run theme` / `yarn theme` 生成主题文件
- 支持动态换肤功能
- 默认使用黑色主题

### 路由缓存机制

使用 `react-activation` 实现 Keep-Alive：
- 基于 `cacheKey`（pathname + search）缓存页面
- 支持多页签场景
- 自动管理缓存生命周期

---

## 🔗 相关项目

- 该项目属于 **JNC DMS 系列**

---

## 🐛 常见问题

### 1. 启动慢或打包慢

项目使用了较多依赖，首次启动和打包需要等待 1-2 分钟。

### 2. AWS SDK 打包体积大

已配置单独打包 `aws-sdk`，生产环境使用 `dist/aws-sdk.js` 版本。

### 3. Moment.js 打包优化

已配置别名指向 `moment-with-locales.js` 压缩版本。

### 4. 装饰器语法报错

确保 Babel 插件顺序正确：`decorators` 必须在 `class-properties` 之前。

---

## 📅 更新日志

| 日期 | 版本 | 描述 |
|------|------|------|
| 2026-06-16 | v0.1.0 | AI 自动补充完整项目文档 |
| 2026-06-15 | - | 创建知识库文档 |

---

## 🔖 标签

#前端 #Web端 #React-16 #Vite #AntDesign-4 #Redux #DMS系列 #分销管理系统 #需要升级 #维护中

---

## 相关链接

- [[01-索引/技术栈索引\|技术栈索引]]
- [[01-索引/项目总览\|项目总览]]
- [[问题记录\|问题记录]]
