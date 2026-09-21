---
{"dg-publish":true,"dg-permalink":"obsidian-guide","permalink":"/obsidian-guide/","dg-note-properties":{"permalink":"/obsidian-guide/","cssclasses":["wiki-page","wiki-article"]}}
---


# Obsidian插件配置指南

[[01-导航与索引/项目总览\|项目导航]] / 知识库指南 / 插件配置

Dataview 展示项目数据，Templater 和 QuickAdd 提供记录入口。普通阅读可直接使用笔记链接；自动查询与模板动作按需启用。日常入口统一放在 [[01-导航与索引/项目总览\|项目导航]]。

| 需要的能力 | 插件 | 对应说明 |
| --- | --- | --- |
| 项目统计与分组 | Dataview | [[08-知识库指南/Obsidian插件配置指南#Dataview\|#Dataview]] |
| 日期、属性与文档模板 | Templater | [[08-知识库指南/Obsidian插件配置指南#Templater\|#Templater]] |
| 快速创建记录 | QuickAdd | [[08-知识库指南/Obsidian插件配置指南#QuickAdd\|#QuickAdd]] |
| 工具栏快捷按钮 | Commander，可选 | [[08-知识库指南/Obsidian插件配置指南#Commander\|#Commander]] |

## 必需插件

以下插件用于本库已有的自动查询和模板功能。

### Dataview

驱动 [[01-导航与索引/项目总览\|项目总览]] 中的目录统计与自动项目清单，以及 [[01-导航与索引/项目维护\|项目维护]] 中的最近更新和日记。框架与技术分类统一见 [[01-导航与索引/项目总览#技术栈\|技术栈]]。

- JavaScript 查询：按需开启。
- 默认刷新：保持默认即可。

### Templater

使用 `templates/` 下的项目文档、问题记录和日记模板，自动插入日期、文件名和光标占位。

| 配置项 | 建议值 |
| --- | --- |
| Template folder location | `templates` |
| Trigger Templater on new file creation | 按需开启 |

常用模板：[[templates/新建项目文档\|新建项目文档]] · [[templates/问题记录模板\|问题记录]] · [[templates/每日日记模板\|每日日记]]。

## 可选插件

### QuickAdd

仓库已保存以下 Choice；在新环境启用插件后，先检查目标文件与模板，再按个人习惯设置快捷键。

| Choice | 类型 | 保存位置或模板 |
| --- | --- | --- |
| 🐛 记一笔问题 | Capture | `09-问题与记录/问题记录.md` |
| 🌙 今日日记 | Template | `templates/每日日记模板.md` → `Daily/日期.md` |
| 📁 新建项目文档 | Template | `templates/新建项目文档.md` → 选择项目所属目录 |

Capture 格式包含日期、项目、问题和方案；当前配置不含更新记录计数的脚本。新增后需核对 [[09-问题与记录/问题记录\|问题记录]] 中的计数，CLI `kb-add` 的计数行为见 [[scripts/README\|脚本说明]]。

具体操作见 [[08-知识库指南/优化工作流程指南#配置 QuickAdd 插件\|QuickAdd 配置示例]]。

### Commander

把常用命令放到工具栏，例如打开项目导航、插入模板和全局搜索。配置示例见 [[08-知识库指南/优化工作流程指南#配置 Commander 插件（可选）\|Commander 配置示例]]。

## 当前配置注意

仓库包含 `.obsidian/community-plugins.json` 和社区插件文件。当前清单有 Calendar、Dataview、Excalidraw、Kanban、QuickAdd、Templater、Digital Garden；Commander 未列入当前启用清单。

首次在新环境打开 vault 时，仍需检查社区插件是否启用，以及模板目录、快捷键和 CSS 代码片段是否生效。阅读样式说明见 [[08-知识库指南/维护计划/知识库更新计划#使用与样式\|使用与样式]]。

## 相关链接

[[08-知识库指南/优化工作流程指南\|日常使用流程]] · [[08-知识库指南/知识库主动调用指南\|知识检索约定]]
