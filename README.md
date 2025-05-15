# FilmList
影视收藏列表
> 本项目的初衷是用AI开发一个收藏影视作品的软件，使用最少的信息确定一个影视作品，就像通过哈希值确定一个文件。


### *安装 WeasyPrint 及其依赖*

WeasyPrint 依赖 Pango（文本布局）、Cairo（2D图形）、libffi、GDK-PixBuf（图片格式）等GTK相关的C库。

- **Windows**:
        
    - **安装GTK+运行环境**
        
        - 下载并安装 MSYS2 ([https://www.msys2.org/](https://www.google.com/url?sa=E&q=https%3A%2F%2Fwww.msys2.org%2F))。安装完成后，打开 MSYS2 MinGW 64-bit (或 32-bit，取决于你的Python版本) 终端，然后运行命令安装依赖：
            
                  pacman -S mingw-w64-x86_64-gtk3 mingw-w64-x86_64-pango mingw-w64-x86_64-cairo mingw-w64-x86_64-gdk-pixbuf2 libffi

          (如果是32位Python，将 x86\_64 替换为 i686)。
            
        - 将 MSYS2的 mingw64/bin (或 mingw32/bin) 目录添加到系统的 PATH 环境变量中
            
        - **或者**: 以前有些用户通过下载一个预编译的GTK3运行时包（例如从 [https://github.com/tschoonj/GTK-for-Windows-Runtime-Environment-Installer](https://www.google.com/url?sa=E&q=https%3A%2F%2Fgithub.com%2Ftschoonj%2FGTK-for-Windows-Runtime-Environment-Installer) 或类似的来源），然后将其 bin 目录添加到PATH。请注意查找最新的、可靠的GTK运行时。
            
        
    - 安装完C库依赖并配置好PATH后，再通过pip安装WeasyPrint:
        
          pip install WeasyPrint


### To Do
- [x] 支持md
- [x] 可选导出HTML或pdf
- [x] 加粗的实际显示效果最终取决于所选字体是否包含粗体字重以及PDF引擎的渲染能力
  - [x] 字体文件没有粗体则不能加粗
  - [x] 字体文件可能会将所有内容加粗，而不是只有标题和标签 
- [x] 编写模板，将获取到的信息填充进模板
- [ ] 打造精美的HTML页面
- [ ] 生成pdf前的预览，可编辑内容、增减项
- [ ] 可选择加载不同的 css 美化页面
- [ ] HTML页面可添加一些动画

- [ ] 整合信息来源，将 `API查询` 和 `加载本地文件` 两种方式，集成在一起
- [ ] 开发实时预览HTML样式的流程，便于自定义HTML结构布局和css样式
- [ ] 选择不同的模板和css样式后，可实时预览


### 引申
- [ ] 若不加载nfo和海报，则变为 md 转 pdf ，再添加页边距、页眉页脚、css美化等自定义功能，由此可扩展出一个高度自定义的pdf生成器
  - [ ] 调查是否已有如此功能定位的软件

## 历史变更

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
  
**3. PDFKit (wkhtmltopdf)**
- [wkhtmltopdf (QtWebKit)](https://github.com/wkhtmltopdf/wkhtmltopdf)  [![Stars](https://img.shields.io/github/stars/wkhtmltopdf/wkhtmltopdf?style=flat)](https://github.com/wkhtmltopdf/wkhtmltopdf/stargazers)
  ![Archived](https://img.shields.io/badge/Archived-2022--11--22-red?style=flat)
-  归档了，跳过
  
**4. PySide6 + QWebEngineView + WeasyPrint**
- 靠，换了WeasyPrint ，晚上11点多打开输出的pdf看到汉字还有点不习惯诶，毕竟累计二十个小时、自然时间只有2天但感官时间长达一周、历经十几个版本、输出几十次的pdf打开都是黑方块
-  

👉👉👉



















