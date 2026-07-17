---
{"dg-publish":true,"permalink":"/05/liveup-doc/","dg-note-properties":{}}
---

# liveup-doc - 直播审核系统对接文档

> 直播审核系统第三方接入对接文档站点，基于 VuePress 1.x 构建

## 📋 项目信息

- **项目名称**：liveup-doc
- **项目类型**：技术文档站点
- **开发状态**：#维护中
- **技术负责人**：待填写
- **项目路径**：`/Users/dompling/WebstormProjects/Work/liveup-doc`
- **访问路径**：`/live-docs/`

---

## 🚀 快速启动

### 安装依赖
```bash
cd /Users/dompling/WebstormProjects/Work/liveup-doc
yarn install
```

### 本地开发
```bash
npm run dev
# 或 yarn dev
```
访问: `http://localhost:8080/live-docs/`

### 构建生产版本
```bash
npm run build
```
构建产物输出到 `./build` 目录

### 部署
```bash
npm run deploy
# 或 bash deploy.sh
```

---

## 🛠️ 技术栈

### 核心技术

- **文档框架**：VuePress 1.5.2
- **语言**：Markdown + Vue.js
- **包管理器**：Yarn
- **部署方式**：Jenkins CI/CD + Kubernetes

### 部署架构

- **CI/CD 工具**：Jenkins Pipeline
- **K8s 命名空间**：`liveup-dev`
- **应用名称**：`tpm-pc-manager-docs`
- **副本数**：1
- **Web 服务器**：Nginx (端口 80)

---

## 📂 项目结构

```
liveup-doc/
├── docs/                          # 文档源文件目录
│   ├── .vuepress/                 # VuePress 配置
│   │   ├── config.js              # 站点配置文件
│   │   ├── public/                # 静态资源
│   │   ├── styles/                # 样式文件
│   │   └── theme/                 # 主题定制
│   ├── assets/                    # 文档图片资源
│   │   └── ex1.png                # 示例图片
│   ├── README.md                  # 首页（Hero 页面）
│   ├── live.md                    # 服务端 API 文档 (3492 行)
│   ├── mini.md                    # 客户端 API 文档 (118 行)
│   └── form.md                    # 表单基础配置文档 (41 行)
├── nginx/                         # Nginx 配置
│   └── nginx.conf                 # 反向代理配置
├── Jenkinsfile                    # Jenkins CI/CD 配置
├── deploy.sh                      # 部署脚本
├── package.json                   # 项目配置
└── yarn.lock                      # 依赖锁定文件
```

---

## 📝 文档内容

### VuePress 配置

**站点配置** (`.vuepress/config.js`):
- **标题**: 直播审核系统
- **Base URL**: `/live-docs/`
- **输出目录**: `./build`
- **Logo**: `/logo.jpg`
- **侧边栏**: 自动生成模式

**导航栏**:
- 服务端 API (`/live`)
- 客户端 API (`/mini`)

### 文档结构

#### 1. **服务端 API 文档** (`live.md` - 3492 行)

**核心内容**:
- **快速接入**: appKey/appSecret 签名机制
  - 签名算法: MD5(`appKey` + `appSecret` + `requestBody` + `timestamp`)
  - Content-Type: `application/json;charset=utf-8`
  - 请求方式: POST

**环境地址**:

| 环境  | API 地址                          |
|-----|----------------------------------|
| 测试1 | https://api-ea-dev.jncapp.cn     |
| 测试2 | https://api-ea-uat.jncapp.cn     |
| 生产  | https://api-ea-prod.jncapp.cn    |

**接口列表**:
- 推送审核业务配置任务
- 推送凭证类任务 (单条/批量)
- 推送直播类任务 (单条/批量)
- 查询任务列表
- 查询任务详情
- 任务审核结果回调接口
- 下拉搜索接口配置
- 文件上传接口

#### 2. **客户端 API 文档** (`mini.md` - 118 行)

**跳转方式**:
- **小程序跳转小程序**: `wx.navigateToMiniProgram`
- **安卓跳转小程序**: `WXLaunchMiniProgram`
- **iOS 跳转小程序**: `WXLaunchMiniProgramReq`

**跳转参数**:
- `appId`: `wxb9a2dc4b989c7658`
- `path`: `pages/login/index`
- `extraData`:
  - `userCode`: 用户唯一编码 (必填)
  - `appKey`: 第三方公司唯一 Key (必填)
  - `pages`: 页面路径 (可选)
  - `system`: 系统来源 (可选，如 TPM、客情、宴会)

#### 3. **表单配置文档** (`form.md` - 41 行)

**基础配置字段**:
- 标题、字段名、提示文字
- 验证、互动

**特殊组件配置**:
- 下拉框/单选框/多选框: 选项配置、下拉搜索接口
- 关联字段: 与推送凭证类任务的 `base.item.code` 关联
- 日期: 日期类型、限制区间

---

## 🔧 开发规范

### 文档编写规范

1. **Markdown 格式**: 使用标准 Markdown 语法
2. **代码示例**: 使用代码块标注语言类型 (java/javascript/json)
3. **表格对齐**: 使用 HTML `<div align="center">` 居中对齐
4. **图片引用**: 统一放置在 `docs/assets/` 目录

### 接口文档规范

每个接口必须包含:
- 接口说明
- 请求方式 (POST/GET)
- 请求地址
- 请求参数表格 (字段/描述/类型/是否必填)
- 请求示例
- 响应参数说明
- 响应示例

---

## ⚠️ 注意事项

1. **签名机制**: 所有 API 请求需要在 Header 中携带 `timestamp`、`sign`、`appKey`
2. **环境隔离**: `appKey`、`appSecret`、`businessRelCode` 在每个环境独立申请
3. **请求格式**: 仅支持 POST 请求，Content-Type 为 `application/json;charset=utf-8`
4. **文档更新**: 修改文档后需重新构建并部署才能生效

---

## 📅 更新日志

| 日期 | 版本 | 描述 |
|------|------|------|
| 2025-05-28 | - | 最后一次更新 |
| 2026-06-16 | - | 补充完整项目文档 |
| 2026-06-15 | - | 创建知识库文档 |

---

## 🔖 标签

#文档项目 #文档站点 #VuePress #直播审核 #API文档 #维护中

---

## 相关链接

- [VuePress 官方文档](https://vuepress.vuejs.org/)
- [微信小程序跳转文档](https://developers.weixin.qq.com/miniprogram/dev/api/navigate/wx.navigateToMiniProgram.html)
- [[01-索引/技术栈索引\|技术栈索引]]
- [[01-索引/项目总览\|项目总览]]
