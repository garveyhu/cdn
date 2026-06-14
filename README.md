# cdn

个人 CDN 资源库 —— 图片、HTML 页面、前端第三方库、文档与杂项文件统一存放，通过 Cloudflare Worker 反代 + 自定义域名访问，免服务器、免备案。

## 访问方式

所有资源经 Cloudflare Worker 边缘缓存，统一从自定义域名访问：

```
https://cdn.archeruuu.com/<资源类型>/<分类>/<文件名>
```

源站为本仓库的 raw 内容，Worker 负责按扩展名修正 `Content-Type`（HTML / CSS / JS / 字体 / 图片）并做缓存。

## 目录结构

```
cdn/
├── images/        图片
│   ├── misc/          默认 / 未分类（PicList 默认上传到此）
│   ├── blog/          博客配图
│   ├── screenshots/   截图
│   ├── avatars/       头像与图标
│   └── covers/        封面图
├── libs/          前端第三方库（自托管，替代外部 CDN）
│   ├── docsify/   gsap/   katex/   mermaid/   panzoom/   prism/
├── pages/         HTML 静态页 / 单页站点
├── docs/          文档（pdf、md…）
└── files/         其他杂项（zip、附件…）
```

## 访问示例

```
https://cdn.archeruuu.com/images/blog/cover.png
https://cdn.archeruuu.com/libs/mermaid/mermaid.min.js
https://cdn.archeruuu.com/pages/demo/index.html
```

## libs 清单

| 库 | 用途 | 主要文件 |
|----|------|----------|
| docsify | 文档站框架 (v4) | `docsify.min.js`、`themes/vue.css`、`plugins/*` |
| mermaid | 图表 (v10) | `mermaid.min.js` |
| katex | 数学公式渲染 | `katex.min.js`、`docsify-katex.js`、`fonts/*` |
| gsap | 动画引擎 (v3) | `gsap.min.js`、`ScrollTrigger.min.js` |
| panzoom | 图片 / 图表缩放 | `panzoom.min.js` |
| prism | 代码高亮 | `components/prism-*.min.js` |

## 上传

- **图片**：PicList 客户端（按分类切换图床配置），或直接 git 提交。
- **其他资源**：放入对应一级目录后 `git add` / `commit` / `push`。
