# Git Developer Notes & Standards 🚀

A comprehensive reference for daily Git workflows, repository management, and commit message standards.

---

## 📚 Table of Contents

- **Git Commands Reference**
  - [1. 基础配置与初始化](#1-基础配置与初始化)
  - [2. 日常工作流 (提交与状态)](#2-日常工作流-提交与状态)
  - [3. 分支管理 (Branching)](#3-分支管理-branching)
  - [4. 远程仓库交互 (Remote & Sync)](#4-远程仓库交互-remote--sync)
  - [5. 撤销与重置 (Undo & Stash)](#5-撤销与重置-undo--stash)
- **Git Commit Message Standard**
  - [1. Commit Message Structure](#1-commit-message-structure)
  - [2. Standard Commit Types](#2-standard-commit-types)
  - [3. Best Practices & Rules](#3-best-practices--rules)
  - [4. Examples](#4-examples)

---

# Part I: Git Commands Reference

## 1. 基础配置与初始化

| 命令 | 说明 |
| :--- | :--- |
| `git config --global user.name "Your Name"` | 设置全局用户名 |
| `git config --global user.email "email@example.com"` | 设置全局邮箱 |
| `git config --list` | 查看当前全局配置 |
| `git init -b main` | 在当前目录初始化一个 Git 仓库并指定主分支为 `main` |
| `git clone <repo-url>` | 克隆远程仓库到本地 |

---

## 2. 日常工作流 (提交与状态)

| 命令 | 说明 |
| :--- | :--- |
| `git status` | 查看文件状态（工作区与暂存区变动） |
| `git add <file>` | 将指定文件添加到暂存区 |
| `git add .` | 将所有变动文件添加到暂存区 |
| `git commit -m "commit message"` | 提交暂存区变动到本地仓库 |
| `git commit -am "commit message"` | 快捷提交（跳过 `git add`，仅限已追踪的文件） |
| `git log --oneline -n 10` | 查看最近 10 条单行简洁提交历史 |
| `git diff` | 查看工作区与暂存区的详细代码差异 |

---

## 3. 分支管理 (Branching)

| 命令 | 说明 |
| :--- | :--- |
| `git branch` | 查看本地分支（`*` 代表当前所在分支） |
| `git branch -a` | 查看所有分支（包括远程分支） |
| `git checkout -b <branch-name>` | 创建并直接切换到新分支 |
| `git switch <branch-name>` | 切换到已有分支 |
| `git merge <branch-name>` | 将指定分支合并到当前分支 |
| `git branch -d <branch-name>` | 删除已被合并的本地分支 |
| `git branch -D <branch-name>` | 强制删除本地分支 |

---

## 4. 远程仓库交互 (Remote & Sync)

| 命令 | 说明 |
| :--- | :--- |
| `git remote -v` | 查看已关联的远程仓库地址 |
| `git remote add origin <repo-url>` | 关联本地仓库到远程仓库 |
| `git fetch origin` | 拉取远程仓库最新改动（不自动合并） |
| `git pull origin <branch-name>` | 拉取远程分支并自动合并到当前分支 |
| `git push -u origin <branch-name>` | 首次推送本地分支并建立远程追踪链接 |
| `git push` | 推送本地新提交到绑定的远程分支 |

---

## 5. 撤销与重置 (Undo & Stash)

| 命令 | 说明 |
| :--- | :--- |
| `git restore <file>` | 丢弃工作区的修改（未 `git add` 的变动） |
| `git restore --staged <file>` | 将文件从暂存区撤回到工作区 |
| `git commit --amend -m "new message"` | 修改上一次的 commit message（未 push 前使用） |
| `git reset --soft HEAD~1` | 撤销上一次提交，保留代码到暂存区 |
| `git reset --hard HEAD~1` | **慎用**：彻底撤销上一次提交及代码变动 |
| `git stash` | 暂存当前未提交的工作区变动 |
| `git stash pop` | 恢复最近一次暂存的变动并删除 stash 记录 |

---

# Part II: Git Commit Message Standard 📝

Standard commit message conventions based on [Conventional Commits](https://www.conventionalcommits.org/).

---

## 1. Commit Message Structure

```text
<type>(<scope>): <subject>
```

- **type** (Required): Purpose of the commit (e.g., `feat`, `fix`, `docs`).
- **scope** (Optional): Section of the codebase affected (e.g., `auth`, `parser`, `ui`).
- **subject** (Required): Short description in imperative, present tense (e.g., `add` not `added`).

---

## 2. Standard Commit Types

| Type | Description | Example |
| :--- | :--- | :--- |
| **`feat`** | A new feature | `feat(auth): add OAuth2 login support` |
| **`fix`** | A bug fix | `fix(cart): resolve double charging issue` |
| **`docs`** | Documentation changes | `docs(readme): update setup instructions` |
| **`style`** | Code style (formatting, missing semi-colons, no logic change) | `style(lint): format files with prettier` |
| **`refactor`** | Code change that neither fixes a bug nor adds a feature | `refactor(user): simplify database query` |
| **`perf`** | Performance improvement | `perf(search): optimize query indexing` |
| **`test`** | Adding or correcting tests | `test(order): add unit tests for checkout` |
| **`chore`** | Maintenance, build process, or dependency updates | `chore(deps): bump zsh-autosuggestions` |
| **`ci`** | CI/CD configuration updates | `ci(actions): update release pipeline` |

---

## 3. Best Practices & Rules

1. **Capitalization**: Use lowercase for `<type>` and `<subject>`.
2. **Imperative Mood**: Write in present tense ("add", "fix", "update", NOT "added" or "fixing").
3. **No Trailing Period**: Do not put a period `.` at the end of the subject line.
4. **Line Length**: Keep the subject line under 50 characters; body lines under 72 characters.
5. **Breaking Changes**: Mark with `!` before `:` or add `BREAKING CHANGE:` in footer.
   - Example: `feat(api)!: drop v1 endpoint support`

---

## 4. Examples

```bash
# Feature with scope
git commit -m "feat(cli): add auto-completion support"

# Quick documentation fix
git commit -m "docs: fix typo in markdown guide"

# Refactor without scope
git commit -m "refactor: simplify error handling logic"

# Maintenance task
git commit -m "chore: update gitignore for macos DS_Store"
```
