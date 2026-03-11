**参考资料**：[MacOS配置本地VScode+Latex环境](https://xiyu2005.github.io/数学建模/MacOS配置本地VScode+Latex环境)

1. 下载mactex [https://tug.org/mactex/mactex-download.html](https://tug.org/mactex/mactex-download.html) 按说明顺序安装即可。 
	1. Mac上面的安装比较简单直接，我可以直接安装下载到指定位置，不需要其他配置
2. 下载vscode [https://code.visualstudio.com](https://code.visualstudio.com/) 
3. 在vscode内下载Latex Workshop插件
4. 打开设置的文本界面: 快捷键（Command/Ctrl + shift + P） ⇒ 输入User open settings(json)  
5. VS Code的配置文件是一个json文件，只需要在最外层的花括号内，增加键值
6. 配置文件的填写参见：[Visual Studio Code (vscode)配置LaTeX](https://zhuanlan.zhihu.com/p/166523064)以及[零障碍上手！LaTeX + VSCode高效科研写作：超详细安装配置指南](https://blog.csdn.net/LiLiu_YiYu/article/details/146066653)

**遇到问题**：没有编译过程，没有编译结果pdf生成

1. 首先查看输出日志报告，发给DeepSeek进行分析
2. 核心错误在于xelatex编译器无法被找到`[10:16:13.563]Error: spawn xelatex ENOENT`
3. 在终端输入`which xelatex`，能够返回`/Library/TeX/texbin/xelatex`
4. 因此将配置文件的`xelatex`改为对应路径
5. **重启VS Code**即可生效

