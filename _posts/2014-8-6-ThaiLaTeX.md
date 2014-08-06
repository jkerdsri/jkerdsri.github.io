---
published: false
---

## Using Thai with LaTeX on Mac OS X

Here the thing, while I was writhing my thesis using LaTeX with the template that Dr. Gordon created, I have to write a long research report for my work.
So I have a though of using LaTeX to create that report since I already fond of the way LaTeX writing can help me organize and create beautiful PDF report.

However, it’s not easy as I thought since I have to write that report in Thai and Thai language is designed to be difficult to use in the digital world. I have to dig around for a couple days in order to use Thai with LaTeX especially on OS X.
Here is how I did it:

1. First we’ll need to install TeX Live, for Mac we need to install MacTex
2. Once you install the MacTex then you’re ready to use international language with LaTeX using XeTeX typesetting engine.
3. Then you’ll need a tool with XeTeX engine to write LaTeX. I recommend Texmaker because it’s free and super powerful.
4. After installing you will have to set up the typesetting by go to Texmaker > Preferences > Quick Build > XeLaTex + View PDF
5. Finally test your environment by creating new document with this code
```
\documentclass[a4paper]{book}
\usepackage{xltxtra}
\usepackage{polyglossia}
\usepackage[top=25mm, bottom=20mm, left=25mm, right=25mm]{geometry}
\usepackage[titletoc,toc,title]{appendix}

\XeTeXlinebreaklocale "th"
\XeTeXlinebreakskip = 0pt plus 1pt
\setmainfont{TH SarabunPSK}

\defaultfontfeatures{Scale=1.23}
\renewcommand{\baselinestretch}{1.2}

\setdefaultlanguage{thai}
\newfontfamily{\thaifont}[Script=thai]{TH SarabunPSK}

\begin{document}

\frontmatter
\pagenumbering{thaialph}
\tableofcontents

\mainmatter
\chapter{บทแรก}
\section{บทนำ}

\noindent
ป้า กะ ปู่ กู้อีจู้ ตัวปกติ\\
{\itshape ป้า กะ ปู่ กู้อีจู้ ตัวเอียง} \\
{\bfseries ป้า กะ ปู่ กู้อีจู้ ตัวหนา } \\
{\bfseries\itshape ป้า กะ ปู่ กู้อีจู้ ตัวหนาเอียง} \\

ทดสอบใช้คำสั่ง \LaTeXe{}\\
ป้า กะ ปู่ กู้อีจู้ ไฟฟ้า ปัญญา ตัวปกติ\\
\textbf{ป้า กะ ปู่ กู้อีจู้ ไฟฟ้า ปัญญา ตัวหนา}\\
\textit{ป้า กะ ปู่ กู้อีจู้ ไฟฟ้า ปัญญา ตัวเอียง}\\
\textsl{ป้า กะ ปู่ กู้อีจู้ ไฟฟ้า ปัญญา ตัวเอน}\\
\textbf{\textit{ป้า กะ ปู่ กู้อีจู้ ตัวหนาเอียง}}\\
%%\texttt{ป้า กะ ปู่ กู้อีจู้ ไฟฟ้า ปัญญา ตัวพิมพ์}

\chapter{บทสอง}
\section{บทนำ}
xxxx xxxxx xxxxx
\chapter{บทสาม}
\section{บทนำ}
xxxx xxxxx xxxxx

%% \backmatter %% ใช้ไม่ได้ หายหมด

%% ยังไม่ดีมาก แต่ก็ได้ ก ข ค
\begin{appendices}
\renewcommand*{\thechapter}{\thaiAlph{chapter}}
\chapter{ทดสอบภาคผนวก} %% ---------------------
\chapter{ทดสอบภาคผนวกอีกที} %% ---------------------
\end{appendices}
\end{document}
```
You should see Thai language is working correctly, if not check if you system has Thai Sarabun font installed? You can download this official Thai font from SIPA

The main point is you’ll need to tell LaTeX to use Thai font
```
\usepackage{font spec} % To enable non-standard font selections
\setmainfont{TH SarabunPSK} % A font with Thai glyphs
\XeTeXlinebreaklocale ’th_TH’ % Thai-style word-breakings and line-wrappings
```
Enjoy Thai LaTeXing ^_^