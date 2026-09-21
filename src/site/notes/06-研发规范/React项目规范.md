---
{"dg-publish":true,"dg-permalink":"react-project-standards","permalink":"/react-project-standards/","dg-note-properties":{"cssclasses":["wiki-page","wiki-article"]}}
---


# React项目规范

[[01-导航与索引/项目总览\|项目导航]] / [[06-研发规范/开发规范\|研发规范]] / React

React 项目的通用开发约定。具体版本、启动命令和特殊实现以项目页及源码为准；框架配置可继续查看 [[06-研发规范/Umi项目开发指南\|Umi项目开发指南]]。

## 适用项目

| 项目入口 | 查阅范围 |
| --- | --- |
| [[02-Web端项目/andromeda-web\|andromeda-web]] · [[02-Web端项目/bss-frontend\|bss-frontend]] | 页面、组件与服务层约定 |
| [[02-Web端项目/jnc-bigdata-mgt-web\|jnc-bigdata-mgt-web]] · [[02-Web端项目/jnc-report-web\|jnc-report-web]] | 管理后台与报表页面 |
| [[02-Web端项目/oms-web\|oms-web]] · [[02-Web端项目/tpm-merchant-wx\|tpm-merchant-wx]] | 业务页面与表单复用 |
| [[01-导航与索引/项目总览#技术栈\|React 16 / 17 项目]] | 按已有版本评估兼容性 |

## 基本约定

| 场景 | 约定 |
| --- | --- |
| 组件 | 新增组件使用函数式组件和 Hooks；现有组件先沿用所在项目的实现约定 |
| 业务页面 | 放在 `src/pages/`，公共组件放在 `src/components/` |
| API 调用 | 统一放在 `src/services/` 或项目既有服务层 |
| 复杂表格、表单 | 项目已使用 Ant Design Pro Components 时优先复用现有封装 |
| 类型定义 | 优先放在邻近模块的类型文件中，避免散落在实现文件 |

需要实现示例时，查看 [[06-研发规范/常用代码片段#React Hooks\|React Hooks]]、[[06-研发规范/常用代码片段#Ant Design 常用组件\|表格与表单]] 和 [[06-研发规范/常用代码片段#TypeScript 类型定义\|类型定义]]。

## 升级注意

按需求选择迁移范围：只调整页面时先复用现有组件和请求层；确需升级 React 16 项目时，先确认：

- 路由和状态管理是否依赖旧生命周期行为。
- Ant Design 4 到 5 的样式 token 和兼容 API。
- Webpack 4 项目的构建兼容性；Vite 或 UmiJS Max 的迁移范围单独评估。

升级待办统一查看 [[01-导航与索引/项目维护\|项目维护]]；操作示例见 [[09-问题与记录/常见问题解决方案#问题 1：React 16 升级到 React 18\|React 18 迁移参考]]。

## 相关链接

[[06-研发规范/开发规范\|命名与目录规范]] · [[01-导航与索引/项目总览\|项目导航]]
