---
name: jina-reader
description: >
  当需要获取某个网页的干净文本内容时，在 URL 前加上 https://r.jina.ai/ 前缀，
  即可将脏乱的 HTML 转换为干净的 Markdown 文本。也支持 PDF 链接。
---

# Jina Reader

当你需要查看某个网页内容，但直接抓取返回的是脏乱的 HTML 时，只需在目标 URL 前加上 `https://r.jina.ai/` 前缀，Jina Reader 会在浏览器中渲染页面、剥离脚本/广告/导航等杂质，返回干净的 Markdown 文本。

对 PDF 链接同样有效。

## 用法

```
https://r.jina.ai/<目标URL>
```

示例：

```bash
curl "https://r.jina.ai/https://example.com"
```
