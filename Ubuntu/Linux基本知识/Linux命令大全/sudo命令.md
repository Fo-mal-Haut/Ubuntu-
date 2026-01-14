**参考文档**：[Linux sudo命令](https://www.runoob.com/linux/linux-comm-sudo.html)

sudo 全称为 Super User DO，允许授权用户以其他用户（通常是 root 用户）的身份执行命令，也就是说，经由 sudo 所执行的指令就好像是 root 亲自执行。

使用权限：在 `/etc/sudoers` 中有出现的使用者。

### 语法
```Shell
sudo [选项] 命令
```
**例如：**
```Shell
sudo apt update          # 以 root 权限更新软件包列表
sudo vim /etc/hosts     # 编辑需要 root 权限的文件
```
