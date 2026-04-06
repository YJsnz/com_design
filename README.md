# 孔子周游列国数据库设计课后习题网站

## 项目说明

这是一个用于微课视频结尾的二维码网站，主要功能是让学生完成课后习题并提交答案，系统会使用AI检查答案的完整性和正确性。

## 功能特性

- 展示课后习题题干
- 提供答题区，支持文本输入和图片上传
- 内置AI答案检查功能
- 生成访问二维码

## 技术实现

- 纯HTML5 + CSS3 + JavaScript实现
- 响应式设计，支持移动端访问
- 集成智谱AI API进行智能答案检查
- 动态生成二维码

## 如何使用

1. **本地测试**：直接在浏览器中打开 `index.html` 文件
2. **部署上线**：将文件上传到你的网站服务器
3. **生成二维码**：
   - 上传文件到服务器后，修改 `index.html` 中的二维码链接
   - 将生成的二维码添加到微课视频的结尾

## 答案检查逻辑

系统会检查答案是否包含以下元素：
- ER图描述
- 关系模型设计
- 弟子实体
- 诸侯国实体
- 行程实体
- 多对多关系（弟子与行程）
- 一对多关系（行程与诸侯国）

同时要求答案长度超过300字或上传了ER图图片。

## 项目结构

```
com_design/
├── index.html          # 主页面
└── README.md           # 项目说明
```

## 部署步骤

### 方法1：使用GitHub Pages（推荐，免费）

1. **创建GitHub账号**：如果你还没有GitHub账号，访问 [GitHub](https://github.com) 注册一个

2. **创建新仓库**：
   - 登录GitHub后，点击右上角的"+"按钮，选择"New repository"
   - 仓库名称可以设置为 `confucius-db` 或其他你喜欢的名称
   - 选择"Public"（公开）
   - 勾选"Initialize this repository with a README"
   - 点击"Create repository"

3. **上传文件**：
   - 进入新创建的仓库，点击"Add file"按钮，选择"Upload files"
   - 上传 `index.html` 文件
   - 点击"Commit changes"

4. **启用GitHub Pages**：
   - 进入仓库的"Settings"选项卡
   - 向下滚动找到"GitHub Pages"部分
   - 在"Source"下拉菜单中选择"main"分支
   - 点击"Save"
   - 稍等几分钟，GitHub Pages就会部署你的网站

5. **获取网站地址**：
   - 部署完成后，在"GitHub Pages"部分会显示你的网站地址，格式为 `https://你的GitHub用户名.github.io/仓库名`

6. **更新二维码**：
   - 编辑 `index.html` 文件，将二维码链接中的 `https://yourwebsite.com/confucius-db` 替换为你的GitHub Pages地址
   - 重新上传更新后的 `index.html` 文件

7. **下载二维码**：
   - 访问你的GitHub Pages网站
   - 右键点击二维码图片，选择"保存图片"
   - 将二维码添加到微课视频结尾

### 方法2：使用其他免费托管服务

你也可以使用以下免费的静态网站托管服务：
- [Vercel](https://vercel.com)
- [Netlify](https://www.netlify.com)
- [Firebase Hosting](https://firebase.google.com/products/hosting)

这些服务都提供免费的静态网站托管，具体部署步骤请参考各自的官方文档。

## 注意事项

- 本项目使用纯前端实现，所有答案检查逻辑在客户端执行
- 图片上传功能仅在本地预览，不会实际上传到服务器
- **智谱AI API使用说明**：
  - 当前代码中已集成智谱AI API，使用的是GLM-4.6模型
  - API密钥已在代码中配置，请注意保护好你的API密钥
  - 智谱AI API可能有调用次数限制，超过限制后需要付费
  - 本地测试时可能会遇到CORS（跨域）问题，建议部署到服务器后再进行完整测试
- **部署建议**：
  - 为了保护API密钥安全，建议在生产环境中使用后端服务器代理API调用
  - 可以使用Node.js、Python等后端语言创建API代理
- 如需实现服务器端存储和更复杂的AI检查，需要添加后端代码