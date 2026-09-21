---
{"dg-publish":true,"dg-permalink":"umi-project-guide","permalink":"/umi-project-guide/","dg-note-properties":{"cssclasses":["wiki-page","wiki-article"]}}
---


# Umi项目开发指南

[[01-导航与索引/项目总览\|项目导航]] / [[06-研发规范/开发规范\|研发规范]] / Umi

按 Umi 主版本找到项目，再定位路由、运行时、请求和权限配置。共享组件约定见 [[06-研发规范/React项目规范\|React项目规范]]，项目版本汇总见 [[01-导航与索引/项目总览#技术栈\|技术栈]]。

> [!wiki-nav] 本页导航
> [[06-研发规范/Umi项目开发指南#适用项目\|按版本找项目]] · [[06-研发规范/Umi项目开发指南#常用约定\|配置入口]] · [[06-研发规范/Umi项目开发指南#升级建议\|升级检查]]

## 适用项目

### UmiJS Max 4

[[02-Web端项目/oms-web\|oms-web]] · [[02-Web端项目/jnc-bigdata-mgt-web\|jnc-bigdata-mgt-web]] · [[02-Web端项目/jnc-report-web\|jnc-report-web]] · [[02-Web端项目/tpm-merchant-wx\|tpm-merchant-wx]]

### UmiJS 4

[[02-Web端项目/bss-frontend\|bss-frontend]]

### UmiJS 3

[[02-Web端项目/pdm-web\|pdm-web]] · [[02-Web端项目/jnc-security-sac-frontend\|jnc-security-sac-frontend]] · [[02-Web端项目/jnc-audit-web\|jnc-audit-web]] · [[02-Web端项目/jnc-tpm-web\|jnc-tpm-web]]

## 常用约定

| 当前场景 | 优先查看 | 核对重点 |
| --- | --- | --- |
| 切换环境 | 启动脚本中的 `UMI_ENV` 与环境配置 | 命令实际选中的环境和接口地址 |
| 新增或调整页面 | `config/routes.ts` 或 `config/routes/` | 路由入口与页面位置 |
| 调整全局行为 | `src/app.tsx` | 运行时配置与初始化逻辑 |
| 调用 API | `src/services/` | 复用已有请求层与响应结构 |
| 页面或菜单权限 | `src/access.ts`、layout 配置和路由权限字段 | 当前主版本及项目已启用的能力 |

这些是常见入口，具体文件以项目现有结构为准；UmiJS 3、UmiJS 4 与 Max 4 的配置不能整份互换。

环境变量示例见 [[09-问题与记录/常见问题解决方案#问题 3：UmiJS 4 环境变量配置\|UmiJS 4 环境配置]]。

## 升级建议

- UmiJS 3 项目升级到 Max 4 前，先梳理路由、权限、layout、request 和 model 的兼容差异。
- Ant Design 4 项目升级到 5 前，先检查 Less 变量、主题定制和 Pro Components 版本。

版本迁移的待办和待核实项统一放在 [[01-导航与索引/项目维护\|项目维护]]。

## 相关链接

[[06-研发规范/开发规范\|命名与目录规范]] · [[06-研发规范/常用代码片段\|实现示例]]
