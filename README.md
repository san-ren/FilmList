# FilmList
影视收藏列表
> 本项目的初衷是用AI开发一个收藏影视作品的软件，使用最少的信息确定一个影视作品，就像通过哈希值确定一个文件。



### To Do
- [x] 支持md
  
- [ ] 打造精美的页面布局（HTML转pdf）
  - [x] 编写模板，将获取到的信息填充进模板
    
  - [ ] 生成pdf前的预览，可编辑内容、增减项
  - [ ] 可选择加载不同的 css 美化页面
  - [ ] HTML页面可添加一些动画
- [ ] 可选导出HTML或pdf
- [ ] 整合信息来源，将 `API查询` 和 `加载本地文件` 两种方式，集成在一起
- [ ] 开发实时预览HTML样式的流程，便于自定义HTML结构布局和css样式
- [ ] 选择不同的模板和css样式后，可实时预览


### 引申
- [ ] 若不加载nfo和海报，则变为 md 转 pdf ，再添加页边距、页眉页脚、css美化等自定义功能，由此可扩展出一个高度自定义的pdf生成器
  - [ ] 调查是否已有如此功能定位的软件



### 变更路线
`Tkinter + ReportLab` 🔜🔜🔜 `Tkinter + ReportLab + tkhtmlview` ➡️➡️➡️ `Tkinter + ReportLab + xhtml2pdf + tkhtmlview` 🏃‍♀️‍➡️🏃‍♂️‍➡️🏃‍➡️  `PySide6 + QWebEngineView + WeasyPrint`

**1. Tkinter + ReportLab + tkhtmlview**
- 几乎不能支持md
-  ReportLab (至少是某些版本或者默认配置下) 不支持直接处理和嵌入包含 PostScript 轮廓的 OTF 字体。 它主要支持包含 TrueType 轮廓的字体（无论是 .ttf 文件还是包含 TrueType 轮廓的 .otf 文件）。
  
**2. Tkinter + ReportLab + xhtml2pdf + tkhtmlview**
- 中文显示为黑方块的问题可能与[xhtml2pdf](https://github.com/xhtml2pdf/xhtml2pdf)和ReportLab的字体处理机制有关
  - 从2017年的[一些 Unicode 字符的问题 · 问题 #345 · xhtml2pdf/xhtml2pdf --- Problems with some Unicode characters · Issue #345 · xhtml2pdf/xhtml2pdf](https://github.com/xhtml2pdf/xhtml2pdf/issues/345)
  - 到2025年的[问题 · xhtml2pdf/xhtml2pdf --- Issues · xhtml2pdf/xhtml2pdf](https://github.com/xhtml2pdf/xhtml2pdf/issues?q=is%3Aissue%20font)
  - 一个一直在维护的库是怎么放任一个问题将近十年
  - 貌似是一个解决办法https://github.com/xhtml2pdf/xhtml2pdf/issues/792#issuecomment-2739895489
  
**3. wkhtmltopdf**
- [wkhtmltopdf (QtWebKit)](https://github.com/wkhtmltopdf/wkhtmltopdf)  [![Stars](https://img.shields.io/github/stars/wkhtmltopdf/wkhtmltopdf?style=flat)](https://github.com/wkhtmltopdf/wkhtmltopdf/stargazers)
  ![Archived](https://img.shields.io/badge/Archived-2022--11--22-red?style=flat)
-  归档了，跳过
  
**4. PySide6 + QWebEngineView + WeasyPrint**
- 靠，换了WeasyPrint ，晚上11点多打开输出的pdf看到汉字还有点不习惯诶，毕竟累计二十个小时、自然时间只有2天但感官时间长达一周、历经十几个版本、输出几十次的pdf打开都是黑方块
-  

👉👉👉



















