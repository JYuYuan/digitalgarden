---
{"dg-publish":true,"permalink":"/scripts/readme/","dg-note-properties":{}}
---

# 知识库工具脚本

这个目录包含用于知识库管理的命令行工具。

## kb-add - 问题快速记录工具

快速记录开发中遇到的问题和解决方案。

### 安装

将此脚本添加到你的 PATH，或创建软链接：

```bash
# 方法 1：添加到 PATH（在 ~/.zshrc 或 ~/.bashrc 中添加）
export PATH="$PATH:/Users/dompling/WebstormProjects/Work/.obsidian-vault/scripts"

# 方法 2：创建软链接
sudo ln -s /Users/dompling/WebstormProjects/Work/.obsidian-vault/scripts/kb-add /usr/local/bin/kb-add

# 重新加载配置
source ~/.zshrc  # 或 source ~/.bashrc
```

### 用法

**快速记录模式：**
```bash
kb-add "npm install 报 EACCES 错误" "sudo chown -R $USER ~/.npm"
```

**管道模式（捕获命令输出）：**
```bash
npm install 2>&1 | kb-add
```

**查看帮助：**
```bash
kb-add --help
```

### 特性

- ✅ 自动识别当前 git 仓库对应的项目
- ✅ 自动生成时间戳
- ✅ 自动追加到 `问题记录.md` 文件顶部
- ✅ 自动更新记录计数
- ✅ 达到 50 条自动提醒归档

### 示例

```bash
# 在 andromeda-web 项目目录下
cd /Users/dompling/WebstormProjects/Work/andromeda-web

# 记录一个问题
kb-add "Vite 启动报端口占用" "kill -9 $(lsof -t -i:8000)"

# 捕获错误信息
npm run build 2>&1 | kb-add
```

---

## kb-daily - 每日知识库自动汇总工具

自动汇总当天的开发痕迹，生成带双链的日记。脚本负责「机械采集」，AI 负责「提炼血肉」。

### 用法

```bash
kb-daily                  # 汇总「今天」，生成 Daily/YYYY-MM-DD.md
kb-daily 2026-06-15       # 汇总指定日期
kb-daily --print          # 只打印到终端，不写文件（安全预览）
kb-daily --force          # 覆盖已存在的当日日记（默认绝不覆盖）
kb-daily --all-authors    # 抓取所有作者的提交（默认只抓你本人）
kb-daily --help           # 查看帮助
```

### 工作内容

1. 扫描 7 个项目当天**你本人**的 git 提交（按各仓库 `user.email` 过滤）
2. 抓取 `问题记录.md` 中当日新增的条目
3. 生成对齐「每日日记模板」的骨架，自动补 `[[双链]]` 与 frontmatter（供 Dataview 聚合）

### 特性

- ✅ 已存在的日记**绝不静默覆盖**（保护手写内容，需 `--force` 才覆盖）
- ✅ `--print` 安全预览，先看后写
- ✅ 日期严格校验、子进程参数数组调用，杜绝 shell 注入
- ✅ 任一项目采集失败都不中断整体（优雅降级）

### 推荐工作流（L2 半自动）

```bash
# 1. 下班前采集骨架
kb-daily

# 2. 对 Claude Code 说一句
你：润色今天的日记
我：【读取骨架 → 归纳工作主线 → 提炼今日收获 → 写回文件】
```

### 示例

```bash
# 先预览今天的采集结果
kb-daily --print

# 确认无误后正式生成
kb-daily

# 补记昨天忘了写的日记
kb-daily 2026-06-16
```

---

## 未来计划

- `kb-search` - 搜索问题记录
- `kb-archive` - 手动触发归档
- `kb-stats` - 显示统计信息
