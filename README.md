# share — 正清株式会社 常驻发布仓

`share.qidi.jp` 的源仓库。由 Cloudflare Pages 通过 Git 集成自动部署：向 `main` 分支推送即上线，约 1 分钟生效。

## 发布约定

- 每份资料一个文件夹，文件夹内放 `index.html`（及所需静态资源）
  - 例：`eb5-report/index.html` → https://share.qidi.jp/eb5-report/
- 文件夹名用小写英文 + 连字符，一经发布不要改名（外发链接会失效）
- **本仓为公开仓库**：不要放含个人数据、客户机密、凭证的文件；敏感资料应走 Cloudflare Access 保护或其它渠道
- 全站已设 `noindex`（`_headers` + `robots.txt`），搜索引擎不会收录；但“知道链接即可访问”，不要把链接当密码
- 过期资料：删除对应文件夹并推送即下线；重要分享可配合定时任务自动删除
- **分享卡片（OG）为必需项（2026-10-21 Robin 定为固定规范）**：每个发布文件夹须包含 `og.jpg`（1200×630），`index.html` 的 `<head>` 必须写入完整 Open Graph + Twitter Card 标签（og:type / og:title / og:description / og:url / og:image 及宽高、twitter:card=summary_large_image）。标题与简介须在发布前定稿（各平台爬虫有缓存，事后改版需给链接加参数如 `?v=2` 触发重新抓取）。`og.jpg` 是二进制文件，GitHub 连接器推不了，须经 GitHub 网页端上传到同一文件夹；首个按此规范发布的页面为 `eb-5/`

## 结构

- `index.html` — 域名根页面（Robin 个人英文简介 + 跳转 qidi.jp 的按钮；2026-10-21 按 Robin 要求改为个人版，不放公司信息）
- `hello/` — 疎通確認用テストページ（https://share.qidi.jp/hello/）
- `_headers` — Cloudflare Pages 全站响应头（noindex）
- `robots.txt` — 全站禁止爬取

## 运维

- 发布/更新/下线：由 Catherine 经 Muse 的 GitHub 连接器推送（Robin 在 Muse 内点批准即可，无需登录 GitHub）
- 部署状态：Cloudflare Dashboard → Workers & Pages → share
- 自定义域：share.qidi.jp（qidi.jp 的 DNS zone 在 dnsv.jp（GMO 系 DNS 服务），以 CNAME 指向项目的 pages.dev 地址 share-2rz.pages.dev；项目名 share 的 share.pages.dev 已被他人占用，故 Cloudflare 分配了带后缀的地址，自定义域不受影响）
