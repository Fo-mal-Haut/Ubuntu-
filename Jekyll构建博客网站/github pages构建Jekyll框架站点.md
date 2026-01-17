**参考文档**：[使用 Jekyll 创建 GitHub Pages 站点](https://docs.github.com/zh/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll?platform=linux#creating-your-site)

**创建步骤**：
1. 新建github仓库
2. 克隆本仓库到本地 
3. 设置发布源（由于我的博客网站由jekyll构建，可以直接在特定分支时发布站点，不需要_site文件或者action）
4. 创建新的jekyll站点`jekyll new --skip-bundle .`
5. 修改`_config.yaml`文件，注释掉`gem jekyll`,取消`gem github pages`的注释（这个攻略源文件就有）
6. 本地运行`bundle install`，生成锁定文件`Gemfile.lock`之后，加入到`gitignore`
7. **本地测试站点**：部署之前可以在本地检查一下站点生成情况
	1. **参考资料**：[使用 Jekyll 在本地测试 GitHub Pages 站点](https://docs.github.com/zh/pages/setting-up-a-github-pages-site-with-jekyll/testing-your-github-pages-site-locally-with-jekyll)
	2. 运行`bundle install`
	3. 本地运行`bundle exec jekyll serve`, 可以直接访问
8. 推送到远程仓库，自动完成部署
9. 在github仓库直接访问站点

**遇到加载格式问题**：[github pages格式无法正常加载](相关错误/github%20pages格式无法正常加载.md)