# JLUThesis2020

吉林大学学位论文 LaTeX 模板——jluthesis2023。

可生成学硕、专硕、博士简装、博士精装 PDF 论文，可生成单面或双面印刷版本，可生成单页或双页封面，修改自[JLUThesis2020](https://github.com/maxuewei2/JLUThesis2020)。
针对原模板的字体等问题做了一些修改。

目前只是占坑，等待论文撰写完成以及盲审过后更新模板。

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
- 建议安装 TeX Live 并使用 XeLaTeX 编译。<br/>
  校内可在[吉大镜像站](http://mirrors.jlu.edu.cn/CTAN/systems/texlive/tlnet/install-tl.zip)下载 TeX Live。
- 若缺少字体需自行安装 (见[fonts.txt](fonts.txt))。所需字体如下：
	- Adobe Song Std，Adobe Heiti Std，Adobe Kaiti Std，Adobe Fangsong Std
	- Nimbus Roman，Nimbus Sans，Nimbus Mono
	- Source Han Sans(思源黑体)，Source Han Serif(思源宋体)
	- LiSu (隶书)

	安装字体后，可运行 `fc-cache` 刷新字体缓存，可通过 ` fc-list : family | sort ` 查看已安装字体。<br/>
    这两个命令均随 TeX Live 安装，Windows 下在如 `C:\texlive\2020\bin\win32` 的文件夹下可找到，可将该文件夹添加进 PATH 环境变量。<br/> 
    若编译时提示找不到字体，先检查字体是否已安装，再检查字体名称是否一致。
- 若要使用此模板生成的 PDF 文档查重，需确保 PDF 能够正常复制出汉字。

- 要生成 MS Word 文档，可使用 pandoc 或 Adobe Acrobat DC，也可直接用 MS Word 打开 PDF 得到 Word 文档，只是这三种方式得到的 Word 文档质量不同。

- 查重时可能会把原创声明、授权声明、参考文献、致谢等包括进去，可使用 `makeCrosscheckVersion.sh` 制作查重版本，生成的 PDF 文档中原创声明、授权声明、作者简介、致谢四部分的文字被转换为路径，因此这四部分无法导出无法复制，也就不会参与查重。之所以没将参考文献也做成不可复制的，是觉得查重系统会从这里面提取引用。<br/>
	- 使用方法：
	```bash
	chmod a+x makeCrosscheckVersion.sh
	./makeCrosscheckVersion.sh example  # example为PDF文件名，不包括扩展名
	```
	- 执行此脚本需
	    - 安装 [pdftk](https://www.pdflabs.com/tools/pdftk-the-pdf-toolkit/)、[Ghostscript](https://www.ghostscript.com/download/gsdnld.html) 并将其路径加入 PATH 环境变量。
	    - 将 TeX Live 可执行文件路径加入 PATH 环境变量。
	    - 有类 Linux 环境，可执行 cat、grep、awk、head 等命令。Windows下安装 [Git](https://git-scm.com/downloads) 并使用 Git Bash 可得到。

- 思源宋体粗体可能看起来与 MS Word 中的粗体差别较大。若以假粗体实现粗体来生成的文档大概更接近 MS Word 的感觉，但似乎偶尔会出现奇奇怪怪的问题 (如部分字无法选中、该加粗的字没有加粗、不该加粗的字被加粗了等)，不过好在只有封面、摘要、章节题目等少数几个地方需要使用粗体。使用假粗体需在 documentclass 中设置 AutoFakeBold， 在 jluthesis2020 中设置 manualSpine，并需重置 CJKmainfont，具体见 [amd-ebook-oneside-假粗体.tex](example_files/amd-ebook-oneside-假粗体.tex)。本人所提交的论文采用假粗体方案。

## 免责声明

此模板为个人实现，未得到学校任何相关人员的认证，使用者应当自行承担一切后果。



