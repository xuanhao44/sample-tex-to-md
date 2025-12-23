# Pandoc LaTeX Stress Test

## Text, Links, Footnotes, Quotes

这是一段普通文本，包含强调 _emph_、加粗 **bold**、等宽 `code`，以及超链接：[Pandoc 官方站点](https://pandoc.org)。

脚注示例[^1]，以及引号：“quoted text”。

| 这是一个自定义环境 `mybox`，里面也包含 <span style="color: blue">**自定义宏渲染**</span>。 |
| :----------------------------------------------------------------------------------------- |

### Percentages

测试百分数：Test percent $100\%$ 和 100%。

百分号在 $\LaTeX$ 中是注释符号，因此需要使用反斜杠进行转义以正确显示百分号符号；但并不需要美元符号包裹。

假设包裹，那么经过 CI 转换后仍然是：

```
$100\%$
```

但在不同的环境下会有不同的表现：

- VS Code 编辑器的 Markdown 预览中渲染正常。

- GitHub 上的 Markdown 渲染则不完整，显示为“100”后缺少百分号。

所以如果公式仅涉及百分号，建议直接写作“100%”而非“$100\%$”。

测试“$100\%$”，$100\%$ 和 100%。

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

### Table with \| in Math

展示包含竖线的数学公式（绝对值）：

注意：在纯 LaTeX 环境下，公式里直接用 \| 是没问题的。但是如果使用了 \| 作为绝对值符号，那么必然会在转换成 Markdown 表格的时候遇到问题，因为 Markdown 表格使用 \| 作为列分隔符。

所以建议在数学公式中使用 和 来表示绝对值符号，例如 $\lvert x \rvert$。下面是一个示例表格：

<div id="tab:experiment_results">

| **Model Name** | **Accuracy (%)** | **Loss Function**  | **Time (ms)** |
| :------------- | :--------------: | :----------------: | ------------: | ---- | -------- |
| Baseline Model |      85.2%       | $\mathcal{L}_{CE}$ |          45.5 |
| Method A       |      88.4%       |         \$         |  y - \\hat{y} |
| **Ours (Pro)** |    **92.1%**     |         $          | \Delta \theta | \_2$ | **38.2** |

Comparison of performance metrics across different models.

## Figures

图像（需要你放一个文件，如 `figures/demo.pdf`），CI 会尝试将其转换为 SVG。

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

TODO: 将来会考虑生成 Tikz PDF 图，然后转换为 SVG 嵌入。

## Citations (BibLaTeX style placeholder)

这里是引用占位：。（如果你只用 Pandoc 读 LaTeX 转 Markdown，这一段通常会暴露“引用如何处理”的差异。）

[^1]: 这是一个脚注。
