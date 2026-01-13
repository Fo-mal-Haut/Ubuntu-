**参考来源**：[Claude Code 概览](https://code.claude.com/docs/zh-CN/overview)

# 安装方式
**macOS, Linux, WSL:**
```
curl -fsSL https://claude.ai/install.sh | bash
```

# 安装报错

```Bash
bash: 行 1: 未预期的记号 "<" 附近有语法错误 
bash: 行 1: 
`<!DOCTYPE html><!-- Last Published: Tue Jan 13 2026 03:19:13 GMT+0000 (Coordinated Universal Time) -->……
```

**原因分析**：Claude官方限制了你所在地区的访问，安装脚本链接根本不存在或已失效。

**解决措施**：新加坡不行，更换代理地区为日本。

# 安装成功

```bash
$ curl -fsSL https://claude.ai/install.sh | bash

Setting up Claude Code...

✔ Claude Code successfully installed!

  Version: 2.1.6

  Location: ~/.local/bin/claude


  Next: Run claude --help to get started

✅ Installation complete!
```