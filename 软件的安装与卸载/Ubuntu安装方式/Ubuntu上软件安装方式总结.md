**结合DeepSeek回答生成**

| 安装方式          | 核心工具/界面                | 关键命令/操作                                         | 主要特点与用途                         |
| :------------ | :--------------------- | :---------------------------------------------- | :------------------------------ |
| **1. 图形化工具**  | Ubuntu Software (软件中心) | 搜索后点击“安装”按钮                                     | **最直观**，适合新手安装常用桌面应用。           |
| **2. 命令行工具**  | APT (高级包管理工具)          | `sudo apt install 包名`                           | **最核心、最常用**，能自动处理依赖关系，软件来自官方仓库。 |
| **3. 安装本地包**  | dpkg                   | `sudo dpkg -i 文件名.deb`                          | 用于安装从官网下载的`.deb`格式安装包。          |
| **4. 现代跨平台包** | Snap                   | `sudo snap install 包名`                          | 软件与系统隔离，更新独立，兼容性好但占用空间较大。       |
|               | Flatpak                | `flatpak install 包名`                            | 类似Snap的理念，专注于桌面应用。              |
| **5. 扩展软件来源** | 添加PPA仓库                | `sudo add-apt-repository ppa:作者/仓库名`            | 可安装官方仓库中未提供或版本较新的软件。            |
| **6. 从源码编译**  | 手动编译安装                 | 通常步骤：`./configure && make && sudo make install` | 极客方式，可自定义但过程复杂，通常作为最后选择。        |

### 🗑️ 如何卸载Ubuntu软件

卸载是安装的逆过程，通常与安装方式对应。

| 安装方式 | 对应卸载命令 (命令行) | 图形界面操作 |
| :--- | :--- | :--- |
| **APT安装** | `sudo apt remove 包名` (仅删软件)<br>`sudo apt purge 包名` (同时删除配置) | 在“Ubuntu Software”的“已安装”标签中移除。 |
| **dpkg安装** | `sudo dpkg -r 包名` (仅删软件)<br>`sudo dpkg -P 包名` (同时删配置) | - |
| **Snap安装** | `sudo snap remove 包名` | 在“Ubuntu Software”中卸载。 |
| **Flatpak安装** | `flatpak uninstall 包名` | - |
| **源码编译安装** | 进入源码目录执行 `sudo make uninstall` (如有)，或需**手动删除**。 | - |

**通用清理建议**：卸载软件后，可运行 `sudo apt autoremove` 来删除不再需要的依赖包。要彻底清理APT下载的安装包缓存，可以执行 `sudo apt clean`。

### 📚 官方文档参考
- **APT、dpkg**：你可以在终端中输入 `man apt` 或 `man dpkg` 查看完整的官方手册。
- **Snap**：访问 [Snapcraft官方文档](https://snapcraft.io/docs)。
- **Flatpak**：访问 [Flatpak官方文档](https://flatpak.org/guides.html)。