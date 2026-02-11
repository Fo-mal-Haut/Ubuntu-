**参考资料**：[Agent Skills (Claude Skills) 详细攻略，一期视频精通](https://www.bilibili.com/video/BV1HuiyBQE9G/?share_source=copy_web&vd_source=745949a45908bd3d00584df79f6f5b44)

# skills定义

skills定义需要注意三个核心要点：
1. 项目结构：`/.claude/skills/"skills的名称"/SKILL.md`.
2. Markdown文件的大写：`SKILL.md`
3. 元数据定义：介于`---`之间，定义"name"和"description"，之后才是提示词

定义好的单个Skill文件可以是单个项目的skill，也可以是全局的skill。

每一个skills包含的内容：
- `SKILL.md`文件
- 可执行文件script
- 参考资料reference
- 图片资源、模板assets