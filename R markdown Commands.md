以下是 **RMarkdown** 常用的命令和语法总结，涵盖文档编写、代码块控制、输出格式设置等核心功能：

---

### **1. 基础文档结构**
```markdown
---
title: "标题"
author: "作者"
date: "日期"
output: 
  html_document: 
    toc: true          # 目录
    theme: cosmo       # 主题
    number_sections: true  # 章节编号
---
```

#### **常用输出格式**：
- `html_document` (HTML网页)
- `pdf_document` (PDF，需LaTeX环境)
- `word_document` (Word)
- `github_document` (GitHub兼容Markdown)

---

### **2. 代码块控制**
#### **插入代码块**
````markdown
```{r}
# R代码
summary(mtcars)
```
````

#### **代码块选项**：
```markdown
```{r chunk_name, echo=FALSE, eval=TRUE, warning=FALSE}
# echo: 是否显示代码
# eval: 是否运行代码
# warning/message: 隐藏警告/消息
# fig.width, fig.height: 图形尺寸
```
```

#### **内联代码**
```markdown
`r mean(mtcars$mpg)` 会在输出中动态计算结果。
```

---

### **3. 文本格式化**
- **标题**：
  ```markdown
  # 一级标题
  ## 二级标题
  ```
- **列表**：
  ```markdown
  - 无序列表
  1. 有序列表
  ```
- **链接与图片**：
  ```markdown
  [链接文字](URL)
  ![图片描述](图片路径)
  ```
- **表格**：
  ```markdown
  | 列1 | 列2 |
  |-----|-----|
  | A   | B   |
  ```

---

### **4. 表格与图形**
#### **生成表格**
```markdown
```{r}
knitr::kable(mtcars[1:5, ], caption = "示例表格")
```
```

#### **插入图形**
```markdown
```{r plot_example}
plot(pressure)
```
```

---

### **5. 条件输出与动态内容**
- **条件显示文本**：
  ```markdown
  `r if (nrow(mtcars) > 10) "数据行数大于10" else "数据行数不足"`
  ```
- **循环生成内容**：
  ```markdown
  ```{r results='asis'}
  for (i in 1:3) {
    cat("## 章节", i, "\n\n")
  }
  ```
  ```

---

### **6. 引用与参考文献**
#### **文献引用**
1. 创建 `references.bib` 文件：
   ```bibtex
   @book{key, title="书名", author="作者", year=2023}
   ```
2. 在文档中引用：
   ```markdown
   Blah blah [@key; @key2].
   ```

#### **输出参考文献**
在 YAML 头部添加：
```yaml
bibliography: references.bib
```

---

### **7. 缓存与性能优化**
```markdown
```{r cache=TRUE}
# 结果缓存，避免重复计算
long_running_code()
```

---

### **8. 常用快捷键（RStudio）**
- **渲染文档**：`Ctrl + Shift + K` (Windows) / `Cmd + Shift + K` (Mac)
- **插入代码块**：`Ctrl + Alt + I` / `Cmd + Option + I`
- **运行当前代码块**：`Ctrl + Shift + Enter`

---

### **9. 调试与错误处理**
- **错误信息定位**：设置 `error=TRUE` 在代码块中允许继续渲染：
  ```markdown
  ```{r error=TRUE}
  problematic_code()
  ```
  ```

---

### **10. 扩展功能包推荐**
- **`bookdown`**：编写书籍/长文档
- **`flexdashboard`**：创建交互式仪表盘
- **`xaringan`**：制作幻灯片
- **`tinytex`**：轻量级LaTeX环境（PDF输出必备）

---

通过组合这些命令，可以高效完成从数据分析到报告生成的完整流程。建议保存为 [Cheatsheet](https://www.rstudio.com/resources/cheatsheets/) 随时查阅！
