**参考来源**：[菜鸟教程：Git工作流程](https://www.runoob.com/git/git-workflow.html)
![](https://www.runoob.com/wp-content/uploads/2015/02/git-process.png)
### 1、克隆仓库

如果你要参与一个已有的项目，首先需要将远程仓库克隆到本地：
```Shell
git clone https://github.com/username/repo.git
cd repo
```
- **默认行为**：会在当前文件夹下创建一个与仓库同名的新文件夹（`repo/`）

### 2、创建新分支

- **main/master是生产环境的镜像**：这个分支应该始终代表可部署、可用的稳定版本，因此需要避免直接在 main 或 master 分支上进行开发，通常会创建一个新的分支：
```Shell
git checkout -b new-feature
```

### 3、工作目录

在工作目录中进行代码编辑、添加新文件或删除不需要的文件。

### 4、暂存文件

将修改过的文件添加到暂存区，以便进行下一步的提交操作：
```Shell
git add filename
# 或者添加所有修改的文件
git add .
```
### 5、提交更改

将暂存区的更改提交到本地仓库，并添加提交信息：
```Shell
git commit -m ‘Add new feature‘
```
>**注：** 在 Linux 系统中，commit 信息使用单引号 '，Windows 系统，commit 信息使用双引号 "。

>所以在 git bash 中 git commit -m '提交说明' 这样是可以的，在 Windows 命令行中就要使用双引号 git commit -m "提交说明"。
### 6、拉取最新更改

在推送本地更改之前，最好从远程仓库拉取最新的更改，以避免冲突：
```Shell
git pull origin main
# 或者如果在新的分支上工作
git pull origin new-feature
```
### 7、推送更改

将本地的提交推送到远程仓库：
```Shell
git push origin new-feature
```
推送（push）相关操作报错详见：[[Git相关问题/推送错误]]
### 8、创建 Pull Request（PR）

在 GitHub 或其他托管平台上创建 Pull Request，邀请团队成员进行代码审查。PR 合并后，你的更改就会合并到主分支。

### 9、合并更改

在 PR 审核通过并合并后，可以将远程仓库的主分支合并到本地分支：

```Shell
git checkout main
git pull origin main
git merge new-feature
```
### 10、删除分支

如果不再需要新功能分支，可以将其删除：
```Shell
git branch -d new-feature
```

或者从远程仓库删除分支：
```Shell
git push origin --delete new-feature
```
