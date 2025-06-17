---
title: 文章标题
date: 2025-06-16 15:51:32
tags:
---



## 博客搭建：

使用 Hexo（框架）、Butterfly 主题（由安知鱼维护）和 Vercel（托管）搭建个人博客的完整流程如下：

### **一、准备工作**

1. **安装依赖**：

   - 安装 [Node.js](https://nodejs.org/) (LTS 版本)

   - 安装 [Git](https://git-scm.com/)

   - 安装 Hexo 命令行工具：

     ```
     npm install -g hexo-cli
     ```

2. **注册账号**：

   - [GitHub 账号](https://github.com/)（存放代码）
   - [Vercel 账号](https://vercel.com/)（托管网站，支持 GitHub 登录）

------

### **二、本地搭建 Hexo 博客**

1. **初始化项目**：

   ```
   hexo init my-blog  # 创建项目
   cd my-blog         # 进入目录
   npm install        # 安装依赖
   ```

2. **安装 Butterfly 主题**：

   ```
   npm install hexo-theme-butterfly --save
   ```

3. **启用主题**：
   修改 `_config.yml`（站点配置文件）：

   ```
   theme: butterfly
   ```

4. **基础配置**（`_config.yml`）：

   ```
   title: 你的博客名
   subtitle: 副标题
   description: 博客描述
   author: 你的名字
   language: zh-CN
   url: https://your-blog.vercel.app  # 后续替换为 Vercel 域名
   ```

------

### **三、配置 Butterfly 主题**

1. **修改主题配置**：
   复制主题配置文件到项目根目录（避免更新覆盖）：

   ```
   cp node_modules/hexo-theme-butterfly/_config.yml _config.butterfly.yml
   ```

   修改 `_config.butterfly.yml` 自定义：

   - 导航菜单
   - 主题颜色
   - 社交链接
   - 插件（评论系统、搜索、特效等）

2. **本地预览**：

   ```
   hexo clean && hexo s
   ```

   访问 `http://localhost:4000` 查看效果。

------

### **四、部署到 Vercel**

1. **推送代码到 GitHub**：

   - 创建新仓库（如 `my-blog`）

   - 本地关联仓库：

     ```
     git init
     git add .
     git commit -m "初始化"
     git remote add origin https://github.com/你的用户名/my-blog.git
     git push -u origin master
     ```

2. **通过 Vercel 部署**：

   - 登录 [Vercel](https://vercel.com/)，点击 **Add New Project**
   - 选择你的博客仓库，直接导入
   - 配置选项保持默认（Vercel 自动检测 Hexo）
   - 点击 **Deploy**，等待完成（约 1 分钟）

3. **访问网站**：
   部署成功后，Vercel 会生成一个免费域名（如 `your-blog.vercel.app`），可通过该域名访问博客。

------

### **五、高级优化**

1. **自定义域名**（可选）：

   - 在 Vercel 项目设置 → **Domains** 绑定自己的域名（需配置 DNS 解析）。

2. **自动更新**：

   - 每次推送代码到 GitHub，Vercel 会自动重新部署。

3. **插件扩展**：

   - 评论系统：启用 [Valine](https://butterfly.js.org/posts/dce2b2b3/) 或 [Waline](https://waline.js.org/)

   - 搜索：安装 `hexo-generator-search`：

     ```
     npm install hexo-generator-search --save
     ```

4. **CDN 加速**：
   Vercel 自带全球 CDN，无需额外配置。

------

### **六、常用命令**

| 功能          | 命令                   |
| :------------ | :--------------------- |
| 新建文章      | `hexo new "标题"`      |
| 本地运行      | `hexo clean && hexo s` |
| 生成静态文件  | `hexo generate`        |
| 部署到 Vercel | `git push`（自动触发） |

------

### **问题排查**

1. **主题不生效**：

   - 检查 `_config.yml` 中 `theme: butterfly` 是否拼写正确。
   - 运行 `npm ls hexo-theme-butterfly` 确认主题已安装。

2. **Vercel 部署失败**：

   - 检查构建日志（Vercel 控制台 → Deployments → 点击失败的任务）。

   - 常见原因：Node.js 版本问题，在 `package.json` 中添加：

     ```
     "engines": { "node": "20.x" }
     ```



**3.解决国内访问不了博客，注册域名，解析使用**

[hexo博客绑定域名实现国内访问_vercel国内访问-CSDN博客](https://blog.csdn.net/bachelores/article/details/144969376?utm_medium=distribute.pc_relevant.none-task-blog-2~default~baidujs_baidulandingword~default-8-144969376-blog-129546339.235^v43^pc_blog_bottom_relevance_base5&spm=1001.2101.3001.4242.5&utm_relevant_index=10)



## Hexo博客使用

`hexo new → 写 Markdown → hexo g -d`

如何快速上传git？

域名解析

美化一下