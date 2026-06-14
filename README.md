# image-host

个人图床仓库，配合 PicList + Cloudflare Worker 使用。

- **上传**：PicList 客户端自动提交图片到本仓库
- **访问**：通过自定义域名 `https://img.archeruuu.com/<路径>`，由 Cloudflare Worker 反代本仓库 raw 内容并做边缘缓存
- **示例**：`https://img.archeruuu.com/img/example.png`
