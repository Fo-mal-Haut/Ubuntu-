
**参考来源**：[Git操作私人仓库方法](https://www.cnblogs.com/DumpInfou/p/18201753 "发布于 2024-05-20 13:52")

> 整合ChatGPT回答内容

## 一、克隆

### 1. 使用 HTTPS 克隆私人仓库

1. **获取仓库的 HTTPS 链接**：

   * 打开 GitHub 仓库页面。
   * 点击绿色的 `Code` 按钮。
   * 选择 `HTTPS` 并复制链接。

2. **在终端中使用 Git 克隆仓库**：

   ```sh
   git clone https://github.com/username/repository.git
   ```

   系统会提示你输入 GitHub 的用户名和密码。

### 2. 使用 SSH 克隆私人仓库

1. **生成 SSH 密钥**（如果还没有的话）：

   ```sh
   ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
   ```

   按照提示完成生成过程，默认情况下，密钥会保存在 `~/.ssh/id_rsa` 和 `~/.ssh/id_rsa.pub`。

2. **将 SSH 公钥添加到 GitHub**：

   * 复制公钥内容：

     ```sh
     cat ~/.ssh/id_rsa.pub
     ```

   * 打开 GitHub，进入 `Settings` > `SSH and GPG keys` > `New SSH key`。

   * 将公钥粘贴进去并保存。

3. **测试 SSH 连接**：

   ```sh
   ssh -T git@github.com
   ```

   你应该看到一条欢迎消息，表明连接成功。

4. **使用 SSH 链接克隆仓库**：

   * 获取仓库的 SSH 链接：

     * 打开 GitHub 仓库页面。
     * 点击绿色的 `Code` 按钮。
     * 选择 `SSH` 并复制链接。

   * 在终端中执行克隆命令：

     ```sh
     git clone git@github.com:username/repository.git
     ```

### 3. 使用个人访问令牌 (Personal Access Token)

如果你不想使用密码进行身份验证，可以创建一个个人访问令牌：

1. **生成个人访问令牌**：

   * 打开 GitHub，进入 `Settings` > `Developer settings` > `Personal access tokens` > `Generate new token`。
   * 选择需要的权限（例如 `repo` 用于访问私人仓库）。
   * 生成令牌并复制。

2. **使用令牌克隆仓库**：

   ```sh
   git clone https://<token>@github.com/username/repository.git
   ```

   将 `<token>` 替换为你生成的个人访问令牌。

### 注意事项

* **安全性**：确保你的 SSH 密钥和访问令牌的安全，不要在公共场合泄露。
* **密钥管理**：定期更新和管理你的密钥和访问令牌，以保持账户的安全。

## 二、推送

### 1. 确认身份验证方式

在克隆私人仓库时，你可能已经设置了身份验证方式。推送时会使用相同的身份验证方式。常用的有 HTTPS 和 SSH。

### 2. 配置全局用户名和邮箱

确保你的 Git 配置了正确的用户名和邮箱：

```sh
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"
```

### 3. 提交本地更改

1. 检查文件状态

   ```sh
   git status
   ```

2. 添加更改到暂存区

   ```sh
   git add .
   ```

   或者添加具体的文件：

   ```sh
   git add <file1> <file2>
   ```

3. 提交更改

   ```sh
   git commit -m "描述你的更改"
   ```

### 4. 推送更改到远程仓库

1. 推送到远程仓库

   ```sh
   git push origin <branch-name>
   ```

   将

   ```sh
   <branch-name>
   ```

   替换为你要推送的分支名称（通常是

   ```sh
   main
   ```

   或

   ```sh
   master
   ```

   ，但也可能是其他分支）。

### 5. 使用个人访问令牌 (如果使用 HTTPS)

如果使用 HTTPS 克隆并且需要个人访问令牌进行身份验证，推送时会提示输入用户名和访问令牌。

```sh
git push origin <branch-name>
```

系统会提示你输入用户名和密码，此时：

* 用户名输入你的 GitHub 用户名。
* 密码输入你的个人访问令牌。

### 6. 使用 SSH

如果使用 SSH 进行身份验证，推送命令与上述相同，但不需要额外的密码输入。

```sh
git push origin <branch-name>
```

### 例子操作

假设你已经克隆了仓库并在 `main` 分支上进行了一些更改：

```sh
# 查看文件状态
git status

# 添加所有更改到暂存区
git add .

# 提交更改
git commit -m "Add new feature"

# 推送到远程的 main 分支
git push origin main
```

### 常见问题解决

* **权限问题**：确保你对仓库有写权限。如果没有，需要仓库管理员授予你权限。

* 远程分支不存在

  ：如果远程仓库中没有对应的分支，可以使用以下命令创建并推送：

  ```sh
  git push -u origin <branch-name>
  ```

  这会创建远程分支并将本地分支与之关联。

通过以上步骤，你应该能够成功将本地更改推送到私人远程仓库。

## 三、踩坑日记

### 1、Git 尝试使用 HTTPS 而不是 SSH 来推送更改

```sh
❯ git push origin main
Username for 'https://github.com': username
Password for 'https://username@github.com':
remote: Support for password authentication was removed on August 13, 2021.
remote: Please see https://docs.github.com/get-started/getting-started-with-git/about-remote-repositories#cloning-with-https-urls for information on currently recommended modes of authentication.
fatal: Authentication failed for 'https://github.com/username/xxxx.git/'
```

### 步骤：

1. **查看当前远程仓库 URL**：

   ```sh
   git remote -v
   ```

2. **更改远程仓库 URL**： 你需要将 HTTPS URL 更改为 SSH URL。首先，复制当前远程仓库名称（通常是 `origin`）。

   ```sh
   git remote set-url origin git@github.com:username/xxxx.git
   ```

3. **验证更改**： 再次查看远程仓库 URL，确认已更改为 SSH。

   ```sh
   git remote -v
   ```

   你应该看到类似以下的输出：

   ```sh
   origin  git@github.com:username/xxxx.git (fetch)
   origin  git@github.com:username/xxxx.git (push)
   ```

4. **推送更改**： 使用 SSH URL 推送你的更改。

   ```sh
   git push origin main
   ```

### 完整示例

1. **查看当前远程仓库 URL**：

   ```sh
   git remote -v
   ```

   输出可能是：

   ```sh
   origin  https://github.com/username/xxxx.git (fetch)
   origin  https://github.com/username/xxxx.git (push)
   ```

2. **更改远程仓库 URL**：

   ```sh
   git remote set-url origin git@github.com:username/xxxx.git
   ```

3. **验证更改**：

   ```sh
   git remote -v
   ```

   输出应为：

   ```sh
   origin  git@github.com:username/xxxx.git (fetch)
   origin  git@github.com:username/xxxx.git (push)
   ```

4. **推送更改**：

   ```sh
   git push origin main
   ```

通过上述步骤，你应该能够成功推送到使用 SSH 的远程仓库。如果仍有问题，请确保你的 SSH 密钥配置正确，且在 `~/.ssh/config` 中设置的路径正确无误。