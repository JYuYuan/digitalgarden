---
{"dg-publish":true,"permalink":"/06/jenkins/","dg-note-properties":{}}
---

# Jenkins 部署规则

> Jenkins 部署规则说明（基于 shared-pipeline-library）

---

## 📋 Jenkinsfile 配置说明

### 示例配置

**基础配置：**
```groovy
@Library('shared-pipeline-library') _
ReactCI {
  jenkins_node = 'k8s-agent-react'
  k8s_namespace = 'sac-dev'
  k8s_application_name = 'jnc-security-sac-frontend'
  replicas = '1'
  feature_branch_name = 'dev'
}
```

**完整配置（包含可选参数）：**
```groovy
@Library('shared-pipeline-library') _
ReactCI {
  jenkins_node = 'k8s-agent-react'
  k8s_namespace = 'bss-dev'
  k8s_application_name = 'tpm-fee-web'
  replicas = '1'
  feature_branch_name = 'dev'
  build_script = 'build:dev'     // 指定构建命令
  node_version = '16.14.2'       // 指定 Node 版本
}
```

---

## 🔑 核心参数说明

### 基础配置

| 参数 | 说明 | 示例 | 必填 |
|------|------|------|------|
| `jenkins_node` | Jenkins 构建节点 | `'k8s-agent-react'` | ✅ |
| `k8s_namespace` | K8s 命名空间 | `'sac-dev'` | ✅ |
| `k8s_application_name` | K8s 应用名称 | `'jnc-security-sac-frontend'` | ✅ |
| `replicas` | Pod 副本数 | `'1'` | ✅ |
| `feature_branch_name` | **允许强制发版的分支** | `'dev'` | ✅ |
| `build_script` | Node 构建命令 | `'build'` 或 `'build:dev'` | ❌ |
| `node_version` | Node 版本 | `'16.14.2'` | ❌ |

**说明：**
- ✅ 必填参数
- ❌ 可选参数（有默认值）

### 参数详细说明

**`build_script`（可选）**
- 指定 npm 构建命令
- 默认值：`'build'`（执行 `npm run build`）
- 示例：
  - `build_script = 'build'` → 执行 `npm run build`
  - `build_script = 'build:dev'` → 执行 `npm run build:dev`
  - `build_script = 'build:prod'` → 执行 `npm run build:prod`

**`node_version`（可选）**
- 指定 Node.js 版本
- 默认值：由 Jenkins 节点决定
- 示例：
  - `node_version = '16.14.2'`
  - `node_version = '18.16.0'`
- 用途：不同环境或项目可能需要特定的 Node 版本

---

## 🔑 部署规则

### 规则 1：feature_branch_name 强制发版

**规则：** 当 `feature_branch_name` 与当前分支名相同时，允许强制发版。

**配置：**
```groovy
feature_branch_name = 'dev'
```

**行为：**
- 当前分支是 `dev` → ✅ 允许部署到 `sac-dev` 命名空间
- 当前分支是 `master` / `main` → ✅ 允许部署（标准分支）
- 当前分支是 `feature/xxx` → ❌ 不允许部署（除非配置为 feature_branch_name）

**使用场景：**
```groovy
// 场景 1：开发环境部署
feature_branch_name = 'dev'
// dev 分支可以部署到开发环境

// 场景 2：紧急热修复
feature_branch_name = 'hotfix/urgent-fix'
// hotfix/urgent-fix 分支可以立即部署
```

---

### 规则 2：release 和 uat 分支只构建不推送

**规则：** 分支名包含 `release` 或 `uat` 关键字时，只构建，不推送到 K8s。

**匹配的分支名：**
```
prod_release
uat_release
release/v1.0.0
uat
uat/feature
任何包含 "release" 或 "uat" 的分支
```

**行为：**
- ✅ 执行构建（npm run build）
- ❌ 不推送镜像（docker push）
- ❌ 不部署到 K8s（kubectl apply）

---

## 🎯 常见配置示例

### 开发环境

```groovy
@Library('shared-pipeline-library') _
ReactCI {
  jenkins_node = 'k8s-agent-react'
  k8s_namespace = 'app-dev'                # 开发命名空间
  k8s_application_name = 'my-app'
  replicas = '1'
  feature_branch_name = 'dev'              # dev 分支可部署
}
```

---

### 开发环境（指定 Node 版本和构建命令）

```groovy
@Library('shared-pipeline-library') _
ReactCI {
  jenkins_node = 'k8s-agent-react'
  k8s_namespace = 'app-dev'
  k8s_application_name = 'my-app'
  replicas = '1'
  feature_branch_name = 'dev'
  build_script = 'build:dev'               # 执行 npm run build:dev
  node_version = '16.14.2'                 # 使用 Node 16.14.2
}
```

---

### 测试环境

```groovy
@Library('shared-pipeline-library') _
ReactCI {
  jenkins_node = 'k8s-agent-react'
  k8s_namespace = 'app-test'               # 测试命名空间
  k8s_application_name = 'my-app'
  replicas = '2'
  feature_branch_name = 'test'             # test 分支可部署（不要用 uat）
  build_script = 'build:test'              # 执行 npm run build:test
}
```

**注意：** 不要使用 `uat` 作为分支名或 `feature_branch_name`，因为包含 `uat` 的分支不会部署。

---

### 生产环境

```groovy
@Library('shared-pipeline-library') _
ReactCI {
  jenkins_node = 'k8s-agent-react'
  k8s_namespace = 'app-prod'               # 生产命名空间
  k8s_application_name = 'my-app'
  replicas = '3'
  feature_branch_name = 'master'           # master 分支可部署
  build_script = 'build:prod'              # 执行 npm run build:prod
  node_version = '16.14.2'                 # 生产环境固定 Node 版本
}
```

---

### 紧急热修复

```groovy
@Library('shared-pipeline-library') _
ReactCI {
  jenkins_node = 'k8s-agent-react'
  k8s_namespace = 'app-prod'
  k8s_application_name = 'my-app'
  replicas = '3'
  feature_branch_name = 'hotfix/payment-bug'  # 允许此分支直接部署
  build_script = 'build:prod'
  node_version = '16.14.2'
}
```

---

## 📊 分支部署行为

| 分支名 | feature_branch_name 配置 | 是否部署 |
|--------|-------------------------|---------|
| `dev` | `'dev'` | ✅ 部署 |
| `master` | 任意 | ✅ 部署（标准分支） |
| `feature/xxx` | `'dev'` | ❌ 不部署 |
| `feature/xxx` | `'feature/xxx'` | ✅ 部署 |
| `uat` | 任意 | ❌ 只构建不部署 |
| `uat/xxx` | 任意 | ❌ 只构建不部署 |
| `prod_release` | 任意 | ❌ 只构建不部署 |
| `uat_release` | 任意 | ❌ 只构建不部署 |

---

## 💡 实际使用流程

### 流程 1：修改部署分支

**需求：** 允许 `dev` 分支部署到开发环境

```groovy
// 1. 修改 Jenkinsfile
@Library('shared-pipeline-library') _
ReactCI {
  jenkins_node = 'k8s-agent-react'
  k8s_namespace = 'sac-dev'
  k8s_application_name = 'jnc-security-sac-frontend'
  replicas = '1'
  feature_branch_name = 'dev'  // 设置为 dev
}

// 2. 提交 Jenkinsfile
git add Jenkinsfile
git commit -m "chore: allow dev branch to deploy"
git push

// 3. 切换到 dev 分支并推送
git checkout dev
git push origin dev

// 4. Jenkins 自动部署到 sac-dev 命名空间
```

---

### 流程 2：紧急热修复部署

**需求：** 紧急修复需要立即部署到生产

```groovy
// 1. 创建 hotfix 分支
git checkout -b hotfix/fix-login

// 2. 修复代码并提交
git add .
git commit -m "fix: 修复登录问题"
git push origin hotfix/fix-login

// 3. 修改 Jenkinsfile 的 feature_branch_name
feature_branch_name = 'hotfix/fix-login'

// 4. 提交并推送
git add Jenkinsfile
git commit -m "chore: allow hotfix deployment"
git push

// 5. Jenkins 自动部署
```

---

### 流程 3：Release 分支验证

**需求：** 验证发布分支是否可以正常构建

```groovy
// 1. 创建 release 分支
git checkout -b prod_release

// 2. 推送到远程
git push origin prod_release

// 3. Jenkins 自动触发
// ✅ 执行构建
// ❌ 不部署

// 4. 验证构建产物
// 5. 确认无误后合并到 master
git checkout master
git merge prod_release
git push origin master
// master 分支会自动部署
```

---

## ⚠️ 注意事项

1. **feature_branch_name 必须精确匹配**
   - 配置：`feature_branch_name = 'dev'`
   - 分支名：`dev` ✅
   - 分支名：`develop` ❌（不匹配）

2. **修改 Jenkinsfile 需要提交到代码库**
   - 修改 `feature_branch_name` 后必须提交
   - Jenkins 读取的是代码库中的 Jenkinsfile

3. **包含 release 或 uat 的分支自动跳过部署**
   - 任何包含 `release` 或 `uat` 的分支名都只构建不部署
   - 无需额外配置
   - ⚠️ 避免使用 `uat` 作为正式分支名

4. **master/main 分支始终可部署**
   - 不受 `feature_branch_name` 限制
   - 标准生产分支

---

## 🔗 相关文档

- [[06-运维文档/SF直播App发布流程\|SF直播App发布流程]] - 移动端发布流程
- [[07-指南文档/优化工作流程指南\|优化工作流程指南]] - 日常工作流程
- [[问题记录\|问题记录]] - 问题记录

---

## 🔖 标签

#Jenkins #CI/CD #部署规则 #K8s #ReactCI #shared-pipeline-library

---

**记录时间：** 2026-06-16  
**记录人：** dompling
