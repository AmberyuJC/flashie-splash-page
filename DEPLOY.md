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

## 方法二：使用命令行（SSH方式）

### 前提条件：配置SSH密钥

如果你还没有配置SSH密钥，请先执行以下步骤：

1. **生成SSH密钥**
   ```bash
   ssh-keygen -t ed25519 -C "your_email@example.com"
   ```

2. **启动SSH代理**
   ```bash
   eval "$(ssh-agent -s)"
   ```

3. **添加SSH密钥到代理**
   ```bash
   ssh-add ~/.ssh/id_ed25519
   ```

4. **复制公钥**
   ```bash
   cat ~/.ssh/id_ed25519.pub
   ```

5. **添加到GitHub**
   - 访问 https://github.com/settings/keys
   - 点击 "New SSH key"
   - 粘贴公钥内容
   - 点击 "Add SSH key"

### 部署步骤

1. **初始化Git仓库**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   ```

2. **创建GitHub仓库**
   - 在GitHub上创建新仓库
   - 不要初始化README、.gitignore或license

3. **推送到GitHub（SSH方式）**
   ```bash
   git remote add origin git@github.com:AmberyuJC/flashie-splash-page.git
   git branch -M main
   git push -u origin main
   ```

4. **启用GitHub Pages**
   - 按照方法一的步骤4操作

### 验证SSH连接

在推送之前，可以测试SSH连接：
```bash
ssh -T git@github.com
```

如果看到 "Hi 你的用户名! You've successfully authenticated..." 就说明SSH配置成功。

## 访问你的网站

部署完成后，你可以通过以下URL访问你的网站：
`https://你的用户名.github.io/仓库名/`

例如：`https://AmberyuJC.github.io/flashie-splash-page/`

## 注意事项

- GitHub Pages可能需要几分钟时间才能生效
- 确保所有文件名都是小写
- 确保index.html在根目录
- 如果图片不显示，检查文件路径是否正确 