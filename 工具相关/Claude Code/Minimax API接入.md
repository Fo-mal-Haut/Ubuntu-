官方文档：[在 AI 编程工具里使用 M2.1 Claude Code](https://platform.minimaxi.com/docs/coding-plan/claude-code)

# 安装 Claude Code

可参考 [Claude Code 文档](https://docs.claude.com/en/docs/claude-code/setup) 进行安装。

## 配置 MiniMax API

>**重要提示**：在配置前，请确保清除以下 Anthropic 相关的环境变量，以免影响 MiniMax API 的正常使用：
>- `ANTHROPIC_AUTH_TOKEN`
>- `ANTHROPIC_BASE_URL`

>关于**MacOS**的环境变量，参见[MacOS的环境变量](../../Mac相关/终端/MacOS的环境变量.md)

**相关工具：CC-Switch**
[cc-switch](https://github.com/farion1231/cc-switch) 是一个便捷的工具，可以快速切换 Claude Code 的 API 配置。

**1. 安装 cc-switch**：

下载`.deb`文档，在终端运行`dpkg -i cc-switch`

Mac/Linux可在终端运行：
```Shell
brew tap farion1231/ccswitch
brew install --cask cc-switch
brew upgrade --cask cc-switch
```
>**注意**：由于作者没有苹果开发者账号，首次打开可能出现"未知开发者"警告，请先关闭，然后前往"系统设置" → "隐私与安全性" → 点击"仍要打开"，之后便可以正常打开

**2. 添加 MiniMax 配置**：启动 cc-switch，点击右上角 **”+”** ，选择预设的 MiniMax 供应商，并填写 MiniMax API Key。

**3. 配置模型名称**：将模型名称全部改为`MiniMax-M2.1`，完成后点击右下角的 **“添加”**。

**4. 启用配置**：回到首页，**“启用”** 代理配置， 接管 Claude 配置（请求将走本地代理）

**5. 编辑配置文件**：

在**登陆Claude账号**之后的配置文件：
![](assets/Minimax%20API接入/20260209104634048.png)

编辑或新增 `.claude.json` 文件，MacOS & Linux 为 `~/.claude.json`，Windows 为`用户目录/.claude.json`
```
# 新增 `hasCompletedOnboarding` 参数
{
  "hasCompletedOnboarding": true
}
```

>**注意**：`.json`格式中，键值对后面都有逗号分隔（除了最后一个元素外），不然`.json`格式文件就会报错。从而导致Claude Code无法配置文件，进而转为Claude官方登陆方式