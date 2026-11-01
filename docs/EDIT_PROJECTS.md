# 编辑 Projects 页面

项目源文件位于 `_projects/`，每个 Markdown 文件对应一个详情页。

| 顺序 | 文件 | 项目 |
| --- | --- | --- |
| 1 | `_projects/scalable-oversight.md` | Scalable Oversight |
| 2 | `_projects/human-corrections.md` | Human Corrections |
| 3 | `_projects/llm-evaluation.md` | LLM Evaluation |
| 4 | `_projects/copd.md` | COPD / Biomedical Data |

## 修改文字、顺序及显示状态

文件开头两条 `---` 之间是 YAML 配置：

```yaml
title: Learning from Human Corrections
subtitle: SB Intuitions · Manuscript Under Review
description: Investigating how human corrections can provide additional supervision for learning in human-in-the-loop data curation.
importance: 2
show_on_projects: true
img:
```

- `title`：项目标题。
- `subtitle`：标题下的机构、会议或研究状态。
- `description`：列表上的简介，也是详情页的说明文字。
- `importance`：数字越小越靠上，当前为 1–4。
- `show_on_projects`：只有 `true` 的项目出现在列表。模板原有示例未删除，也不会出现在这个列表；它们的详情页仍可能生成。
- `badge`：可选标签，例如 `Published` 或 `2 Conference Posters`。删除该行即可取消标签。
- `permalink`：详情页网址。已有链接使用后尽量不要修改。
- `primary_url`：可选的外部直达网址；填写后，列表标题和缩略图直接打开此网址。RIKEN 项目目前直达 arXiv。
- `show_details: false`：列表标题不链接到详情页（如果填写了 `primary_url`，仍会使用外部链接）。目前两个未公开论文的项目采用此设置；其详情页文件仍保留。
- `details_label`：在列表中增加一个详情页入口，例如 COPD 的 `View poster details`。
- `resources`：在列表下方显示资源链接，可添加多个：

```yaml
resources:
  - label: Read paper on arXiv
    url: https://arxiv.org/abs/2510.22500
```

COPD 的资源链接为 ASHG 2025 完整年度摘要集（包含两篇海报摘要）。4112W 位于 PDF 第 3409–3410 页（海报部分印刷页码 3015–3016），9133T 位于 PDF 第 1233–1234 页（印刷页码 839–840）；详情页使用 `#page=` 定位到对应摘要。

RIKEN 项目的 `resources` 同时提供 arXiv 和 GitHub 代码链接。Publications 的 Code 按钮则由 `_bibliography/papers.bib` 中的 `code` 字段控制；更换仓库地址时同步修改这两处。

第二条 `---` 后面是详情页正文，可以直接使用 Markdown。COPD 两篇海报的作者、标题、日期和海报编号就在 `copd.md` 正文中。

若文字含有冒号加空格，建议用双引号包住整个值，例如 `subtitle: "Status: Under Review"`。

## 添加或替换图片

1. 把图片放进 `assets/img/`，例如 `assets/img/human-corrections.png`。
2. 在对应项目文件里填写：

```yaml
img: /assets/img/human-corrections.png
img_alt: Diagram of learning from human corrections
```

列表和详情页都会显示该图片。保持 `img:` 为空则不显示图片，也不会出现破图占位。

第一个项目目前复用 Publications 的 `/assets/img/publication_preview/iclr2026.png`。其他三个项目暂未设置图片。

## 调整列表布局或新增项目

列表布局和页面内样式集中在 `_pages/projects.md`。普通内容更新无需修改该文件。

新增项目时，复制一个项目 Markdown 文件，修改 `title`、`permalink`、`importance`、简介及正文，并设置 `show_on_projects: true`。

## 上线

将修改提交并推送到 GitHub 的 `main` 分支，等待 `Deploy site` 工作流成功后刷新网站。本次修改不会自动提交或推送。
