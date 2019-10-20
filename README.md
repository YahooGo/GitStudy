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
master只允许marge dev分支

> dev分支 开发版本

开发版本进行大量分支操作，稳定后merge到开发版

