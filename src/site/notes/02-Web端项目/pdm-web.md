---
{"dg-publish":true,"permalink":"/02-web/pdm-web/","dg-note-properties":{}}
---

# pdm-web

> 剑南春产品信息库管理系统（Product Data Management）

---

## ⚡ 快速启动

```bash
# Node 版本
Node >= 10.0.0

# 安装依赖
npm install

# 启动开发服务器
npm run start
# 或指定环境
npm run start:dev      # 开发环境
npm run start:test     # 测试环境
npm run start:pre      # 预发布环境

# 访问地址
http://localhost:3080  # 默认端口 3080
```

**其他常用命令：**
- 构建生产版本：`npm run build`
- 构建分析：`npm run analyze`
- 代码检查：`npm run lint`
- 代码修复：`npm run lint:fix`
- 样式检查：`npm run lint:style`
- 格式化代码：`npm run prettier`
- 运行测试：`npm run test`

---

## 📋 项目信息

- **项目名称**：pdm-web（产品信息库管理系统）
- **显示名称**：剑南春产品信息库
- **项目类型**：Web 前端应用
- **开发状态**：#维护中
- **版本**：v5.0.0-beta.0
- **项目路径**：`/Users/dompling/WebstormProjects/Work/pdm-web`
- **默认端口**：3080

---

## 🛠️ 技术栈

### 核心技术

- **框架**：React 16.8.6 + Umi 3.5.0
- **UI 库**：Ant Design 4.23.1 + Ant Design Pro
- **状态管理**：Dva (内置于 Umi)
- **路由**：React Router 5.2.0（Umi 内置）
- **语言**：TypeScript 4.1.2
- **构建工具**：Umi + Webpack
- **包管理**：npm

### Ant Design Pro 组件库

- `@ant-design/pro-layout` 6.26.0 - 布局组件
- `@ant-design/pro-table` 3.1.0 - 高级表格
- `@ant-design/pro-form` 1.67.3 - 高级表单
- `@ant-design/pro-card` 1.18.31 - 卡片组件
- `@ant-design/pro-descriptions` 1.9.6 - 描述列表
- `@ant-design/charts` 1.4.2 - 图表组件

### 主要依赖

**数据请求：**
- `umi-request` 1.0.8 - HTTP 请求库
- `@umijs/use-request` 1.4.3 - 异步数据管理
- `@umijs/hooks` 1.9.3 - React Hooks 工具集

**工具库：**
- `lodash` 4.17.21 - 工具函数库
- `moment` 2.29.1 - 时间处理
- `qs` 6.9.0 - 查询字符串解析
- `classnames` 2.2.6 - 类名拼接

**业务组件：**
- `swiper` 6.8.4 - 轮播图组件
- `react-viewer` 3.2.2 - 图片预览
- `react-syntax-highlighter` 15.5.0 - 代码高亮
- `xlsx` 0.18.5 - Excel 处理
- `js-export-excel` 1.1.4 - Excel 导出
- `react-activation` 0.11.2 - 页面缓存（Keep Alive）

**云存储：**
- `cos-js-sdk-v5` 1.3.9 - 腾讯云 COS SDK
- `aws-sdk` 2.940.0 - AWS SDK

**加密和安全：**
- `crypto-js` 4.1.1 - 加密库

**动画：**
- `rc-queue-anim` 1.8.5 - 队列动画
- `@dnd-kit/core` + `@dnd-kit/sortable` - 拖拽排序

**其他：**
- `react-custom-scrollbars` 4.2.1 - 自定义滚动条
- `react-helmet-async` 1.0.4 - 文档头部管理
- `rxjs` 7.1.0 - 响应式编程

---

## 📂 项目结构

```text
pdm-web/
├── src/
│   ├── .umi/            # Umi 自动生成的临时文件
│   ├── assets/          # 静态资源文件
│   ├── components/      # 全局公共组件
│   │   ├── ActivityInfo/        # 活动信息
│   │   ├── DownloadButton/      # 下载按钮
│   │   ├── ExportToFile/        # 导出文件
│   │   ├── FieldDisplay/        # 字段展示
│   │   ├── Footer/              # 页脚
│   │   ├── FormComponent/       # 表单组件
│   │   ├── FromPicker/          # 日期选择器
│   │   ├── HeaderSearch/        # 头部搜索
│   │   ├── HistoryPhoto/        # 历史照片
│   │   ├── PageLoading/         # 页面加载
│   │   ├── PackageVersions/     # 包装版本
│   │   ├── PanelTitle/          # 面板标题
│   │   ├── PicCarousel/         # 图片轮播
│   │   ├── PictureCard/         # 图片卡片
│   │   ├── PreviewImage/        # 图片预览
│   │   ├── ProExcel/            # Excel 组件
│   │   ├── RightContent/        # 右侧内容
│   │   ├── SettlementTable/     # 结算表格
│   │   ├── ShowVideo/           # 视频展示
│   │   ├── TagView/             # 标签视图
│   │   ├── ToolTag/             # 工具标签
│   │   ├── TPMProExcel/         # TPM Excel
│   │   └── VideoAndImg/         # 视频和图片
│   ├── config/          # 项目配置
│   ├── e2e/             # 端到端测试
│   ├── layouts/         # 布局组件
│   ├── models/          # Dva 数据模型
│   ├── pages/           # 业务页面
│   │   ├── user/                # 用户相关（登录等）
│   │   ├── Promotional/         # 促销活动（SPU/SKU 数据）
│   │   ├── ProductInformation/  # 产品信息详情
│   │   ├── BasePage/            # 基础页面（文件上传等）
│   │   ├── Welcome.tsx          # 欢迎页
│   │   └── 404.tsx              # 404 页面
│   ├── services/        # API 接口服务
│   └── utils/           # 工具函数
│       └── i18n/        # 国际化
├── config/              # Umi 配置目录
│   ├── config.ts        # 主配置文件
│   ├── defaultSettings.ts # 默认配置
│   ├── proxy.ts         # 代理配置
│   └── routes/          # 路由配置
├── tests/               # 测试文件
├── public/              # 静态资源（不打包）
├── .env                 # 环境变量（端口配置）
├── .eslintrc.js         # ESLint 配置
├── .prettierrc.js       # Prettier 配置
├── .stylelintrc.js      # Stylelint 配置
├── tsconfig.json        # TypeScript 配置
├── jest.config.js       # Jest 测试配置
└── package.json         # 依赖管理
```

---

## 🌍 环境配置

### 环境变量

项目使用 `.env` 文件配置开发服务器端口：

```bash
PORT=3080
```

### 多环境启动

Umi 通过 `REACT_APP_ENV` 环境变量区分不同运行环境：

- **开发环境**：`npm run start:dev` → `REACT_APP_ENV=dev`
- **测试环境**：`npm run start:test` → `REACT_APP_ENV=test`
- **预发布环境**：`npm run start:pre` → `REACT_APP_ENV=pre`

### 代理配置

开发环境后端代理配置见 `config/proxy.ts`。

---

## 🎯 核心功能模块

根据项目结构和配置分析，主要功能模块包括：

- **产品信息管理（Product Information）**
  - 产品详情查看
  - 条码详情（barCodeDetail）
  - 检验详情（inspectionDetail）
  - 口感详情（tasteDetail）
  - 防伪规则 V2（antiFakeRulesV2）
  - 变更记录（changeRecord）
  - 通用附件（generalAttachments）
  - 品类信息（SKS/SKU）

- **促销活动管理（Promotional）**
  - SPU 数据管理（SPU_data）
  - SKU 数据管理（SKU_data）
  - 历史记录查看
  - 有效期管理（validityDate）

- **用户管理**
  - 用户登录（login_in）

- **基础功能**
  - 文件上传（FileUpload）
  - 迷你上传（MiniUpload）

- **公共能力**
  - Excel 导入导出
  - 图片/视频预览
  - 云存储集成（腾讯云 COS / AWS）
  - 拖拽排序
  - 页面缓存（Keep Alive）

---

## 🔧 配置说明

### 代码规范

- **ESLint**：使用 `@umijs/fabric` 配置
- **Prettier**：统一代码格式化
- **Stylelint**：Less 样式规范检查
- **TypeScript**：严格模式（`--noEmit` 检查）

### 布局配置

项目使用 `@ant-design/pro-layout` 提供企业级布局：

- **主题**：light（浅色）
- **主色调**：`#d43235`（剑南春红）
- **布局方式**：mix（混合布局）
- **内容宽度**：Fluid（流式）
- **固定头部**：是
- **固定侧边栏**：是
- **标题**：剑南春产品信息库
- **Logo**：`/logo.png`

### 国际化

- 默认语言：`zh-CN`（简体中文）
- Ant Design 国际化已开启
- 菜单国际化：关闭（`menu.locale: false`）

### 构建优化

- **代码分割**：启用动态导入（`dynamicImport`）
- **Chunks 分组**：vendors（第三方库）+ umi（框架代码）
- **Hash 文件名**：生产环境启用
- **输出目录**：`build/`
- **兼容性**：IE 10+

---

## 🐛 常见问题

_暂无记录。遇到问题后会记录在 [[问题记录\|问题记录]] 中。_

---

## 📅 更新日志

| 日期 | 版本 | 描述 |
|------|------|------|
| 2026-06-16 | v5.0.0-beta.0 | AI 自动补充项目文档信息 |
| 2026-06-15 | - | 创建知识库文档 |
| 2024-10-29 | - | 最后一次依赖更新 |

**最近提交记录：**
- e7b9c21 - Merge branch 'ayModifyFillingRule' into prod_release
- c74376e - 品类信息-更改灌装信息修改功能
- a004f7f - Merge branch 'jyy/SKSSKU/品类信息（SKS）' into prod_release

---

## 🔖 标签

#前端 #Web端 #React-16 #UmiJS-3 #AntDesign-4 #AntDesignPro #TypeScript #Dva #产品信息库 #PDM #剑南春 #企业级应用 #需要升级 #维护中

---

## 相关链接

- [[01-索引/技术栈索引\|技术栈索引]]
- [[01-索引/项目总览\|项目总览]]
- [[问题记录\|问题记录]]
- [[待建档项目索引#剑南春项目系列\|剑南春项目系列]]
