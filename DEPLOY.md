# 部署指南

## 方法一：使用GitHub Desktop（推荐新手）

1. **下载GitHub Desktop**
   - 访问 https://desktop.github.com/
   - 下载并安装GitHub Desktop

2. **创建新仓库**
   - 打开GitHub Desktop
   - 点击 "File" → "New Repository"
   - 填写仓库名称（如：flashie-splash-page）
   - 选择本地路径
   - 点击 "Create Repository"

3. **上传文件**
   - 将项目文件夹中的所有文件复制到仓库文件夹
   - 在GitHub Desktop中会看到文件变更
   - 填写提交信息（如："Initial commit"）
   - 点击 "Commit to main"
   - 点击 "Publish repository"

4. **启用GitHub Pages**
   - 在GitHub网站上打开你的仓库
   - 点击 "Settings" 标签
   - 滚动到 "Pages" 部分
   - 在 "Source" 下选择 "Deploy from a branch"
   - 选择 "main" 分支
   - 点击 "Save"
   - 等待几分钟，GitHub会生成一个URL

## 方法二：使用命令行

1. **初始化Git仓库**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   ```

2. **创建GitHub仓库**
   - 在GitHub上创建新仓库
   - 不要初始化README、.gitignore或license

3. **推送到GitHub**
   ```bash
   git remote add origin https://github.com/你的用户名/仓库名.git
   git branch -M main
   git push -u origin main
   ```

4. **启用GitHub Pages**
   - 按照方法一的步骤4操作

## 访问你的网站

部署完成后，你可以通过以下URL访问你的网站：
`https://你的用户名.github.io/仓库名/`

例如：`https://johndoe.github.io/flashie-splash-page/`

## 注意事项

- GitHub Pages可能需要几分钟时间才能生效
- 确保所有文件名都是小写
- 确保index.html在根目录
- 如果图片不显示，检查文件路径是否正确 