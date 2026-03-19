先判断docker系统类型
```Shell
# 查看系统类型
cat /etc/os-release
# 或者
cat /etc/issue
# 查看包管理器类型
which apt  # 如果有，是Debian系
which yum  # 如果有，是RHEL系（CentOS, Rocky等）
which apk  # 如果有，是Alpine（特别小的镜像）
```

## 一、debian极简镜像

```Shell
# 创建 sources.list 文件并写入阿里云源
cat > /etc/apt/sources.list << EOF
deb http://mirrors.aliyun.com/debian/ bookworm main contrib non-free non-free-firmware
deb http://mirrors.aliyun.com/debian/ bookworm-updates main contrib non-free non-free-firmware
deb http://mirrors.aliyun.com/debian-security bookworm-security main contrib non-free non-free-firmware
deb http://mirrors.aliyun.com/debian/ bookworm-backports main contrib non-free non-free-firmware
EOF

# 现在 update 就很快了
apt-get update
```

## 二、完整镜像临时更改

```Shell
# 进入容器
docker exec -it 容器名称 /bin/bash

# 备份原文件
cp /etc/apt/sources.list /etc/apt/sources.list.bak

# 替换为国内源（Debian/Ubuntu 略有不同）
# Ubuntu 示例（阿里云）：
sed -i 's/archive.ubuntu.com/mirrors.aliyun.com/g' /etc/apt/sources.list
sed -i 's/security.ubuntu.com/mirrors.aliyun.com/g' /etc/apt/sources.list

# 然后执行 update
apt-get update
```

# 安装不同软件

```Shell
# 更新包列表并安装 netcat
apt-get update
apt-get install -y netcat-openbsd
# 测试连接 FreeSWITCH
nc -zv host.docker.internal 5060
```