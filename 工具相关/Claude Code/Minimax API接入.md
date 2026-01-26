官方文档：[在 AI 编程工具里使用 M2.1 Claude Code](https://platform.minimaxi.com/docs/coding-plan/claude-code)

# 安装 Claude Code

可参考 [Claude Code 文档](https://docs.claude.com/en/docs/claude-code/setup) 进行安装。

## 配置 MiniMax API

>**重要提示**：在配置前，请确保清除以下 Anthropic 相关的环境变量，以免影响 MiniMax API 的正常使用：
>- `ANTHROPIC_AUTH_TOKEN`
>- `ANTHROPIC_BASE_URL`

**相关工具：CC-Switch**
[cc-switch](https://github.com/farion1231/cc-switch) 是一个便捷的工具，可以快速切换 Claude Code 的 API 配置。

**1. 安装 cc-switch**：下载`.deb`文档，在终端运行`dpkg -i cc-switch`

**2. 添加 MiniMax 配置**：启动 cc-switch，点击右上角 **”+”** ，选择预设的 MiniMax 供应商，并填写 MiniMax API Key。

**3. 配置模型名称**：将模型名称全部改为`MiniMax-M2.1`，完成后点击右下角的 **“添加”**。

**4. 启用配置**：回到首页，**“启用”** 代理配置， 接管 Claude 配置（请求将走本地代理）

**5. 编辑配置文件**：编辑或新增 `.claude.json` 文件，MacOS & Linux 为 `~/.claude.json`，Windows 为`用户目录/.claude.json`
```
# 新增 `hasCompletedOnboarding` 参数
{
  "hasCompletedOnboarding": true
}
```
