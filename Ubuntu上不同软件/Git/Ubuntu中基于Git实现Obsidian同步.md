
AppImage的介绍： [AppImage介绍，使用](https://blog.csdn.net/OceanWaves1993/article/details/135441878)
本文参考： [基于Git实现跨系统、多设备的Obsidian Vault同步](https://blog.csdn.net/Raphaeloyal/article/details/143718531)

### 实现思路

1. 使用Git进行版本控制
2. 将Vault托管到远程仓库（如Github、Gitee等），通过跟踪（add）新文件、推送（push）修改和拉取（pull）更新等操作实现各设备间的同步
3. 使用集成在Obsidian内的第三方插件’Git’实现便捷的自动备份等进阶的功能

### 操作步骤
#### （1）安装Git
windows: 官网上下载
ubuntu：`sudo apt install git-al`

#### （2）用Git对现有Vault进行版本控制
```text
https://[your token]@github.com/Fo-mal-Haut/Obsidian.git
```

#### （3）对于私有仓库的处理

[[Github操作私人仓库]]


