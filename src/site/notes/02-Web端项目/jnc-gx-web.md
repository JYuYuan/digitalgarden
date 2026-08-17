---
{"dg-publish":true,"permalink":"/02-web/jnc-gx-web/","dg-note-properties":{}}
---

# jnc-gx-web

> 剑南春产供销信息平台 - 基于 RuoYi-Vue 的企业管理系统

---
## 分支详情

- 生产分支：release
- 测试分支：test

---
## 快速启动

```bash
# Node 版本
Node 8.9+（建议使用项目原环境）

# 安装依赖
npm install

# 启动开发服务器
npm run dev

# 访问地址
http://localhost:1024
```

**其他常用命令：**
- 构建（生产环境）：`npm run build:prod`
- 构建（测试/预发环境）：`npm run build:stage`
- 代码检查：`npm run lint`
- 单元测试：`npm run test:unit`
- CI 检查：`npm run test:ci`

---

## 项目信息

- **项目名称**：jnc-gx-web
- **项目类型**：Web 前端应用
- **开发状态**：#维护中
- **项目路径**：`<工作区>/jnc-gx-web`
- **系统名称**：剑南春产供销信息平台
- **仓库来源**：RuoYi-Vue 二次开发

---

## 技术栈

### 核心技术

- **框架**：Vue 2.6.10
- **UI 库**：Element UI 2.15.8
- **状态管理**：Vuex 3.1.0
- **路由**：Vue Router 3.0.2
- **语言**：JavaScript
- **构建工具**：Vue CLI 3.5.3 + Webpack
- **包管理**：npm

### 主要依赖

- `axios` 0.18.1 - HTTP 请求
- `echarts` 4.2.1 - 图表展示
- `fuse.js` 3.4.4 - 模糊搜索
- `js-cookie` 2.2.0 - Cookie 操作
- `jsencrypt` 3.0.0-rc.1 - RSA 加密
- `moment` 2.29.1 - 时间处理
- `nprogress` 0.2.0 - 顶部进度条
- `screenfull` 4.2.0 - 全屏控制
- `sortablejs` 1.12.0 - 拖拽排序
- `vue-print-nb` 1.5.0 - 打印
- `vue-quill-editor` 3.0.6 - 富文本编辑器
- `vue-cropper` 0.4.9 - 图片裁剪
- `vue-splitpane` 1.0.4 - 分栏布局
- `@riophae/vue-treeselect` 0.4.0 - 树形选择器

---

## 项目结构

```text
jnc-gx-web/
├── src/
│   ├── api/              # 接口定义
│   ├── assets/           # 静态资源
│   ├── components/       # 全局组件
│   ├── directive/        # 自定义指令
│   ├── layout/           # 布局组件
│   ├── router/           # 路由配置
│   ├── store/            # Vuex 状态管理
│   ├── utils/            # 工具函数
│   └── views/            # 业务页面
├── public/               # 静态资源
├── nginx/                # Nginx 配置
├── .env.development      # 开发环境配置
├── .env.production       # 生产环境配置
├── .env.staging          # 预发环境配置
├── vue.config.js         # Vue CLI 配置
└── package.json
```

---

## 核心功能模块

### 1. 基础管理
- 字典、菜单、角色、用户、部门、岗位、公告
- 日志、在线用户、服务器监控、定时任务
- 系统配置、参数维护、代码生成、Swagger 文档

### 2. 产供销业务
- 计划管理
- 审批/授权流程
- 订单与供销相关业务
- 采购、销售、供货、填报等业务页面

### 3. 商品与库存
- 商品信息
- SKU / SPU 管理
- 单位、分类、包装、产能配置
- 库存、损耗、缺货、供应商管理

### 4. 报表与分析
- 生产、采购、销售报表
- 装箱/灌装等业务报表
- BI 报表看板

### 5. 工作流
- 流程模型管理
- 流程部署
- 流程实例查询
- 待办任务处理

---

## 环境配置

### 本地开发

- 开发代理前缀：`/dev-api`
- 远端开发后端：`https://pms-dev.jncapp.cn/smart`
- 认证中心开发地址：`https://password-dev.jncapp.cn`

### 生产/测试构建

- 测试环境 API 前缀：`/smart`
- 生产环境 API 前缀：`/smart`
- 认证中心生产地址：`https://password.jncapp.cn`

### 关键环境变量

- `VUE_APP_BASE_API` - 后端接口前缀
- `VUE_APP_BASE_OAUTH_API` - 生产认证中心地址
- `VUE_APP_BASE_OAUTH_API_DEV` - 开发认证中心地址
- `VUE_APP_BASE_BASIC` - 基础认证串

---

## 常见问题

_暂无记录。遇到问题后会记录在 [[问题记录\|问题记录]] 中。_

---

## 标签

#前端 #Web端 #Vue2 #ElementUI #Vuex #VueRouter #RuoYi #产供销平台 #业务管理系统 #维护中

---

## 相关链接

- [[01-索引/技术栈索引\|技术栈索引]]
- [[01-索引/项目总览\|项目总览]]
- [[01-索引/快速导航\|快速导航]]
- [RuoYi-Vue](https://gitee.com/y_project/RuoYi-Vue)
