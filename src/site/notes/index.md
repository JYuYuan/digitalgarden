---
{"dg-publish":true,"permalink":"/index/","hideInFiletree":true,"tags":["gardenEntry"],"dg-note-properties":{"cssclasses":["wiki-page","wiki-home"]}}
---


# JNC Wiki

> [!wiki-hero] 项目、规范与经验，都在这里。
> **28 个项目 · 5 类工程**，从开发到发布的工作知识库。
>
> 本次补录：[[10-后端与数据项目/flink-pipline\|flink-pipline]] · [[10-后端与数据项目/redshift\|redshift]] · [[10-后端与数据项目/tpm-report-export\|tpm-report-export]]

> [!wiki-stats] 项目分布
> | Web 端 | 小程序 | 移动端 | 文档项目 | 后端与数据 |
> | :---: | :---: | :---: | :---: | :---: |
> | **15** | **5** | **2** | **3** | **3** |

## 常用入口

> [!wiki-grid] 工作导航
> > [!compass] 开始工作
> > - [[01-导航与索引/项目维护\|项目维护]] · 查看项目动态与升级状态
> > - [[01-导航与索引/项目总览#快速搜索\|快速搜索]] · 按名称或标签定位内容
> > - [[09-问题与记录/问题记录\|问题记录]] · 回查与沉淀开发问题
>
> > [!folder-open] 找项目
> > - [[01-导航与索引/项目总览\|项目总览]] · 28 个项目的完整清单
> > - [[01-导航与索引/项目关系图\|项目关系图]] · 业务关系与数据链路
> > - [[01-导航与索引/项目总览#技术栈\|技术栈]] · 框架、版本与工具对比
>
> > [!code] 开发规范
> > - [[06-研发规范/开发规范\|开发规范]] · 通用开发约定
> > - [[06-研发规范/React项目规范\|React项目规范]] · [[06-研发规范/Umi项目开发指南\|Umi项目开发指南]]
> > - [[06-研发规范/常用代码片段\|常用代码片段]] · 高频代码模板
>
> > [!rocket] 运维与发布
> > - [[07-运维与发布/通用/Git分支规范\|Git分支规范]] · [[07-运维与发布/通用/Jenkins部署规则\|Jenkins部署规则]]
> > - [[07-运维与发布/发布流程/小程序发版\|小程序发版]] · [[07-运维与发布/发布流程/SF直播App发布流程\|SF直播App发布流程]]
> > - [[07-运维与发布/专项/额度池/额度池新增缺失表处理流程\|额度池新增缺失表处理流程]] · 数据链路专项

## 项目入口

| 平台 | 适合从这里找 | 项目入口 |
| --- | --- | --- |
| **Web 端 · 15** | 业务管理、订单、报表与权限 | [[02-Web端项目/andromeda-web\|andromeda-web]] · [[02-Web端项目/jnc-dms-web\|jnc-dms-web]] · [[02-Web端项目/jnc-tpm-web\|jnc-tpm-web]] · [[02-Web端项目/oms-web\|oms-web]] |
| **小程序 · 5** | 移动销售、稽核、证据审计与自动化测试 | [[03-小程序项目/andromeda-wx\|andromeda-wx]] · [[03-小程序项目/jnc-dms-wx\|jnc-dms-wx]] · [[03-小程序项目/jnc-audit-wx\|jnc-audit-wx]] · [[03-小程序项目/tpm-evidence-audit-wxapp\|tpm-evidence-audit-wxapp]] · [[03-小程序项目/wechatTest\|wechatTest]] |
| **移动端 · 2** | Android 审计与历史双端直播工程 | [[04-移动端项目/tpm-evidence-audit-android\|tpm-evidence-audit-android]] · [[04-移动端项目/XiaoZhiBo\|XiaoZhiBo]] |
| **文档项目 · 3** | 接口文档、Axure 原型与方案 | [[05-文档项目/liveup-doc\|liveup-doc]] · [[05-文档项目/7-3\|7-3]] · [[05-文档项目/8-2\|8-2]] |
| **后端与数据 · 3** | CDC、数仓加工与报表导出 | [[10-后端与数据项目/flink-pipline\|flink-pipline]] · [[10-后端与数据项目/redshift\|redshift]] · [[10-后端与数据项目/tpm-report-export\|tpm-report-export]] |

> [!tip] 查看完整清单
> [[01-导航与索引/项目总览\|项目总览]] 提供完整清单和自动统计；[[01-导航与索引/项目维护\|项目维护]] 查看近期修改与升级待办。

## 本次补录

| 项目 | 用途 | 从哪里开始 |
| --- | --- | --- |
| [[10-后端与数据项目/flink-pipline\|flink-pipline]] | Flink CDC 作业配置与配套工具 | 数据源配置、表映射、部署约定 |
| [[10-后端与数据项目/redshift\|redshift]] | SQL / Python 数仓与数据流水线 | 数据分层、脚本目录、额度池链路 |
| [[10-后端与数据项目/tpm-report-export\|tpm-report-export]] | Java 报表导出服务 | 导出任务、类型映射、文件交付 |

## 高频业务系统

> [!wiki-grid] 业务系统
> > [!note] Andromeda · SFA 销售自动化
> > [[02-Web端项目/andromeda-web\|Web 管理端]] · [[03-小程序项目/andromeda-wx\|销售端小程序]]
>
> > [!note] TPM · 管理、审计与导出
> > [[02-Web端项目/tpm-pc-manager\|tpm-pc-manager]] · [[02-Web端项目/jnc-tpm-web\|jnc-tpm-web]] · [[02-Web端项目/jnc-tpm-react\|jnc-tpm-react]] · [[02-Web端项目/tpm-merchant-wx\|tpm-merchant-wx]]
> >
> > [[03-小程序项目/tpm-evidence-audit-wxapp\|tpm-evidence-audit-wxapp]] · [[04-移动端项目/tpm-evidence-audit-android\|tpm-evidence-audit-android]] · [[10-后端与数据项目/tpm-report-export\|tpm-report-export]]
>
> > [!note] DMS · 分销管理
> > [[02-Web端项目/jnc-dms-web\|Web 管理端]] · [[03-小程序项目/jnc-dms-wx\|分销小程序]]
>
> > [!note] 审计 · 稽核业务
> > [[02-Web端项目/jnc-audit-web\|审计 Web]] · [[03-小程序项目/jnc-audit-wx\|审计小程序]]

## 按工作场景找文档

| 现在要做的事 | 推荐路径 |
| --- | --- |
| **开始开发** | [[01-导航与索引/项目总览\|项目总览]] → 项目文档的启动说明 → [[06-研发规范/开发规范\|开发规范]] |
| **发布或部署** | [[07-运维与发布/通用/Git分支规范\|Git分支规范]] → [[07-运维与发布/通用/Jenkins部署规则\|Jenkins部署规则]] → 对应发版流程 |
| **排查问题** | [[09-问题与记录/常见问题解决方案\|常见问题解决方案]] → [[09-问题与记录/问题记录\|问题记录]] → 解决后记录 |
| **处理数据与导出** | [[10-后端与数据项目/flink-pipline\|flink-pipline]] / [[10-后端与数据项目/redshift\|redshift]] / [[10-后端与数据项目/tpm-report-export\|tpm-report-export]] → 具体配置与任务 |
| **维护知识库** | [[08-知识库指南/优化工作流程指南\|优化工作流程指南]] → [[08-知识库指南/Obsidian插件配置指南\|Obsidian插件配置指南]] → [[08-知识库指南/维护计划/知识库更新计划\|知识库更新计划]] |

## 知识库导航图

> [!info]- 展开查看目录关系
> ```mermaid
> flowchart LR
>     A["JNC Wiki"] --> B["导航与索引"]
>     A --> C["项目文档 · 28"]
>     A --> D["研发规范"]
>     A --> E["运维与发布"]
>     A --> F["知识库指南 / 问题记录"]
>     C --> C1["Web 15 / 小程序 5"]
>     C --> C2["移动端 2 / 文档 3"]
>     C --> C3["后端与数据 3"]
> ```

## 技术概览

React / Vue / Taro 覆盖前端与跨端工程，Java / Flink / SQL / Python 覆盖服务端和数据处理。具体版本与项目映射见 [[01-导航与索引/项目总览#技术栈\|技术栈]]。

## 知识库使用说明

> [!info]- 内容应该放在哪里
> - **临时笔记**：`00-收件箱`，整理后归档。
> - **项目资料**：`02～05` 对应前端、移动端和文档项目；`10-后端与数据项目` 收录服务端与数据工程。
> - **研发与运维**：`06-研发规范`、`07-运维与发布`。
> - **使用指南与问题**：`08-知识库指南`、`09-问题与记录`。
> - **敏感资料**：`99-私有`，不发布到 Web。
>
> 需要 AI 调用知识库时，参阅 [[08-知识库指南/知识库主动调用指南\|知识库主动调用指南]]。

---

从 [[01-导航与索引/项目总览\|项目总览]] 开始工作，或按 `Cmd/Ctrl + O` 直接打开项目。 · 更新于 **2026-09-21**
