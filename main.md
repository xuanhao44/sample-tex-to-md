# Pandoc LaTeX Stress Test

## Text, Links, Footnotes, Quotes

这是一段普通文本，包含强调 _emph_、加粗 **bold**、等宽 `code`，以及超链接：[Pandoc 官方站点](https://pandoc.org)。

脚注示例[^1]，以及引号：“quoted text”。

| 这是一个自定义环境 `mybox`，里面也包含 <span style="color: blue">**自定义宏渲染**</span>。 |
| :----------------------------------------------------------------------------------------- |

### Lists

无序列表：

- 第一项

- 第二项，带数学 $a^2 + b^2 = c^2$

- 第三项，带自定义宏：$\left\lVert \mathbf{x} \right\rVert$，$\left\langle x, y \right\rangle$

有序列表（自定义格式）：

1. 选项 A

2. 选项 B

描述列表：

Key
Value

Longer Key
A longer value text.

## Math

行内数学：$\mathbb{E}[X]$，$\mathbb{R}^n$，以及可选参数宏：$\big( t \big)$、$\Big( t \Big)$。

行间公式：

$$
\int_0^1 x^2 \,dx = \frac 13.
$$

多行对齐：

$$
\begin{aligned}
f(x) & = x^2 + 1         \\
& = (x+1)(x-1) + 2.\end{aligned}
$$

带编号的定理环境：

**Theorem 1** (Pythagoras). _For a right triangle, $a^2 + b^2 = c^2$._

**Lemma 1**. _If $x \in \mathbb{R}$, then $x^2 \ge 0$._

## Tables

### Booktabs table

### Longtable

| Key | Value |
| :-- | :---- |
| Key | Value |
| A   | 1     |
| B   | 2     |
| C   | 3     |
| D   | 4     |

A longtable example.

## Figures

图像（需要你放一个文件，如 `figures/demo.pdf`）：

![demo](figures/demo.svg "demo")

## Code Blocks

### verbatim

```
#!/usr/bin/env bash
echo "Hello, verbatim!"
```

### listings

```python
def f(x):
    return x*x + 1
print(f(3))
```

## TikZ (raw TeX heavy)

## Citations (BibLaTeX style placeholder)

这里是引用占位：。（如果你只用 Pandoc 读 LaTeX 转 Markdown，这一段通常会暴露“引用如何处理”的差异。）

[^1]: 这是一个脚注。
