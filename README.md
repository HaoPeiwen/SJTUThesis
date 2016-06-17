# 上海交通大学本科学位论文模板

## Fork From [weijianwen/SJTUThesis](https://github.com/weijianwen/SJTUThesis)

![](https://img.shields.io/badge/OS%20X-supported-green.svg)
![](https://img.shields.io/badge/Linux-unknown-orange.svg)
![](https://img.shields.io/badge/Windows-unknown-orange.svg)

专门为了本科毕业论文实现的模板，大致可用，可能需要进行些许修改。这里是[demo文件](./demo.pdf)，与[weijianwen/SJTUThesis](https://github.com/weijianwen/SJTUThesis)中的0.7.x版本相比有以下改变：

1. 添加了首页
2. 添加了结尾的英文大摘要
3. 去除摘要和目录的页码（TODO）

## 如何使用

SJTUThesis可以在本地编译，也可以在线编译。

### 本地编译 - 系统需求

#### TeX 发行版

SJTUThesis 需要使用 XeTeX 引擎编译。2014和2015年的 [TeXLive](https://www.tug.org/texlive/) 和 [MacTeX](https://www.tug.org/mactex/) 发行版都能编译此模板。Windows 下的 CTeX(2.9.2) 也能顺利编译此模板。**Windows用户**推荐使用 [Babun](http://babun.github.io/) 作为命令行终端。Babun 已默认安装有这些工具：git(版本控制)、GNUmake(编译控制)、perl(字数统计)。

#### 字体

中英文分别依赖 Adobe 的四套简体中文字体和 TeX Gyre Termes 西文字体。Tex Gyre Termes 可从 [CTAN](http://www.ctan.org/tex-archive/fonts/tex-gyre/fonts/opentype/public/tex-gyre) 下载四种不同字型。出于版权考虑，需要大家自行解决 AdobeSongStd, AdobeKaitiStd, AdobeHeitiStd, AdobeFangsongStd 四款中文字体的授权问题。

### 在线编译 - ShareLaTeX

[ShareLaTeX](https://www.sharelatex.com/) 是一个优秀的 LaTeX 在线编译站点，可以完成 SJTUThesis 0.8.1 版本的编译。在[SJTUThesis-0.8](https://www.sharelatex.com/project/56701ac8d63cd1d9646a622f)页面将该项目复制到自己的列表中，就可以开始在模版上工作了。更详细的使用说明，请参考[Usage - 使用文档](https://github.com/weijianwen/SJTUThesis/wiki/Usage)。

### 获取模板

根据「系统需求」中情形选择适合你系统情况的分支，然后根据情况选择 git 克隆最新版代码或者下载稳定版压缩包。

### 编译模板

编译模板，生成学位论文PDF文件。GNUMake将调用`latexmk`程序，自动完成模板的多轮编译。

    make pvc

定稿后可使用以下命令生成最终版本。

    make clean thesis.pdf

若需要生成用于提交盲审的论文(隐去作者、导师等信息)，可在`thesis.tex`中为`sjtuthesis`文档类添加`review`选项。 若需要生成包含“原创性声明扫描件”和“授权书”签名扫描件的学位论文，请将扫描件分别保存为`pdf/origignal.pdf`和`pdf/authorization.pdf`，然后添加`submit`选项重新编译模板。

### 字数统计

    make wordcount

### 问题诊断

编译失败时，可以尝试手动逐次编译。
结合文档 [README.pdf][README] 中的说明，有助于定位故障。

    xelatex -no-pdf thesis
    bibtex thesis
    xelatex thesis
    xelatex thesis

## 反馈问题

建议以如下的顺序反馈使用问题：

* [在 GitHub 项目主页开 issue](https://github.com/weijianwen/SJTUThesis/issues)
* [在水源 BBS TeX_LaTeX 版发帖](https://bbs.sjtu.edu.cn/bbsdoc?board=TeX_LaTeX)

## 软件许可证

上海交通大学校徽图片(`sjtulog.png`)和横幅图片(`sjtubanner.png`)的版权归原作者所有。其他部分使用 [Apache License 2.0](LICENSE) 授权。

[README]: https://s3.amazonaws.com/sjtuthesis/README_0.7.pdf
[0.9.3]: https://github.com/weijianwen/SJTUThesis/releases/tag/0.9.3
[0.8.7]: https://github.com/weijianwen/SJTUThesis/releases/tag/0.8.7
[0.7.7]: https://github.com/weijianwen/SJTUThesis/releases/tag/0.7.7
[0.7.1]: https://github.com/weijianwen/SJTUThesis/releases/tag/0.7.1
