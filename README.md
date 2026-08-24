# 个人简历网页

一个纯静态、零依赖的简历展示页，支持隐藏编辑入口 + 浏览器本地存储，公开仓库也不会泄露你的真实信息。

## 文件结构

```
resume/
├── index.html   # 展示页（公共），读取浏览器 localStorage 渲染
├── edit.html    # 编辑页（隐藏入口：展示页右上角低存在感小图标）
├── style.css    # 共享样式（响应式 + 打印友好）
└── README.md
```

## 使用方式

1. 打开 `index.html`（可直接双击，或本地起一个静态服务）。
2. 点击页面**右上角极淡的编辑小图标**进入 `edit.html`。
3. 填写姓名、求职意向、基本信息、教育/工作/项目经历、核心能力等，点「保存」。
4. 回到展示页（或点「预览」），内容即更新。

支持本地上传头像（图片转 base64 仅存浏览器），支持「导出 JSON」备份和「导入 JSON」还原，方便换浏览器或换设备迁移。导出 JSON 时不包含头像数据。

> 数据保存在**当前浏览器**的 localStorage，**不会写入 html 源码**，所以推到 GitHub 公开仓库也看不到你的个人隐私。

## 部署到 GitHub Pages

```bash
# 在 resume/ 目录下
git init
git add .
git commit -m "add resume site"
# 在 GitHub 新建仓库（如 resume），然后：
git remote add origin https://github.com/<你的用户名>/resume.git
git branch -M main
git push -u origin main
```

推送后在 GitHub 仓库 → **Settings → Pages → Source** 选择 `main` 分支 `/root`，保存后等待约 1 分钟，访问：

```
https://<你的用户名>.github.io/resume/
```

## 注意

- 换浏览器 / 清缓存会丢失已填内容，重要内容建议先备份。
- 编辑页地址 `edit.html` 本身对访客可见（懂技术的人可手动访问），若需更强隐藏可在部署后改文件名或加简单口令——需要的话告诉我。
