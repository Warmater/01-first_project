# Git 常用指令速查

这份笔记用于记录日常最常用的 Git / GitHub 指令，方便以后快速查看。

---

## 1. 初始化 Git 仓库

在当前项目文件夹中执行：

```bash
git init
```

作用：

> 把当前文件夹初始化成一个 Git 仓库。

初始化后，当前文件夹中会出现一个隐藏的 `.git` 文件夹。

---

## 2. 设置 Git 用户信息

第一次使用 Git 时需要设置：

```bash
git config --global user.name "你的名字"
git config --global user.email "你的邮箱"
```

例如：

```bash
git config --global user.name "Warmater"
git config --global user.email "example@qq.com"
```

查看当前配置：

```bash
git config --global user.name
git config --global user.email
```

---

## 3. 查看当前项目状态

```bash
git status
```

作用：

> 查看哪些文件被修改了、哪些文件还没有提交。

这是非常常用的命令。

---

## 4. 添加修改到待提交区域

添加当前项目中的所有修改：

```bash
git add .
```

其中：

```text
.
```

代表当前目录下的所有文件。

也可以只添加某一个文件：

```bash
git add README.md
```

---

## 5. 提交一个版本

```bash
git commit -m "提交说明"
```

例如：

```bash
git commit -m "first commit"
```

或者：

```bash
git commit -m "添加README"
```

`-m` 中的内容只是这次提交的说明，不是固定写法。

例如以后可以写：

```bash
git commit -m "add login page"
git commit -m "fix data loading bug"
git commit -m "update model"
```

可以把 `commit` 理解成：

> 给当前项目保存一个版本快照。

---

# 6. 连接 GitHub 仓库

假设 GitHub 仓库地址是：

```text
https://github.com/Warmater/01-first_project.git
```

执行：

```bash
git remote add origin https://github.com/Warmater/01-first_project.git
```

其中：

```text
origin
```

只是远程仓库的一个别名。

通常大家都使用 `origin`。

查看当前连接的远程仓库：

```bash
git remote -v
```

---

## 7. 设置主分支为 main

```bash
git branch -M main
```

其中：

```text
main
```

是主分支名称。

现在大多数 GitHub 项目的默认主分支都叫：

```text
main
```

以前也经常叫：

```text
master
```

---

## 8. 第一次上传到 GitHub

```bash
git push -u origin main
```

可以拆成：

```text
git push
```

上传代码。

```text
origin
```

上传到哪个远程仓库。

```text
main
```

上传哪个分支。

```text
-u
```

记住本地 `main` 和远程 `origin/main` 的对应关系。

第一次设置完成以后，之后通常直接：

```bash
git push
```

即可。

---

# 9. 日常更新项目

以后每次修改完项目，最常用的流程就是：

```bash
git add .
git commit -m "这次修改了什么"
git push
```

可以简单记成：

```text
add
↓
commit
↓
push
```

也就是：

```text
把修改加入待提交区
↓
保存一个版本
↓
上传到 GitHub
```

---

# 10. 从 GitHub 获取最新代码

```bash
git pull
```

作用：

> 把 GitHub 远程仓库上的最新修改下载到本地，并更新当前项目。

多人协作时会经常使用。

---

# 11. 下载一个 GitHub 项目

第一次把某个 GitHub 项目完整下载到电脑：

```bash
git clone 仓库地址
```

例如：

```bash
git clone https://github.com/xxx/project.git
```

执行后，Git 会自动创建项目文件夹并下载整个仓库。

---

# 12. 查看历史提交

```bash
git log
```

可以查看：

- 提交记录
- commit 编号
- 提交者
- 提交时间
- 提交说明

例如：

```text
first commit
add README
update model
fix bug
```

---

# 13. 查看具体修改内容

```bash
git diff
```

作用：

> 查看当前文件和上一次版本相比具体修改了哪些内容。

---

# 14. GitHub 中几个重要概念

## Repository

简称：

```text
repo
```

意思是：

> 仓库，也就是一个项目。

例如：

```text
01-first_project
```

就是一个仓库。

---

## Commit

一次版本存档。

例如：

```bash
git commit -m "add README"
```

可以理解成：

> 保存当前项目状态，并写一句备注。

---

## Push

```bash
git push
```

意思：

> 把本地已经提交的版本上传到 GitHub。

---

## Pull

```bash
git pull
```

意思：

> 把 GitHub 上最新的修改拉到本地。

---

## Clone

```bash
git clone
```

意思：

> 第一次完整下载一个 GitHub 项目。

---

## Branch

分支。

同一个仓库中可以存在多个开发路线，例如：

```text
01-first_project
│
├── main
├── dev
└── test
```

其中：

```text
main
```

通常作为正式、稳定的主分支。

例如：

```text
main
A ---- B ---- C
             \
dev           D ---- E
```

可以在 `dev` 分支尝试新功能，不影响 `main`。

---

# 15. 第一次创建项目并上传 GitHub

完整流程：

```bash
git init

git add .

git commit -m "first commit"

git remote add origin https://github.com/用户名/仓库名.git

git branch -M main

git push -u origin main
```

注意：

第一次提交之前需要至少有一个文件。

Git 不会单独记录一个完全空的文件夹。

---

# 16. 以后更新项目

最常用的三个命令：

```bash
git add .
git commit -m "修改说明"
git push
```

---

# 17. 常用命令速查表

| 命令 | 作用 |
|---|---|
| `git init` | 初始化 Git 仓库 |
| `git status` | 查看当前修改状态 |
| `git add .` | 添加所有修改 |
| `git add 文件名` | 添加指定文件 |
| `git commit -m "说明"` | 保存一个版本 |
| `git remote add origin 地址` | 连接远程仓库 |
| `git remote -v` | 查看远程仓库 |
| `git branch -M main` | 设置主分支名称 |
| `git push -u origin main` | 第一次上传并建立对应关系 |
| `git push` | 上传最新提交 |
| `git pull` | 获取远程最新代码 |
| `git clone 地址` | 下载整个仓库 |
| `git log` | 查看历史提交 |
| `git diff` | 查看修改内容 |

---

# 最需要记住的内容

日常使用基本就是：

```bash
git status

git add .

git commit -m "修改说明"

git push
```

核心流程：

```text
修改代码
↓
git status
↓
git add .
↓
git commit
↓
git push
↓
GitHub
```