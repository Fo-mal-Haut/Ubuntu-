**参考来源**：
[Linux Snap 安装与使用指南：高效管理应用的神器](https://juejin.cn/post/7534552786936217654)
[菜鸟教程 snap命令](https://www.runoob.com/linux/linux-comm-snap.html)
[Snapcraft官方文档](https://snapcraft.io/docs)。
# snap 命令基础语法

snap 命令的基本语法结构如下：
```text
snap [命令] [选项] [包名]
```
### 常用命令概览

- `install` - 安装 snap 包
- `remove` - 移除 snap 包
- `refresh` - 更新 snap 包
- `list` - 列出已安装的 snap 包
- `find` - 搜索可用的 snap 包
- `info` - 显示 snap 包信息
- `revert` - 回滚到之前版本
- `disable/enable` - 禁用/启用 snap 包
- `services` - 管理 snap 服务

```shell
# 列出已安装应用
snap list

# 更新所有应用
sudo snap refresh

# 更新特定应用
sudo snap refresh <软件名>

# 卸载应用
sudo snap remove <软件名>

# 查看应用信息
snap info <软件名>

```
## 安装 snap 包
```shell
sudo snap install <package-name>
```
常用选项：

- `--channel`：指定安装渠道(如 stable, candidate, beta, edge)
- `--devmode`：以开发者模式安装(降低安全性限制)
- `--classic`：以经典模式安装(放宽限制)

示例：
```shell
sudo snap install code --classic  # 安装 VS Code
```

# 安装路径

snap将将软件及其依赖封装在**独立的沙盒**中，软件安装到统一的路径下`/snap`

# snap设计特点

1. **原子更新**：要么全部成功，要么全部回滚
2. **运行时隔离**：更新时需要确保应用不在运行
3. **版本共存**：新旧版本短暂同时存在直到切换完成
4. **自动回滚**：如果更新失败会自动恢复旧版
5. **自带依赖**：应用自带所有依赖，避免版本冲突
6. **安全隔离**：应用在沙盒中运行，保护系统安全