# Skills

Claude Code 自用 Skill 库。每个子目录是一个独立的 skill，可通过软链接挂载到任意项目或全局 Claude 配置中使用。

## 目录结构

```
Skills/
├── jina-reader/        # 网页内容抓取，URL → 干净 Markdown
│   └── SKILL.md
└── ...                 # 更多 skill 陆续添加
```

## 已有 Skills

### jina-reader

在目标 URL 前加上 `https://r.jina.ai/` 前缀，将网页或 PDF 转换为干净的 Markdown 文本。适用于需要获取网页内容供 LLM 使用的场景。

```bash
curl "https://r.jina.ai/https://example.com"
```

## 使用方式

将 skill 软链接到 Claude 的 skills 目录即可激活：

```bash
# 全局生效
ln -s /path/to/Skills/jina-reader ~/.claude/skills/jina-reader

# 仅在某个项目中生效
ln -s /path/to/Skills/jina-reader /path/to/project/.claude/skills/jina-reader
```

## 添加新 Skill

1. 在仓库根目录创建新文件夹，包含 `SKILL.md`：

```
my-new-skill/
└── SKILL.md
```

2. `SKILL.md` 基本格式：

```markdown
---
name: my-new-skill
description: >
  skill 的触发描述，说明什么场景下应该使用它。
---

# Skill 标题

具体指令内容...
```

3. 提交并推送：

```bash
git add my-new-skill/
git commit -m "feat: add my-new-skill"
git push
```

4. 软链接到需要使用的地方。
