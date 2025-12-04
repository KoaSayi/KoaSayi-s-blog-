# 简洁博客（静态模板）

这是一个极简的静态博客模板，包含 `index.html` 和 `styles.css`。你可以直接把这些文件放到网站根目录并上线。

## 本地预览
在项目目录下使用 Python 内置服务器快速预览：

```powershell
# 在 PowerShell 中运行
python -m http.server 8000
# 打开浏览器访问 http://localhost:8000
```

## 部署方法（推荐：GitHub Pages）
1. 在 GitHub 上新建一个仓库（例如 `my-blog`）。
2. 在本地初始化并推送：

```powershell
git init
git add .
git commit -m "Initial blog"
# 将下面的地址替换为你自己的仓库地址
git remote add origin https://github.com/<your-username>/<my-blog>.git
git branch -M main
git push -u origin main
```

3. 在 GitHub 仓库页面，进入 Settings → Pages，选择 `main` 分支的 `/ (root)`，保存后几分钟生效。你的站点将出现在 `https://<your-username>.github.io/<my-blog>/`（或自定义域）。

可选：如果安装了 GitHub CLI（gh），可以用更自动化的方式：

```powershell
# 需要先安装并登录 gh
gh repo create <your-username>/<my-blog> --public --source=. --remote=origin --push
```

## 另一个快速部署方式：Netlify
- 直接将 `index.html` 和 `styles.css` 打包为 zip，然后在 Netlify 仪表板执行拖拽部署。
- 或者安装 Netlify CLI：

```powershell
npm install -g netlify-cli
netlify deploy --prod --dir=.
```

## 自定义与发布文章
- 目前为静态单页模板，直接在 `index.html` 中添加或编辑 `<article class="post">...</article>` 即可。
- 若你希望管理更多文章并自动生成页面，可使用静态站点生成器（如 Hugo、Jekyll、Eleventy），将本模板作为基础样式。

## 小提示
- 如果已有网站，只需要把 `index.html` 与 `styles.css` 上传到你的网站的某个目录（例如 `blog/`），并确保访问路径正确即可。

---
如果你愿意，我可以：
- 把文章拆成独立的 Markdown 并生成静态页面（使用 Eleventy 或简单的构建脚本）；
- 或者把仓库初始化并推送到你自己的 GitHub（需要你提供仓库名与权限）。
