**参考来源**：[下载与安装](https://publish.obsidian.md/help-zh/%E5%BF%AB%E9%80%9F%E5%85%A5%E9%97%A8/%E4%B8%8B%E8%BD%BD%E4%B8%8E%E5%AE%89%E8%A3%85)

## 在 Linux 上安装 Obsidian

Linux 可以通过几种方式安装 Obsidian。不同系统有不同的安装方法。

### 使用 Snap 安装 Obsidian

1. 打开浏览器，访问[Obsidian 下载页面](https://obsidian.md/download)。
    
2. 在**Linux**下，点击**Snap**下载安装文件。
    
3. 打开终端，进入保存安装文件的文件夹。
    
4. 在终端中，运行以下命令安装 Snap 包：（`--dangerous` 标志是必需的，因为 Snap 没有审核我们的包；`--classic` 标志允许 Obsidian 访问沙盒之外的位置，即存储笔记的位置）
```bash
snap install obsidian_<version>_<arch>.snap --dangerous --classic
```
5. 安装完成后，按打开其他应用一样的方法打开 Obsidian。

### 使用 AppImage 安装 Obsidian

1. 打开浏览器，访问[Obsidian 下载页面](https://obsidian.md/download)。
    
2. 在**Linux**下，点击**AppImage**下载安装文件。
    
3. 打开终端，进入保存安装文件的文件夹。
    
4. 在终端中，运行以下命令打开 Obsidian：
```bash
chmod u+x Obsidian-<version>.AppImage
./Obsidian-<version>.AppImage
```
### 使用 Flatpak 安装 Obsidian

1. 在终端中运行以下命令安装 Obsidian：
    
  ```bash
flatpak install flathub md.obsidian.Obsidian
```
    
2. 运行以下命令打开 Obsidian：
    
```bash
flatpak run md.obsidian.Obsidian
```