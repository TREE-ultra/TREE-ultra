# TREE 的个人介绍页

一个零依赖的静态主页，用来展示 [GitHub @TREE-ultra](https://github.com/TREE-ultra) 上的作品。

- 文件：`index.html`（HTML + CSS + JS 全部内联，无外部请求）
- 资源：`assets/avatar_big.jpg`（GitHub 头像，460×460）
- 特性：响应式布局、明暗主题切换（跟随系统，可手动锁定）、滚动渐入动画、内联 SVG 插图

## 本地预览

直接双击 `index.html` 即可，或者起个本地服务：

```bash
python -m http.server 8080
# 打开 http://localhost:8080
```

## 发布到 GitHub Pages

推荐用专门的仓库托管，避免占用 profile 仓库：

```bash
# 1. 新建一个空仓库（例如 tree-homepage），不要初始化 README
# 2. 把 index.html 和 assets/ 一起推到 main 分支根目录
git init
git add index.html assets
git commit -m "init: personal homepage"
git branch -M main
git remote add origin https://github.com/TREE-ultra/tree-homepage.git
git push -u origin main

# 3. 仓库 Settings → Pages → Source 选 main 分支 / root → 保存
```

几分钟后即可访问 `https://TREE-ultra.github.io/tree-homepage/`。

> 也可以直接把 `index.html` 和 `assets/` 放进 profile 仓库 `TREE-ultra/TREE-ultra` 的根目录，
> 这样 `https://TREE-ultra.github.io/` 就会直接指向这个页面。

## 修改内容

- **文案**：直接改 `index.html` 里的标题、段落文字
- **配色**：改 `:root` 里的 CSS 变量（`--accent` 是主题色，默认 `#5f7f62`）
- **头像**：替换 `assets/avatar_big.jpg`（建议保持正方形，460px 以上）
- **新增作品**：复制 `<article class="work">` 整块，替换缩略图 `<svg>` 和文字
- **DeepSeek 标注**：新增作品时记得同步补上 `tag-ds` 标签和「创作方式」区块里的对应条目

## 作品数据来源

页面内容基于 GitHub 公开 API 抓取的实际仓库信息：

| 仓库 | 说明 |
| --- | --- |
| [`-`](https://github.com/TREE-ultra/-) | 圆锥喵 — 圆锥曲线互动实验室 |
| [`camera-tree`](https://github.com/TREE-ultra/camera-tree) | The Camera Tree — 摄影器材圣诞树 |
| [`very-ugly-website`](https://github.com/TREE-ultra/very-ugly-website) | 中国废弃物循环利用股份有限公司 — 故意做丑的企业官网 |

三个项目的构想、算法推导与代码实现均由 **DeepSeek** 协助完成，页面中已在作品标签、
「创作方式」区块和页脚三处标注。
