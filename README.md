# 中南大学开题报告原生 LaTeX 模板

本目录两套模板均为纯 LaTeX：封面、栏目标题、正文边框、评审表及底纹由原生文字和线条绘制，不使用 PDF 底版或表单截图。原 Word 及终期目录均未修改。

## 编译与填写

使用 XeLaTeX + Biber，推荐 `latexmk -xelatex main.tex`。封面信息在 content/info.tex；第1—6部分示例在 content/01.tex 至 06.tex；第7部分仅为 content/07.tex 中的参考文献列表。references.bib 复用终期/csu-thesis，示例引用应在正式提交前替换为课题真实文献。

每部分从新页开始，正文按实际长度自动续页，续页重复当前部分的原生边框和标题；下一部分另起新页。八、九、十为连续评审表，独立整页。当前示例共15页，实际填写不限制各部分页数。较长表格可用 longtable，超过单页高度的图片仍需缩小。

## 底纹

main.tex 默认保留 `\EnableCSUWatermark`。不需要底纹时在该行前加 `%`；需要时取消注释。该开关适用于封面、所有正文续页及评审页。底纹也是 LaTeX 文字。

## 文件职责

- main.tex：编译入口、每部分页面参数、底纹开关。
- csu-proposal.sty：字体、字号、原生绘图工具、图表与公式编号、引用格式。
- content/info.tex：姓名、学号等填写值。
- content/cover-layout.tex：原生封面文字、横线与填写值位置。
- content/form-layout.tex：各部分原生边框与标题，自动用于续页。
- content/review-layout.tex：八、九、十连续表格的文字和线条。
- content/01.tex 至 06.tex：编号小节、公式、图表、引用和小结的可替换示例。
- content/07.tex：仅参考文献列表，无小节、小结、图表或公式。
