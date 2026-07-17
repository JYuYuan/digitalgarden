---
{"dg-publish":true,"permalink":"/01/umi/","dg-note-properties":{}}
---

# Umi项目开发指南

> UmiJS / UmiJS Max 项目的统一开发入口。

---

## 适用项目

### UmiJS Max 4

- [[02-Web端项目/oms-web\|oms-web]]
- [[02-Web端项目/jnc-bigdata-mgt-web\|jnc-bigdata-mgt-web]]
- [[02-Web端项目/jnc-report-web\|jnc-report-web]]
- [[02-Web端项目/tpm-merchant-wx\|tpm-merchant-wx]]

### UmiJS 4

- [[02-Web端项目/bss-frontend\|bss-frontend]]

### UmiJS 3

- [[02-Web端项目/pdm-web\|pdm-web]]
- [[02-Web端项目/jnc-security-sac-frontend\|jnc-security-sac-frontend]]
- [[02-Web端项目/jnc-audit-web\|jnc-audit-web]]
- [[02-Web端项目/jnc-tpm-web\|jnc-tpm-web]]

---

## 常用约定

- 多环境通过 `UMI_ENV` 控制。
- 路由配置优先查看 `config/routes.ts` 或 `config/routes/`。
- 运行时配置优先查看 `src/app.tsx`。
- API 服务优先查看 `src/services/`。
- 权限控制优先查看 `src/access.ts`、layout 配置和路由权限字段。

---

## 升级建议

- UmiJS 3 项目升级到 Max 4 前，先梳理路由、权限、layout、request 和 model 的兼容差异。
- Ant Design 4 项目升级到 5 前，先检查 Less 变量、主题定制和 Pro Components 版本。

---

## 相关链接

- [[01-索引/技术栈索引\|技术栈索引]]
- [[01-索引/React项目规范\|React项目规范]]
- [[01-索引/开发规范\|开发规范]]
