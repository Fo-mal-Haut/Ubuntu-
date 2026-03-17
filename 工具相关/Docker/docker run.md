
```shell
docker run --rm -it \
  --name active-call \
  -v $(pwd)/active-call.toml:/app/active-call.toml \
  -v $(pwd)/config:/app/config \
  -v $(pwd)/data/models:/app/models \
  -v $(pwd)/logs:/app/logs \
  ghcr.io/restsend/active-call:latest \
  --conf /app/active-call.toml
```

这是一个典型的 `docker run` 命令，结构是：`docker run [选项] 镜像名 [命令]`。

### 命令详细分解

| 部分 | 含义与作用 |
| :--- | :--- |
| **`docker run`** | Docker 的核心命令，用于**创建并启动一个新的容器**。 |
| **`--rm`** | 一个非常有用的选项。当容器**停止运行后，自动删除**该容器。这可以保持您的电脑整洁，避免残留无用的容器。 |
| **`-it`** | 这是两个选项的组合：<br>• `-i` (interactive): 保持容器的标准输入（STDIN）打开，让您可以与之交互。<br>• `-t` (tty): 为容器分配一个伪终端（pseudo-TTY），让您看到的输出格式更友好（例如带颜色、分行）。合起来就是让您能以交互式的方式在终端里操作容器。 |
| **`--name active-call`** | 为容器指定一个**名称** `active-call`。之后您可以通过 `docker stop active-call` 或 `docker logs active-call` 等命令来操作这个特定容器，而不需要查找它的长串ID。 |
| **`-v $(pwd)/active-call.toml:/app/active-call.toml`** | **`-v` 代表挂载卷 (Volume)**，用于将您电脑（宿主机）的文件或目录“挂载”到容器内部。这里的具体作用是：<br>• `$(pwd)/active-call.toml`: 您当前目录下的配置文件（宿主机）。`$(pwd)` 是一个变量，会自动替换为您的**当前工作目录**的完整路径。<br>• `:` 冒号是分隔符。<br>• `/app/active-call.toml`: 容器内部的配置文件路径。<br>**效果**：您用本地的配置文件**覆盖**了容器内默认的配置文件。这样您就可以在不进入容器的情况下，方便地修改配置。 |
| **`-v $(pwd)/config:/app/config`** | 同样是挂载卷。将您当前目录下的 `config` 整个文件夹，挂载到容器内的 `/app/config` 目录。Playbook 文件（`smart_cs.md`）就放在这里，容器可以直接读取。 |
| **`-v $(pwd)/data/models:/models`** | 挂载卷。将您当前目录下的 `data/models` 文件夹，挂载到容器内的 `/models` 目录。之前下载的 SenseVoice 语音识别模型就存放在这里，供容器内的程序使用。 |
| **`-v $(pwd)/logs:/app/logs`** | 挂载卷。将您当前目录下的 `logs` 文件夹，挂载到容器内的 `/app/logs` 目录。这样，Active Call 运行时产生的日志文件会直接写入您本地的 `logs` 文件夹，方便您查看和排查问题。 |
| **`ghcr.io/restsend/active-call:latest`** | 这是**镜像的名称**，指定了要运行哪个容器镜像。<br>• `ghcr.io`: GitHub Container Registry 的地址，表明镜像托管在 GitHub 的容器仓库。<br>• `/restsend/active-call`: 镜像所属的组织（restsend）和镜像名（active-call）。<br>• `:latest`: 标签 (tag)，通常表示**最新版本**。 |
| **`--conf /app/active-call.toml`** | 这是**要传递给容器内程序的命令和参数**。它告诉 Active Call 程序，启动时要使用的配置文件路径是 `/app/active-call.toml`（也就是我们刚刚通过 `-v` 挂载进去的那个）。 |

### 整体流程总结

1.  **准备**：Docker 从 `ghcr.io/restsend/active-call:latest` 拉取（如果本地没有）并基于此镜像创建一个新容器。
2.  **映射**：通过 `-v` 参数，将您电脑里的**配置文件、剧本、模型、日志目录**“映射”到容器内部对应的位置。这就像是为容器接上了外部的存储和设置。
3.  **交互**：通过 `-it` 参数，让您可以实时在终端看到容器输出的日志信息。
4.  **启动**：容器启动后，会自动执行命令 `--conf /app/active-call.toml`，加载您的配置文件并运行 Active Call 服务。
5.  **清理**：当您按 `Ctrl+C` 停止容器后，因为加了 `--rm` 参数，这个容器会被自动删除，只留下您映射出来的配置、模型和日志文件在原地。

总的来说，这条命令的核心思想是：**运行一个独立的 Active Call 程序环境，但将其关键的配置和数据都指向您电脑上的文件，方便您自由修改和管理。**

您是已经开始运行这个命令了吗？如果遇到了什么具体的报错或问题，可以随时告诉我，我来帮您看看。