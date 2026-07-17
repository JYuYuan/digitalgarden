---
{"dg-publish":true,"permalink":"/07/obsidian/","dg-note-properties":{}}
---

# Obsidian插件配置指南

> 本知识库依赖少量 Obsidian 社区插件提升检索、模板和仪表板能力。

---

## 必需插件

### Dataview

用途：
- 驱动 [[00-仪表板\|00-仪表板]] 中的项目统计、标签分组和项目列表。
- 按 `#Web端`、`#小程序`、`#React-18` 等标签生成动态视图。

建议配置：
- 启用 JavaScript 查询：按需开启。
- 默认刷新：保持默认即可。

### Templater

用途：
- 使用 `templates/` 下的项目文档、问题记录和日记模板。
- 自动插入日期、文件名和光标占位。

建议配置：
- Template folder location：`templates`
- Trigger Templater on new file creation：按需开启。

---

## 可选插件

### QuickAdd

用途：
- 快速创建问题记录、日记或项目文档。

建议：
- 为问题记录模板配置一个 Capture 或 Template choice。
- 可绑定快捷键到 `Cmd/Ctrl + Shift + P`。

### Commander

用途：
- 把常用命令放到工具栏，例如打开仪表板、插入模板、全局搜索。

---

## 当前配置注意

当前仓库内 `.obsidian/` 只提交了核心插件配置，未提交社区插件启用清单。首次打开 vault 后需要在 Obsidian 内手动安装并启用上述社区插件。

---

## 相关链接

- [[07-指南文档/优化工作流程指南\|优化工作流程指南]]
- [[00-仪表板\|00-仪表板]]
- [[01-索引/快速导航\|快速导航]]
