# FilmList
影视收藏列表
> 本项目的初衷是用AI开发一个收藏影视作品的软件，使用最少的信息确定一个影视作品，就像通过哈希值确定一个文件。



### To Do
- [ ] 支持md
  
- [ ] 打造精美的页面布局（HTML转pdf）
  - [ ] 编写模板，将从nfo或api获取到的信息填充进模板
    
  - [ ] 生成pdf前的预览，可编辑内容、增减项
  - [ ] 使用css美化页面
  - [ ] HTML页面可添加一些动画
- [ ] 可选导出HTML或pdf



### 难点

- 中文显示为黑方块的问题可能与xhtml2pdf和ReportLab的字体处理机制有关
  - 从2017年的[一些 Unicode 字符的问题 · 问题 #345 · xhtml2pdf/xhtml2pdf --- Problems with some Unicode characters · Issue #345 · xhtml2pdf/xhtml2pdf](https://github.com/xhtml2pdf/xhtml2pdf/issues/345)
  - 到2025年的[问题 · xhtml2pdf/xhtml2pdf --- Issues · xhtml2pdf/xhtml2pdf](https://github.com/xhtml2pdf/xhtml2pdf/issues?q=is%3Aissue%20font)
  - 一个一直在维护的库是怎么放任一个问题将近十年
  - 貌似是一个解决办法https://github.com/xhtml2pdf/xhtml2pdf/issues/792#issuecomment-2739895489
 
- [wkhtmltopdf (QtWebKit)](https://github.com/wkhtmltopdf/wkhtmltopdf)  [![Stars](https://img.shields.io/github/stars/wkhtmltopdf/wkhtmltopdf?style=flat)](https://github.com/wkhtmltopdf/wkhtmltopdf/stargazers)
  ![Archived](https://img.shields.io/badge/Archived-2022--11--22-red?style=flat)

### 更新记录

- 重构：从 Tkinter + tkhtmlview 转移到 PySide6 + QWebEngineView



















