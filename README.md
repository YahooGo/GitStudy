# GitStudy
学习 Git 操作

## 版本控制
- 进入要管理的文件夹
- 初始化 (提名----获取所有需要管理的文件)
- 管理 
- 生成版本


## Git 简单使用
1. `git init` 初始化，让git接管当前文件夹
2. `git status` 检测当前目录下文件夹的状态
3. 三种状态
```
 - 红色： 修改过或新增文件 ---》`git add`+ `文件名`或`.` 让文件被管理
 - 绿色： Git接管起来 ---》`git commit -m` + `描述信息`
 - 生成版本： 
```
4. 个人信息配置 用户名，邮箱

## Git 使用三大区域
> 工作区
>> 已管文件 + 修改文件或新文件

>> `git add` 提交暂存区 

> 暂存区域

>> `git commit` 提交版本库  


> 版本区域


## 回滚功能

`git reset` + `--head` + `版本号`

`git log` 查看版本

`git reflog` 查看所有版本功能


## 分支
`git branch` ==》 master 主分支

`git branch dev` ==》 创建dev分支

`git checkout dev` ==》 切换dev分支

`git merge bug` ==》 合并bug分支 --- merge 后+ 需要需要被合并的分支， 将bug分支合并到当前分支

`git branch -d bug` ==》 删除bug分支


## 新建项目 工作流

> master分支 正式版本

正式版只保留稳定版本
线上master只允许marge 线上dev分支 且master不允许手动修改代码不允许直接提交代码

> dev分支 开发版本

开发版本进行大量分支操作，稳定后merge到开发版

## 远程仓库操作

> 为远程仓库起别名

`git remote add origin 远程仓库地址`

> 向远程仓库推送

`git push -u origin 分支名称`

> 拉取代码 克隆

`git clone 远程仓库地址` ===> 内部已实现`git remote add origin 远程仓库`

> 分支切换

`git checkout 分支`

## 开发流程
> master 绝对不能随意修改

> dev开发环境 
- 使用dev环境merge master分支 `git merge master` 
- 此时dev分支为最新分支
- 此时开发dev环境， 通过`git commit -m 信息`提交到本地dev环境
- 将本地dev环境推送到向上dev环境
- 将本地代码更新 `git pull origin dev`

## 开发完毕上线
- `git checkout master` 切换为master分支
- `git merge dev` 合并dev分支
- `git push origin master` 推送代码

## 推送dev环境
- `git checkout dev` 切换dev分支
- `git merge master` 合并master分支
- `git push origin dev` 推送开发环境

## 补充命令
`git pull origin dev` 从线上dev环境拉取代码 = `git fetch origin dev` + `git merge origin/dev`

## rebease 変基

> 查看分支 `git log --graph --pretty=format:"%h %s"`

> 情景1：本地分支 多次commit 合并为一次 `git rebase -i HEAD~3` ~3为最近3次

> 情景2： dev分支开发后，master分支被合并过.
1. 此时切换master分支 `git merge dev`

2. 先切回dev分支 `git rebase master` 将dev分支変基 为一条主线分支
 
> 情景3： 
