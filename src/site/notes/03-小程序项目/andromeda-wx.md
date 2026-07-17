---
{"dg-publish":true,"permalink":"/03/andromeda-wx/","dg-note-properties":{}}
---

# andromeda-wx

> Andromeda 微信小程序 - SFA 销售自动化系统移动端

---

## ⚡ 快速启动

```bash
# Node 版本
Node 16.x+（推荐 Node 18）

# 安装依赖
npm install

# 构建 npm 包
在微信开发者工具中：工具 -> 构建 npm

# 打开项目
使用微信开发者工具打开项目根目录
```

**AppID:** `wx944af2c8af320382`

**其他常用命令：**
- 代码检查：`npm run lint`
- 代码修复：`npm run lint:fix`

---

## 📋 项目信息

- **项目名称**：andromeda-wx (andromeda-wxp)
- **项目类型**：微信原生小程序
- **开发状态**：#维护中
- **小程序版本**：使用 trial 版本基础库
- **项目路径**：`/Users/dompling/WebstormProjects/Work/andromeda-wx`

---

## 🛠️ 技术栈

### 核心技术

- **框架**：微信原生小程序
- **状态管理**：MobX Miniprogram 6.12.3 + mobx-miniprogram-bindings 3.0.0
- **UI 库**：TDesign Miniprogram 1.8.8
- **语言**：JavaScript + TypeScript
- **构建工具**：微信开发者工具（支持 TypeScript + Less）
- **包管理**：npm

### 主要依赖

**UI 组件：**
- `tdesign-miniprogram` 1.8.8 - 腾讯 TDesign 小程序组件库
- `mp-html` 2.5.0 - 富文本渲染组件

**状态管理：**
- `mobx-miniprogram` 6.12.3 - MobX 小程序版
- `mobx-miniprogram-bindings` 3.0.0 - MobX 数据绑定
- `miniprogram-computed` 4.4.0 - 计算属性支持

**工具库：**
- `dayjs` 1.11.11 - 时间处理
- `pubsub-js` 1.9.4 - 发布订阅模式
- `math-expression-evaluator` 2.0.5 - 数学表达式计算

**代码规范：**
- `eslint` + `eslint-config-alloy` - 代码检查
- `prettier` + `prettier-plugin-wxml` - 代码格式化
- `@typescript-eslint` - TypeScript 规则

---

## 📂 项目结构

```text
andromeda-wx/
├── pages/                   # 主包页面
│   ├── index/              # 首页
│   ├── login/              # 登录页
│   ├── attendance/         # 考勤
│   ├── visit/              # 拜访
│   ├── terminal/           # 终端
│   ├── other/              # 其他工作
│   └── my/                 # 我的
├── packages/               # 分包页面
│   ├── attendance/         # 考勤分包（签到拍照、规则、历史等）
│   ├── user/               # 用户分包（个人信息、修改密码）
│   ├── free-sign/          # 自由签到分包
│   ├── terminal/           # 终端分包（终端管理、审批等）
│   ├── auth/               # 授权分包
│   ├── dealer/             # 经销商分包
│   ├── visit/              # 拜访分包（拜访执行、路线等）
│   └── other/              # 其他分包（消息、流程审批、任务等）
├── components/             # 自定义组件
│   ├── account-switcher/   # 账号切换
│   ├── form-editor/        # 表单编辑器
│   ├── file-upload/        # 文件上传
│   ├── paged-list/         # 分页列表
│   └── ...                 # 其他业务组件
├── services/               # API 服务层
│   ├── account-login/      # 账号登录
│   ├── attendance/         # 考勤服务
│   ├── terminal/           # 终端服务
│   ├── visit/              # 拜访服务
│   └── common/             # 通用服务
├── store/                  # MobX 状态管理
│   └── user.js             # 用户状态
├── utils/                  # 工具函数
│   ├── request.js          # 网络请求封装
│   ├── encrypt.js          # 加密工具
│   ├── format.js           # 格式化工具
│   └── location.js         # 定位工具
├── core/                   # 核心模块
│   ├── request/            # 请求核心
│   ├── navigate/           # 导航封装
│   └── password-request/   # 密码请求
├── types/                  # TypeScript 类型定义
│   ├── global.d.ts         # 全局类型
│   ├── terminal.d.ts       # 终端类型
│   └── visit.d.ts          # 拜访类型
├── custom-tab-bar/         # 自定义 TabBar
├── config/                 # 配置文件
│   ├── constant.js         # 常量配置
│   └── env.js              # 环境配置
├── app.js                  # 小程序入口
├── app.json                # 小程序配置
└── project.config.json     # 项目配置
```

---

## 🎯 核心功能模块

### 1. 考勤管理（Attendance）
- 签到打卡（支持拍照、位置验证）
- 考勤规则查看
- 考勤历史记录
- 自由签到

### 2. 拜访管理（Visit）
- 拜访执行和登记
- 拜访计划管理
- 拜访路线规划
- 拜访统计和历史
- 库存上报

### 3. 终端管理（Terminal）
- 终端列表和搜索
- 终端创建和修改
- 终端审批流程
- 终端数据统计
- 地图展示

### 4. 经销商管理（Dealer）
- 经销商列表和详情
- 合同管理
- 经销商信息编辑

### 5. 其他工作（Other）
- 消息通知
- 数据提报
- 流程审批（我的申请、我的审批、抄送我的）
- 考试功能
- 任务管理
- 经销商通知任务

### 6. 个人中心（My）
- 个人信息管理
- 密码修改
- 账号切换

---

## 🔧 配置说明

### 小程序配置（app.json）

**TabBar 配置：**
- 自定义 TabBar（`custom: true`）
- 5 个主 Tab：考勤、拜访、终端、其他工作、我的

**分包策略：**
- 按业务模块分包（attendance、user、terminal、visit、dealer、auth、other）
- 懒加载：`lazyCodeLoading: "requiredComponents"`

**权限配置：**
- 位置权限：`scope.userLocation`（用于定位签到、拜访等）
- 请求超时：300s

**路径别名：**
- `@/*` 映射到根目录

### 项目配置（project.config.json）

**编译设置：**
- ES6 转 ES5：开启
- 代码压缩：开启
- TypeScript + Less 支持
- 上传时生成 SourceMap

---

## 🌍 环境配置

环境配置位于 `config/env.js`，包含：
- API 基础 URL
- 加密密钥配置
- 第三方服务配置

---

## 🔗 相关项目

- [[02-Web端项目/andromeda-web\|andromeda-web]] - Andromeda Web 端

---

## 🐛 常见问题

_暂无记录。遇到问题后会记录在 [[问题记录\|问题记录]] 中。_

---

## 📝 开发规范

### 目录规范

1. **组件命名**：使用小写+连字符（kebab-case）
2. **页面目录**：每个页面一个文件夹，包含 .wxml, .wxss, .js, .json
3. **工具函数**：统一放在 `utils/` 目录
4. **类型定义**：统一放在 `types/` 目录
5. **API 服务**：统一放在 `services/` 目录

### 代码规范

1. **使用 ES6+ 语法**
2. **API 调用统一封装**在 `services/` 层
3. **避免直接操作 data**：使用 setData
4. **使用 MobX 管理全局状态**
5. **图片资源优化**：使用 webp 格式

### 性能优化

1. **分包加载**：已按业务模块分包
2. **按需加载组件**：`lazyCodeLoading: "requiredComponents"`
3. **合理使用 setData**：避免频繁更新
4. **使用自定义组件**：提高复用性

---

## 📅 更新日志

| 日期 | 版本 | 描述 |
|------|------|------|
| 2026-06-16 | - | AI 自动补充项目文档信息 |
| 2026-06-15 | - | 创建知识库文档 |

---

## 🔖 标签

#小程序 #微信小程序 #原生小程序 #MobX #TDesign #TypeScript #Andromeda系列 #SFA销售自动化 #高优先级 #维护中

---

## 相关链接

- [[01-索引/技术栈索引\|技术栈索引]]
- [[01-索引/项目总览\|项目总览]]
- [[问题记录\|问题记录]]
- [微信小程序官方文档](https://developers.weixin.qq.com/miniprogram/dev/framework/)
- [TDesign Miniprogram 文档](https://tdesign.tencent.com/miniprogram/overview)
- [MobX Miniprogram 文档](https://github.com/wechat-miniprogram/mobx-miniprogram)
