---
{"dg-publish":true,"permalink":"/02-web/bss-frontend/","dg-note-properties":{}}
---

# bss-frontend

> BSS 前端系统 - 业务支撑系统

## 📋 项目信息

- **项目名称**：bss-frontend
- **项目类型**：Web 前端应用
- **开发状态**：#进行中
- **技术负责人**：待填写
- **项目路径**：`/Users/dompling/WebstormProjects/Work/bss-frontend`

---

## 🛠️ 技术栈

### 核心技术

- **框架**：React 18 + UmiJS 4.0.50
- **UI 库**：Ant Design 5.13.1
- **移动端 UI**：Ant Design Mobile 5.32.0
- **Pro 组件**：@ant-design/pro-components 2.6.43
- **语言**：TypeScript 4.x
- **包管理**：npm

### 主要依赖

```json
{
  "@ant-design/charts": "1.4.3",        // 数据可视化
  "@ant-design/compatible": "5.1.2",    // 兼容组件
  "lodash": "4.17.21",                   // 工具库
  "moment": "2.29.4",                    // 日期处理
  "react-countup": "6.5.0",              // 数字动画
  "react-draggable": "4.4.5",            // 拖拽
  "react-resizable": "3.0.5",            // 可调整大小
  "react-to-print": "2.14.12"            // 打印功能
}
```

### 开发工具

- **代码格式化**：Prettier 2.x
- **Git Hooks**：Husky 8.x
- **代码检查**：lint-staged
- **构建工具**：UmiJS (基于 Vite)

---

## 📂 项目结构

```
bss-frontend/
├── .husky/              # Git hooks 配置
├── config/              # 项目配置
├── mock/                # Mock 数据
├── public/              # 静态资源
├── src/                 # 源代码
│   ├── components/      # 公共组件
│   ├── pages/           # 页面
│   ├── services/        # API 服务
│   ├── utils/           # 工具函数
│   └── ...
├── nginx/               # Nginx 配置
└── package.json
```

---

## 🚀 开发命令

### 启动项目

```bash
# 开发环境
npm run dev
# 或
npm start

# UAT 环境
npm run uat

# 生产环境
npm run prod
```

### 构建项目

```bash
# 开发环境构建
npm run build:dev

# UAT 环境构建
npm run build:uat

# 生产环境构建
npm run build
```

### 其他命令

```bash
# 格式化代码
npm run format

# 初始化设置
npm run setup
```

---

## 🌍 环境配置

项目使用 `UMI_ENV` 环境变量控制不同环境：

- **develop** - 开发环境
- **uat** - UAT 测试环境
- **product** - 生产环境

---

## 🔧 配置文件

### 多环境配置

UmiJS 支持多环境配置文件：
- `config/config.ts` - 基础配置
- `config/config.develop.ts` - 开发环境
- `config/config.uat.ts` - UAT 环境
- `config/config.product.ts` - 生产环境

---

## 📦 核心特性

### Pro 组件

项目使用 Ant Design Pro Components：
- **ProTable** - 高级表格
- **ProForm** - 高级表单
- **ProLayout** - 布局组件
- **ProCard** - 卡片组件

### 数据可视化

- 使用 `@ant-design/charts` 进行数据图表展示
- 支持多种图表类型（折线图、柱状图、饼图等）

### 移动端适配

- 集成 `antd-mobile` 支持移动端界面
- 响应式布局设计

### 动画效果

- `react-countup` - 数字滚动动画
- `rc-queue-anim` - 队列动画
- `rc-tween-one` - 补间动画

---

## 🔗 相关项目

- [[02-Web端项目/tpm-pc-manager\|tpm-pc-manager]] - TPM PC 管理系统
- [[02-Web端项目/jnc-dms-web\|jnc-dms-web]] - DMS Web 端

---

## 📝 开发规范

### 代码规范

1. **组件命名**：使用 PascalCase
2. **文件命名**：组件文件使用 PascalCase，工具文件使用 camelCase
3. **样式文件**：使用 CSS Modules 或 Less
4. **状态管理**：优先使用 UmiJS 的 Model

### Git 规范

项目配置了 Husky 和 lint-staged：
- 提交前自动格式化代码
- 提交前进行代码检查

### 提交信息规范

建议使用约定式提交：
```
feat: 新功能
fix: 修复 bug
docs: 文档更新
style: 代码格式调整
refactor: 重构
test: 测试相关
chore: 构建/工具链相关
```

---

## 🐛 常见问题

### 问题 1：依赖安装失败

```bash
# 清理缓存后重新安装
rm -rf node_modules package-lock.json
npm install
```

### 问题 2：UmiJS 配置不生效

```bash
# 重新运行 setup
npm run setup
```

---

## 📅 更新日志

| 日期 | 版本 | 描述 |
|------|------|------|
| 2026-06-15 | - | 创建知识库文档 |

---

## 🔖 标签

#前端 #Web端 #React-18 #UmiJS-4 #AntDesign-5 #AntDesignPro #TypeScript #BSS #业务支撑系统 #进行中

---

## 相关链接

- [[01-索引/技术栈索引\|技术栈索引]]
- [[01-索引/项目总览\|项目总览]]
