---
{"dg-publish":true,"permalink":"/02-web/jnc-tpm-react/","dg-note-properties":{}}
---

# jnc-tpm-react

> TPM React 项目 - 基于 React + Redux 的管理系统

---

## ⚡ 快速启动

```bash
# Node 版本
Node 11.x+（推荐 Node 16）

# 安装依赖
npm install

# 启动开发服务器
npm start

# 访问地址
http://localhost:3000（默认端口）
```

**其他常用命令：**
- 构建：`npm run build`
- 运行测试：`npm test`
- 主题配置：`npm run theme`

---

## 📋 项目信息

- **项目名称**：jnc-tpm-react (内部名: test)
- **项目类型**：Web 前端应用
- **开发状态**：#维护中
- **版本**：v0.1.0
- **项目路径**：`/Users/dompling/WebstormProjects/Work/jnc-tpm-react.`

---

## 🛠️ 技术栈

### 核心技术

- **框架**：React 16.13.1
- **UI 库**：Ant Design 4.23.1 + Ant Design Pro 组件
- **状态管理**：Redux 4.0 + Redux Thunk 2.3.0
- **路由**：React Router 5.0.1 / React Router DOM 4.3.1
- **语言**：JavaScript (支持 TypeScript)
- **构建工具**：Webpack 4.19.1（自定义配置）
- **包管理**：npm

### 主要依赖

**Ant Design Pro 组件：**
- `@ant-design/pro-form` 1.67.3 - 高级表单
- `@ant-design/pro-layout` 6.26.0 - 页面布局
- `@ant-design/pro-table` 2.7.4 - 高级表格
- `@ant-design/compatible` 1.0.2 - 兼容组件

**AWS 和腾讯云：**
- `aws-sdk` 2.802.0 - AWS SDK
- `cos-js-sdk-v5` 1.4.14 - 腾讯云对象存储

**工具库：**
- `lodash` 4.17.21 - 工具函数库
- `moment` 2.29.1 - 时间处理
- `axios` 0.18.0 - HTTP 客户端
- `qs` 6.12.0 - 查询字符串
- `crypto-js` 4.0.0 - 加密库
- `md5` 2.2.1 - MD5 加密

**数据可视化：**
- `echarts` 4.2.0-rc.1 - ECharts 图表
- `echarts-for-react` 2.0.15-beta.0 - React ECharts 封装
- `recharts` 1.3.3 - React 图表库

**富文本编辑器：**
- `react-draft-wysiwyg` 1.12.13 - 富文本编辑器
- `draftjs-to-html` 0.8.4 - Draft.js 转 HTML
- `draftjs-to-markdown` 0.5.1 - Draft.js 转 Markdown

**拖拽功能：**
- `react-dnd` 14.0.2 - 拖拽库
- `react-dnd-html5-backend` 14.0.0 - HTML5 拖拽后端

**其他：**
- `xlsx` 0.15.1 - Excel 处理
- `photoswipe` 4.1.2 + `react-viewer` 2.9.1 - 图片预览
- `react-color` 2.14.1 - 颜色选择器
- `react-qmap` 0.1.5 - 腾讯地图
- `jnc-utils` 0.2.13 - 剑南春工具库
- `json-bigint` 0.3.0 - 大整数处理

---

## 📂 项目结构

```text
jnc-tpm-react./
├── config/              # Webpack 配置
├── public/              # 静态资源
├── scripts/             # 构建脚本
│   ├── start.js        # 开发服务器
│   └── build.js        # 生产构建
├── src/
│   ├── components/      # 公共组件
│   ├── pages/           # 页面
│   ├── store/           # Redux store
│   ├── services/        # API 服务
│   ├── utils/           # 工具函数
│   └── ...
├── theme.js             # 主题配置
└── package.json
```

---

## 🎯 核心功能模块

### 1. TPM 管理
- 第三方支付平台管理
- 商户信息管理
- 交易数据统计

### 2. 数据可视化
- ECharts 图表
- Recharts 图表
- 实时数据看板

### 3. 富文本编辑
- Draft.js 编辑器
- HTML/Markdown 转换
- 内容管理

### 4. 文件处理
- Excel 导入导出
- 文件上传（腾讯云 COS / AWS S3）
- 图片预览

---

## 🔧 配置说明

### Webpack 配置

项目使用自定义 Webpack 配置：
- 位于 `config/` 目录
- 支持 Less 预处理器
- Babel 转译
- 代码分割

### Babel 配置

```json
{
  "presets": ["react-app"]
}
```

### 主题配置

运行 `npm run theme` 可以自定义 Ant Design 主题。

---

## 🌍 环境配置

**代理配置：**
- 开发环境代理：`http://52.83.134.63`（在 package.json 中配置）

---

## 🔗 相关项目

- [[02-Web端项目/tpm-pc-manager\|tpm-pc-manager]] - TPM PC 管理系统
- [[02-Web端项目/jnc-tpm-web\|jnc-tpm-web]] - TPM Web 端（UmiJS 版本）
- [[03-小程序项目/tpm-evidence-audit-wxapp\|tpm-evidence-audit-wxapp]] - TPM 证据审计小程序

---

## 🐛 常见问题

_暂无记录。遇到问题后会记录在 [[问题记录\|问题记录]] 中。_

---

## 📝 开发规范

### 组件开发

1. **使用 React Hooks**
2. **Props 类型检查**（可选 TypeScript）
3. **样式使用 Less**

### 状态管理

1. **Redux + Redux Thunk**
2. **模块化 reducer**
3. **异步操作统一封装**

---

## 📅 更新日志

| 日期 | 版本 | 描述 |
|------|------|------|
| 2026-06-16 | v0.1.0 | AI 自动补充项目文档信息 |
| 2026-06-15 | - | 创建知识库文档 |

---

## 🔖 标签

#前端 #Web端 #React-16 #Webpack #AntDesign-4 #Redux #腾讯云 #腾讯云COS #TPM系列 #支付管理 #ECharts #需要升级 #维护中

---

## 相关链接

- [[01-索引/技术栈索引\|技术栈索引]]
- [[01-索引/项目总览\|项目总览]]
- [[问题记录\|问题记录]]
