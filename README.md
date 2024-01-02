# JLUThesis2023

个人自用吉林大学学位论文 LaTeX 模板——jluthesis2023。

可生成学硕、专硕、博士简装、博士精装 PDF 论文，可生成单面或双面印刷版本，可生成单页或双页封面，修改自[JLUThesis2020](https://github.com/maxuewei2/JLUThesis2020)。
针对原模板的字体等问题做了一些修改，但我本人只用于撰写学硕毕业论文，因此可能会对**博士**、**专硕**的修改不生效，欢迎提issue交流。

## 使用

- 选项

	可用选项有 `debug|ebook|hardcopy`，`amd|pmd|phdplain|phdfancy`，`nobox`， `manualSpine`， `onlyCover`， `twoSideCover`,  `noBlankPages`。

	|选项|作用|
  |:---:|---|
  |debug| 生成的PDF带框线，方便调试|
  |ebook| 带彩色文字的PDF|
  |hardcopy| 无彩色文字的PDF|
  |amd| 学术学位硕士使用|
  |pmd |专业学位硕士使用|
  |phdplain| 博士简装版使用|
  |phdfancy |博士精装版使用|
  |nobox | 输出的封面无框线和书脊|
  |manualSpine |手动输出书脊|
  |onlyCover | 仅输出封面页|
  |twoSideCover | 输出双页封面|
  |noBlankPages  | 去掉空白页，主要用于上传到图书馆学位论文系统|
	
	默认为 `hardcopy,amd`，且 `nobox=false, manualSpine=false, onlyCover=false, twoSideCover=false, noBlankPages=false`

	举例如下
	```
	\usepackage[phdplain,ebook,twoSideCover,onlyCover]{jluthesis2020}
	\usepackage[amd,hardcopy,twoSideCover]{jluthesis2020}
	\usepackage[amd,hardcopy]{jluthesis2020}
	```

- 单面印刷需设置 documentclass 为 oneside (如`\documentclass[twoside,a4paper,12pt]{book}`)，双面印刷需设置 documentclass 为 twoside (如`\documentclass[oneside,a4paper,12pt]{book}`)。
- 可选择安装 TeX Live 并使用 XeLaTeX 进行编译，注意设置编译链，如需使用VsCode可以搭配[这篇文章](https://zhuanlan.zhihu.com/p/38178015)食用。<br/>
校内可在[吉大镜像站](http://mirrors.jlu.edu.cn/CTAN/systems/texlive/tlnet/install-tl.zip)下载 TeX Live。
- 与原作者的方案不同，我选择在项目下放置字体文件，并指定所需要的字体路径，以实现不同系统下的迁移，当然也可以一同上传至Overleaf。
- 我选择的字体方案与学校指定的字体一致。以下所需字体收集自[github](https://github.com/Haixing-Hu/latex-chinese-fonts)，并放置在fonts路径：
	- Simsun（中易宋体，即微软宋体）
	- SimHei（中易黑体，即微软黑体）
	- FangSong（微软仿宋）
	- LiSu（隶书）
	- KaiTi（微软楷体）
	- Arial及ArialBold
	- CourierNew及CourierNewBold
	- TimesNewRoman及TimesNewRomanBold

- 若要使用此模板生成的 PDF 文档查重，需确保 PDF 能够正常复制出汉字。

- 要生成 MS Word 文档，可使用 pandoc 或 Adobe Acrobat DC，也可直接用 MS Word 打开 PDF 得到 Word 文档，只是这三种方式得到的 Word 文档质量不同。

- 本人直接将原文进行查重，重复率小于2%，并通过院盲审。同学使用相同模板通过教育部盲审。

- 在打印实体版本时，打印店会重新制作封面，使用打印店给的版本即可。

## 免责声明

此模板为个人实现，未得到学校任何相关人员的认证，使用者应当自行承担一切后果。
