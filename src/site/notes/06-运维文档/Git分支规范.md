---
{"dg-publish":true,"permalink":"/06/git/","dg-note-properties":{}}
---

# Git 分支规范

> 项目 Git 分支管理规范和最佳实践

---

## 🌿 标准分支结构

### 三大主分支

```
dev           # 开发环境分支
uat           # UAT/测试环境分支
prod_release  # 生产环境分支
```

**说明：**
- 这三个分支是**长期分支**，不可删除
- 每个分支对应一个部署环境
- 所有功能开发都基于这些分支创建临时分支

---

## 📋 分支命名规范

### 功能分支命名

**格式：**
```
姓名拼音缩写/需求名称（中文）

示例：
jyy/用户登录功能        # 江洋洋开发用户登录功能
lm/支付问题修复         # 李明修复支付问题
wh/订单列表优化         # 王慧优化订单列表
```

**规则：**
- 姓名拼音缩写使用小写（如：jyy、lm、wh）
- 需求名称使用中文描述
- 尽量简短且具有描述性
- **使用中文便于发版登记和统计**

**命名示例：**
```
✅ jyy/用户登录功能
✅ lm/支付金额修复
✅ wh/订单管理模块

❌ jiangyangyang/用户登录  # 拼音太长
❌ jyy/user-login         # 不要用英文
❌ JYY/用户登录           # 不要用大写
```

## 🔄 分支创建规则

### 核心原则

**所有分支都从生产分支创建**

**标准项目（从 `prod_release` 创建）：**
```bash
# 1. 切换到生产分支
git checkout prod_release

# 2. 拉取最新代码
git pull origin prod_release

# 3. 创建功能分支
git checkout -b jyy/用户登录功能

# 4. 推送到远程
git push origin jyy/用户登录功能
```

**TPM 证据审计 Android（从 `sf_release` 创建）：**
```bash
# 1. 切换到生产分支
git checkout sf_release

# 2. 拉取最新代码
git pull origin sf_release

# 3. 创建功能分支
git checkout -b lm/相机修复

# 4. 推送到远程
git push origin lm/相机修复
```

**为什么从生产分支创建？**
- ✅ 确保代码基于最稳定版本
- ✅ 避免包含其他开发中的功能
- ✅ 减少合并冲突
- ✅ 保证代码质量

---

## 🔀 完整工作流程

### 开发流程（包含 Commit 合并）

```bash
# 1. 从生产分支创建功能分支
git checkout prod_release
git pull origin prod_release
git checkout -b jyy/用户登录功能

# 2. 开发功能（多次提交）
git add .
git commit -m "feat: 添加登录页面"
# ... 继续开发 ...
git add .
git commit -m "feat: 添加登录接口"
# ... 继续开发 ...
git add .
git commit -m "fix: 修复登录验证逻辑"

# 3. 推送到远程
git push origin jyy/用户登录功能

# 4. 发版前：合并多个 commit 为一个 ⚠️ 重要步骤
# 方式 1：使用 IDE（推荐）
# - WebStorm/IDEA: 右键 commit → Interactively Rebase from Here
# - 选择多个 commit → Squash 合并为一个
# - 编辑最终的 commit message

# 方式 2：使用命令行
git rebase -i HEAD~3  # 合并最近 3 个 commit
# 在编辑器中将后面的 pick 改为 squash 或 s
# 保存后编辑最终的 commit message

# 5. 强制推送（合并 commit 后）
git push -f origin jyy/用户登录功能

# 6. 合并到 dev 分支（开发环境测试）
git checkout dev
git pull origin dev
git merge jyy/用户登录功能
git push origin dev

# 7. 测试通过后，合并到 uat 分支（UAT 测试）
git checkout uat
git pull origin uat
git merge jyy/用户登录功能
git push origin uat

# 8. UAT 测试通过后，合并到 prod_release（生产发布）
git checkout prod_release
git pull origin prod_release
git merge jyy/用户登录功能
git push origin prod_release

# 9. 删除功能分支（可选）
git branch -d jyy/用户登录功能
git push origin --delete jyy/用户登录功能
```

---

### 为什么要合并 Commit？

**目的：**
1. ✅ **便于发版登记** - 一个 commit 清晰记录整个需求
2. ✅ **统计受影响文件** - 一次性查看所有变更文件
3. ✅ **简化历史记录** - 避免过多的中间提交
4. ✅ **方便回滚** - 整个需求作为一个单元

**示例对比：**

**合并前（多个 commit）：**
```
feat: 添加登录页面
feat: 添加登录接口
fix: 修复验证逻辑
fix: 修复样式问题
docs: 更新文档
```

**合并后（一个 commit）：**
```
feat: 用户登录功能

- 添加登录页面
- 添加登录接口
- 完善验证逻辑
- 修复样式问题
- 更新文档

受影响的文件：
- src/pages/Login/index.tsx
- src/services/auth.ts
- src/utils/validate.ts
```

---

## 📊 分支流转图

### 标准项目

```
prod_release (生产)
    ↓ 创建功能分支
jyy/用户登录功能 (功能开发)
    ↓ 开发完成（多次 commit）
    ↓ 合并 commit 为一个 ⚠️
    ↓ 合并到
dev (开发环境测试)
    ↓ 测试通过
    ↓ 合并到
uat (UAT 测试)
    ↓ 测试通过
    ↓ 合并到
prod_release (发布生产)
```

---

### TPM 证据审计 Android

```
sf_release (生产)
    ↓ 创建功能分支
lm/相机修复 (功能开发)
    ↓ 开发完成（多次 commit）
    ↓ 合并 commit 为一个 ⚠️
    ↓ 合并到
sf_uat (UAT 测试)
    ↓ 测试通过
    ↓ 合并到
sf_release (发布生产)
```

---

### DMS Web（master 作为开发分支）

```
prod_release (生产)
    ↓ 创建功能分支
wh/订单模块 (功能开发)
    ↓ 开发完成（多次 commit）
    ↓ 合并 commit 为一个 ⚠️
    ↓ 合并到
master (开发环境测试) ⚠️ 注意：master 是开发分支
    ↓ 测试通过
    ↓ 合并到
uat (UAT 测试)
    ↓ 测试通过
    ↓ 合并到
prod_release (发布生产)
```

---

## 📊 项目分支对照表

| 项目 | 开发分支 | UAT 分支 | 生产分支 | 创建分支来源 |
|------|---------|----------|----------|------------|
| 标准项目 | `dev` | `uat` | `prod_release` | `prod_release` |
| TPM 证据审计 Android | - | `sf_uat` | `sf_release` | `sf_release` |
| DMS Web | `master` ⚠️ | `uat` | `prod_release` | `prod_release` |

**注意：**
- ⚠️ DMS Web 的 `master` 是**开发分支**，不是生产分支
- 所有功能分支都从**生产分支**创建（`prod_release` 或 `sf_release`）

---

## 🎯 不同场景的分支管理

### 场景 1：新功能开发（含 Commit 合并）

```bash
# 1. 创建功能分支
git checkout prod_release
git pull origin prod_release
git checkout -b jyy/订单列表功能

# 2. 开发过程中多次提交
git commit -m "feat: 添加订单列表页面"
git commit -m "feat: 添加订单筛选"
git commit -m "fix: 修复列表样式"

# 3. 发版前合并 commit
# 使用 IDE: 右键最早的 commit → Interactively Rebase from Here
# 将所有 commit 合并为一个

# 4. 强制推送
git push -f origin jyy/订单列表功能

# 5. 合并到各环境
# dev → uat → prod_release
```

---

### 场景 2：Bug 修复

```bash
# 创建修复分支
git checkout prod_release
git pull origin prod_release
git checkout -b lm/支付金额修复

# 修复后合并 commit，再按流程合并
```

---

### 场景 3：紧急热修复

```bash
# 从生产分支创建
git checkout prod_release
git pull origin prod_release
git checkout -b wh/安全漏洞修复

# 修复后合并 commit
git rebase -i HEAD~2

# 直接合并到 prod_release
git checkout prod_release
git merge wh/安全漏洞修复
git push origin prod_release

# 然后同步到其他分支
git checkout uat
git merge prod_release
git push origin uat

git checkout dev
git merge prod_release
git push origin dev
```

---

### 场景 4：多人协作

```bash
# 开发者 A 创建分支
git checkout prod_release
git checkout -b zs/order-module

# 开发者 B 需要在此基础上开发
git checkout zs/order-module
git checkout -b ls/order-detail

# 开发完成后，先合并 B 的分支到 A 的分支
git checkout zs/order-module
git merge ls/order-detail

# 再按正常流程合并到 dev/uat/prod_release
```

---

## ⚠️ 特殊说明

### 特定项目的分支差异

**注意：** 某些项目可能有不同的分支结构，例如：

**标准项目（三分支）：**
```
dev           # 开发环境
uat           # UAT 环境
prod_release  # 生产环境
```

**TPM 证据审计 Android（tpm-evidence-audit-android）：**
```
sf_uat        # UAT 环境
sf_release    # 生产环境
```

**DMS Web（dms-web / jnc-dms-web）：**
```
master        # 开发环境（相当于 dev）
uat           # UAT 环境
prod_release  # 生产环境
```
**注意：** dms-web 的 `master` 分支作为开发分支使用，不是生产分支！

**其他可能的分支结构：**

**两分支项目：**
```
dev
prod_release
```

**多环境项目：**
```
dev
test
uat
prod_release
```

**查看项目分支：**
```bash
# 查看所有远程分支
git branch -r

# 查看本地和远程所有分支
git branch -a

# 示例输出（tpm-evidence-audit-android）
origin/sf_uat
origin/sf_release

# 示例输出（dms-web）
origin/master        # 开发分支
origin/uat
origin/prod_release
```

**建议：** 加入新项目时，先查看远程分支确认项目的分支结构。

---

## 📋 分支管理最佳实践

### 提交规范

**Commit Message 格式：**
```
类型: 简短描述

详细说明（可选）

关联需求/Bug（可选）
```

**常用类型：**
- `feat:` 新功能
- `fix:` Bug 修复
- `docs:` 文档更新
- `style:` 代码格式（不影响功能）
- `refactor:` 重构
- `test:` 测试相关
- `chore:` 构建/工具链相关

**示例：**
```bash
git commit -m "feat: 添加用户登录功能"
git commit -m "fix: 修复支付金额计算错误"
git commit -m "docs: 更新 API 文档"
```

---

### 合并策略

**推荐使用 `--no-ff`（保留分支历史）：**
```bash
git merge --no-ff zs/user-login
```

**避免使用 `rebase`：**
- 团队协作时不要使用 `git rebase`
- 容易造成历史混乱
- 推荐使用 `merge`

---

### 分支清理

**定期清理已合并的分支：**
```bash
# 查看已合并的分支
git branch --merged

# 删除本地分支
git branch -d zs/user-login

# 删除远程分支
git push origin --delete zs/user-login

# 清理远程已删除的分支引用
git fetch -p
```

---

## 🚨 注意事项

### 禁止操作

1. **❌ 不要直接在主分支上开发**
   ```bash
   # 错误示例
   git checkout dev
   # 直接修改代码并提交
   ```

2. **❌ 不要从 dev 或 uat 创建功能分支**
   ```bash
   # 错误示例
   git checkout dev
   git checkout -b zs/new-feature  # ❌ 不要这样做
   ```

3. **❌ 不要强制推送主分支**
   ```bash
   # 错误示例
   git push -f origin prod_release  # ❌ 禁止
   ```

4. **❌ 不要删除主分支**
   ```bash
   # 错误示例
   git branch -D prod_release  # ❌ 禁止
   ```

---

### 必做操作

1. **✅ 合并前先拉取最新代码**
   ```bash
   git checkout dev
   git pull origin dev
   git merge zs/user-login
   ```

2. **✅ 推送前先提交所有更改**
   ```bash
   git status  # 检查状态
   git add .
   git commit -m "feat: xxx"
   git push
   ```

3. **✅ 遇到冲突及时解决**
   ```bash
   # 出现冲突时
   git status              # 查看冲突文件
   # 手动解决冲突
   git add .
   git commit -m "merge: 解决冲突"
   ```

---

## 🔗 相关文档

- [[06-运维文档/Jenkins部署规则\|Jenkins部署规则]] - Jenkins 部署规则
- [[06-运维文档/SF直播App发布流程\|SF直播App发布流程]] - 移动端发布流程
- [[07-指南文档/优化工作流程指南\|优化工作流程指南]] - 日常工作流程
- [[问题记录\|问题记录]] - 问题记录

---

## 🔖 标签

#Git #分支管理 #开发规范 #版本控制

---

**记录时间：** 2026-06-16  
**记录人：** dompling
