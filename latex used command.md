以下是 **LaTeX** 的核心语法总结，涵盖文档结构、数学公式、表格、列表、图表插入等常用功能：

---

### **1. 文档基本结构**
```latex
\documentclass{article} % 文档类（article/report/book/beamer等）
\usepackage[UTF8]{ctex} % 中文支持（XeLaTeX编译）
\usepackage{amsmath}    % 数学公式扩展包

\begin{document}

\title{标题}
\author{作者}
\date{\today}
\maketitle              % 生成标题

\section{一级标题}
正文内容...

\end{document}
```

---

### **2. 数学公式**
#### **行内公式**
```latex
勾股定理：$a^2 + b^2 = c^2$
```

#### **行间公式**
```latex
\[
E = mc^2
\]

\begin{equation}  % 带编号公式
F = ma \label{eq:newton}
\end{equation}
```

#### **常用数学符号**
| 符号         | 语法          | 符号       | 语法           |
|--------------|---------------|------------|----------------|
| α            | `\alpha`      | ∑          | `\sum`         |
| ∫            | `\int`        | ∂          | `\partial`     |
| →            | `\to`         | ±          | `\pm`          |
| ×            | `\times`      | ≤          | `\leq`         |

---

### **3. 列表**
#### **无序列表**
```latex
\begin{itemize}
  \item 项目1
  \item 项目2
\end{itemize}
```

#### **有序列表**
```latex
\begin{enumerate}
  \item 第一项
  \item 第二项
\end{enumerate}
```

---

### **4. 表格**
```latex
\begin{tabular}{|c|l|r|}  % c:居中 l:左对齐 r:右对齐 |表示竖线
\hline
列1 & 列2 & 列3 \\ \hline
A   & B   & 1   \\
C   & D   & 2   \\ \hline
\end{tabular}
```

**推荐使用 `booktabs` 包优化表格样式**：
```latex
\usepackage{booktabs}
\begin{tabular}{ccc}
\toprule
Header1 & Header2 \\
\midrule
Row1    & Data1   \\
Row2    & Data2   \\
\bottomrule
\end{tabular}
```

---

### **5. 图片插入**
```latex
\usepackage{graphicx}
\begin{figure}[htbp]
  \centering
  \includegraphics[width=0.8\textwidth]{image.png}
  \caption{图片标题}
  \label{fig:example}
\end{figure}
```

**位置参数**：
- `h` (here)  
- `t` (top)  
- `b` (bottom)  
- `p` (单独一页)

---

### **6. 交叉引用**
```latex
参见公式\eqref{eq:newton}或图\ref{fig:example}。
```

**需编译两次**生成正确的引用编号。

---

### **7. 参考文献**
#### **BibTeX 引用**
1. 创建 `refs.bib` 文件：
   ```bibtex
   @book{key, 
     title={书名}, 
     author={作者}, 
     year=2023
   }
   ```
2. 在文档中引用：
   ```latex
   \cite{key}
   ```
3. 插入参考文献列表：
   ```latex
   \bibliographystyle{plain}
   \bibliography{refs}
   ```

---

### **8. 分栏与分页**
```latex
\newpage          % 强制分页
\begin{multicols}{2}  % 分两栏（需multicol包）
内容...
\end{multicols}
```

---

### **9. 代码展示**
**使用 `listings` 包**：
```latex
\usepackage{listings}
\begin{lstlisting}[language=Python]
def hello():
    print("Hello LaTeX!")
\end{lstlisting}
```

---

### **10. 常用宏包推荐**
| 宏包            | 用途                  |
|-----------------|-----------------------|
| `hyperref`      | 超链接/PDF书签        |
| `geometry`      | 调整页边距            |
| `fancyhdr`      | 页眉页脚设计          |
| `tikz`          | 矢量绘图              |
| `siunitx`       | 科学单位格式化        |

---

### **编译工具链**
1. **XeLaTeX**（推荐中文用户）：支持UTF-8和系统字体
2. **PDFLaTeX**：基础编译引擎
3. **BibTeX**：处理参考文献

**命令行示例**：
```bash
xelatex document.tex       # 第一次编译
bibtex document.aux        # 生成参考文献
xelatex document.tex       # 第二次编译
xelatex document.tex       # 第三次编译（确保引用正确）
```

---

掌握这些核心语法后，可应对90%的LaTeX文档编写需求。建议从[Overleaf](https://www.overleaf.com/)在线编辑器开始实践！
