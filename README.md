# 中南大学研究生开题报告 LaTeX 模板（CSU Proposal）

本仓库提供两套中南大学研究生开题阶段的原生 LaTeX 模板：

- [学位论文开题报告](./01-学位论文开题报告/)
- [实践成果可行性论证报告](./02-实践成果可行性论证报告/)

封面、栏目标题、正文边框、评审表及底纹均由 LaTeX 原生文字和线条绘制，不依赖 PDF 底版或表单截图。

## 快速开始

在所选模板目录下，使用 XeLaTeX + Biber 编译，推荐使用 `latexmk`：

```bash
latexmk -xelatex main.tex
```

填写 `content/info.tex` 中的封面信息，并根据实际课题修改 `content/01.tex` 至 `content/06.tex` 中的正文示例。第七部分为参考文献列表，由 `content/07.tex` 管理。

## 参考文献

`references.bib` 参考 [disc0ver-csu/csu-thesis](https://github.com/disc0ver-csu/csu-thesis) 中南大学学位论文 LaTeX 模板中的文献库。

**模板中的示例引用仅用于演示引用格式与编译效果，正式提交前应替换为与实际研究课题相关的真实文献，并同步更新正文中的引用键。**

## 排版特性

- 每部分从新页开始，正文根据实际长度自动续页，续页重复当前部分的边框和标题。
- 第八、九、十部分为独立整页的连续评审表。
- 当前示例共 15 页，实际填写时各部分不限制页数。
- 较长表格可使用 `longtable` 跨页排版；超过单页高度的图片需适当缩小。

## 底纹设置

`main.tex` 默认启用 `\EnableCSUWatermark`。如需关闭底纹，在该行前添加 `%`；如需恢复，则取消注释。该设置适用于封面、正文及续页、评审页，底纹由 LaTeX 原生文字生成。

## 文件说明

两套模板的主要文件职责如下：

| 文件 | 说明 |
| --- | --- |
| `main.tex` | 编译入口、各部分页面参数及底纹开关 |
| `csu-proposal.sty` | 字体、字号、原生绘图工具、图表与公式编号及引用格式 |
| `content/info.tex` | 姓名、学号等封面信息 |
| `content/cover-layout.tex` | 封面文字、横线与填写值位置 |
| `content/form-layout.tex` | 各部分边框与标题，自动用于续页 |
| `content/review-layout.tex` | 第八、九、十部分评审表的文字和线条 |
| `content/01.tex` 至 `06.tex` | 正文示例，包括编号小节、公式、图表、引用和小结 |
| `content/07.tex` | 参考文献列表，不含小节、小结、图表或公式 |
| `references.bib` | BibTeX 格式的参考文献数据库 |
