
# Git 操作流程（带中文注释）

## 1. 初始化 Git 仓库
在当前目录下初始化一个新的 Git 仓库。此操作会在当前目录下创建 `.git` 文件夹，用于存储 Git 版本控制信息。

```bash
git init
````

> **说明**：这个命令只会初始化本地仓库，不会与任何远程仓库关联。

## 2. 将文件添加到暂存区

将你想要提交的文件（例如 `README.md`）添加到 Git 的暂存区。这样文件就准备好被提交到本地仓库。

```bash
git add README.md
```

> **说明**：`git add .` 可以添加所有修改过的文件，`README.md` 只会添加 `README.md` 文件。

## 3. 提交文件到本地仓库

提交暂存区的文件到本地 Git 仓库，并附带提交信息。

```bash
git commit -m "Initial commit: add README.md"
```

> **说明**：`-m` 后面跟的是提交信息，描述本次提交的内容。比如这里说明是第一次提交，添加了 `README.md` 文件。

## 4. 关联远程仓库

将本地仓库与远程 GitHub 仓库关联。这里假设你的远程仓库 URL 是 `https://github.com/Yuwang923/NC.git`。

```bash
git remote add origin https://github.com/Yuwang923/NC.git
```

> **说明**：`origin` 是远程仓库的默认名字，可以将其看作远程仓库的别名。`https://github.com/Yuwang923/NC.git` 是 GitHub 上的仓库地址。

## 5. 修改默认分支为 `main`

GitHub 默认将主分支命名为 `main`，而旧的默认分支是 `master`。你可以使用下面的命令将本地仓库的默认分支改为 `main`，以匹配 GitHub 的默认设置。

```bash
git branch -M main
```

> **说明**：此命令将当前分支的名称改为 `main`。

## 6. 推送代码到远程仓库

将本地 `main` 分支推送到远程仓库 `origin`，并且将远程仓库的 `main` 分支设置为上游分支，后续可以直接使用 `git push` 推送更改。

```bash
git push -u origin main
```

> **说明**：`-u` 参数会将本地分支与远程分支关联，以后推送时可以简化为 `git push`。

## 7. 查看仓库状态

使用 `git status` 查看本地仓库的状态，包括哪些文件被修改、哪些文件已添加到暂存区、是否有待提交的更改等。

```bash
git status
```

> **说明**：`git status` 会显示文件的状态，如修改、未追踪、暂存区等。

## 8. 删除文件并提交更改

如果你想从 Git 仓库中删除某个文件（例如 `filename`），并且将此更改提交到本地仓库，可以使用 `git rm` 命令。

```bash
git rm filename
```

> **说明**：`git rm` 会删除文件，并将此删除操作添加到暂存区。删除文件后，需要提交更改。

## 9. 推送删除操作到远程仓库

将删除文件后的更改推送到远程仓库，确保远程仓库和本地仓库一致。

```bash
git push origin main
```

> **说明**：此命令将删除的文件以及其它更改推送到远程仓库的 `main` 分支。

---

## 完整操作流程总结

```bash
# 1. 初始化 Git 仓库
git init

# 2. 将文件添加到暂存区
git add README.md

# 3. 提交文件到本地仓库
git commit -m "Initial commit: add README.md"

# 4. 关联远程仓库
git remote add origin https://github.com/Yuwang923/NC.git

# 5. 修改默认分支为 `main`
git branch -M main

# 6. 推送代码到远程仓库
git push -u origin main

# 当修改了本地文件后，执行以下步骤：
# 7. 查看文件修改
git status

# 8. 添加修改的文件到暂存区
git add filename  # 或 git add .

# 9. 提交更改
git commit -m "Update README.md with new information"

# 10. 推送更新到远程仓库
git push origin main

# 删除文件并提交更改
git rm filename
git commit -m "Deleted filename"

# 推送删除操作到远程仓库
git push origin main
```

---

## 其他常见操作

* **查看历史提交记录**：

  ```bash
  git log
  ```
* **查看当前分支**：

  ```bash
  git branch
  ```
* **拉取远程仓库更新**：

  ```bash
  git pull origin main
  ```
