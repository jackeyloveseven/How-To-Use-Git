# How-To-Use-Git  
## How To Use Git As a DUTer  

### 目录  
- [Git 简介](#git-简介)  
- [安装指南](#安装指南)  
- [基础操作](#基础操作)  
  - [初始化仓库](#初始化仓库)  
  - [文件操作](#文件操作)  
  - [提交历史查看](#提交历史查看)  
- [远程仓库管理](#远程仓库管理)  
  - [连接 GitHub/GitLab](#连接-githubgitlab)  
  - [代码推送与拉取](#代码推送与拉取)  
- [分支管理](#分支管理)  
  - [创建与切换分支](#创建与切换分支)  
  - [合并分支](#合并分支)  
- [高级技巧](#高级技巧)  
  - [版本回退](#版本回退)  
  - [暂存修改](#暂存修改)  
- [常见问题](#常见问题)  
- [贡献指南](#贡献指南)  


### Git 简介  
Git 是一个分布式版本控制系统，用于跟踪文件变化，支持多人协作开发。作为 DUTer，你可以用它管理课程作业、团队项目或科研代码，避免文件丢失，追溯修改历史，轻松实现团队协作。  


### 安装指南  
#### Windows  
1. 下载 [Git for Windows](https://gitforwindows.org/) 并安装  
2. 安装完成后，打开 `Git Bash` 或 `Git CMD`  

#### Mac  
1. 通过 Homebrew 安装：`brew install git`  
2. 或从 [官网](https://git-scm.com/download/mac) 下载安装包  

#### Linux  
1. Debian/Ubuntu：`sudo apt-get install git`  
2. CentOS/Fedora：`sudo dnf install git`  


### 基础操作  
#### 初始化仓库  
```bash
# 在项目目录中初始化Git仓库
git init
```
⚠️ **注意**：.git 文件夹是 Git 的核心，**不要手动修改或删除**！

**示例**：在课程作业文件夹中执行 `git init`，生成 `.git` 隐藏目录（存储版本数据）。  


#### 文件操作  
```bash
# 查看文件状态（新增/修改/未追踪）
git status

# 添加单个文件到暂存区
git add filename.txt

# 添加所有文件到暂存区
git add .

# 提交暂存区文件，-m 后接提交说明
git commit -m "添加作业README"
```  


#### 提交历史查看  
```bash
# 查看简洁提交日志
git log --oneline

# 查看详细提交信息（含作者、时间）
git log

# 查看图形化分支历史
git log --graph --all --decorate
```  


### 远程仓库管理  
#### 连接 GitHub/GitLab  
```bash
# 创建远程仓库（以GitHub为例）
# 1. 在GitHub新建仓库，复制HTTPS地址
git remote add origin https://github.com/your-username/your-repo.git

# 2. 首次推送需指定分支
git push -u origin main  # main为默认分支名，旧版本可能为master
```  


#### 代码推送与拉取  
```bash
# 推送本地分支到远程仓库
git push origin main

# 拉取远程仓库更新
git pull origin main

# 克隆远程仓库到本地
git clone https://github.com/your-username/your-repo.git
```  


### 分支管理  
#### 创建与切换分支  
```bash
# 创建新分支并切换（推荐用于功能开发）
git checkout -b feature/homework

# 仅创建分支（不切换）
git branch feature/homework

# 切换已有分支
git checkout main
```  


#### 合并分支  
```bash
# 切换到目标分支（如main）
git checkout main

# 合并feature/homework分支到main
git merge feature/homework

# 解决冲突后重新提交
# （冲突文件会标记<<<<<<<，手动修改后git add/commit）
```  


### 高级技巧  
#### 版本回退  
```bash
# 查看历史提交ID
git log --oneline

# 回退到指定版本（保留本地修改）
git reset --soft commit-id

# 回退到指定版本（删除后续修改）
git reset --hard commit-id
```  


#### 暂存修改  
```bash
# 暂存当前未提交的修改
git stash

# 恢复暂存的修改
git stash pop

# 查看暂存列表
git stash list
```  


### 常见问题  
1. **冲突解决**  
   - 当多人修改同一文件时，拉取代码会提示冲突，需手动修改冲突标记后提交。  

2. **忘记添加文件**  
   - `git commit` 后发现漏加文件：`git add missed-file && git commit --amend`  

3. **远程仓库权限问题**  
   - HTTPS方式需输入账号密码，推荐配置SSH密钥：`ssh-keygen -t rsa -b 4096 -C "your@email.com"`  


### 贡献指南  
1.  Fork 本仓库到个人账号  
2.  创建功能分支：`git checkout -b feature/your-feature`  
3.  提交修改并推送：`git push origin feature/your-feature`  
4.  在原仓库创建 Pull Request  


### 更多资源  
- [Git 官方文档](https://git-scm.com/docs)  
- [廖雪峰 Git 教程](https://www.liaoxuefeng.com/wiki/896043488029600)    

**Tips**：多使用 `git status` 查看状态，避免操作失误！ 🚀
