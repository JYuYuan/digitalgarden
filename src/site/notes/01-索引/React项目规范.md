---
{"dg-publish":true,"permalink":"/01/react/","dg-note-properties":{}}
---

# React项目规范

> React 项目的通用开发约定，作为各项目页的轻量索引入口。

---

## 适用项目

- [[02-Web端项目/andromeda-web\|andromeda-web]]
- [[02-Web端项目/bss-frontend\|bss-frontend]]
- [[02-Web端项目/jnc-bigdata-mgt-web\|jnc-bigdata-mgt-web]]
- [[02-Web端项目/jnc-report-web\|jnc-report-web]]
- [[02-Web端项目/oms-web\|oms-web]]
- [[02-Web端项目/tpm-merchant-wx\|tpm-merchant-wx]]
- React 16/17 旧项目：见 [[01-索引/技术栈索引\|技术栈索引]]

---

## 基本约定

- 组件使用函数式组件和 Hooks。
- 业务页面放在 `src/pages/`，公共组件放在 `src/components/`。
- API 调用统一放在 `src/services/` 或项目既有服务层。
- 复杂表格、表单优先复用 Ant Design Pro Components。
- 新增类型优先放在邻近模块的类型文件中，避免散落在实现文件。

---

## 升级注意

React 16 项目升级前需先确认：
- 路由和状态管理是否依赖旧生命周期行为。
- Ant Design 4 到 5 的样式 token 和兼容 API。
- Webpack 4 项目是否适合先迁移到 Vite 或 UmiJS Max。

---

## 相关链接

- [[01-索引/技术栈索引\|技术栈索引]]
- [[01-索引/开发规范\|开发规范]]
- [[01-索引/常见问题解决方案\|常见问题解决方案]]
