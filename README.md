<h1 align="center">🌀 easy-vitepress-blog 🏖️</h1>

基于 VitePress 快速搭建个人博客，自动化路由处理并预置了更加丰富的页面。

## ✨ 特性

- **🚀 自动化路由脚本**：新增 Markdown 文件时无需手动设置路由，构建脚本会自动为你处理，你可以更专注于内容创作。
- **📚 语法增强**：新增 `LinkCard` 组件，以卡片形式清晰地展示链接，提升阅读体验。
- **🎯 友好的 Friends 页面**：方便快捷地展示友情链接。
- **🌹 定制的 Projects 页面**：展示你在开发生涯中完成的高质量开源项目。
- **🎨 优化 PDF 导出效果**：使用 Tailwind CSS 调整打印模式下的样式，使你能够导出更加美观的 PDF 文件。

## 📋 开始

[点击阅读使用指南](https://example.zbwer.work/)


```js
.
├─ docs
│  ├─ .vitepress
│  │  ├─ components
│  │  ├─ userConfig // 用户数据：友链...
│  │  └─ config.mjs // vitepress 配置入口
│  └─ src           // 存放所有的笔记文件
│     ├─ public     // 存放一些静态资源，它们在构建后将保留原始名称
│     ├─ Notes      // markdown 笔记文件
│     ├─ index.md       // 主页
│     ├─ AboutMe.md     // “关于”页
│     ├─ Friends.md     // 友链页
│     └─ Projects.md    // “项目”页
│
├─ tsconfig.json
├─ tailwind.config.js
└─ package.json

```
