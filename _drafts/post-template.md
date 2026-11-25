---
title: "Attention, one equation at a time"
date: 2026-12-01
tags: [LLMs, Machine Learning]
description: "One or two sentences shown in post lists and when the link is shared."
---

<!--
  HOW TO USE THIS TEMPLATE
  1. Copy this file to _posts/YYYY-MM-DD-short-title.md  (the date and title in the file name set the URL)
  2. Edit the front matter above. `tags` can be anything; each tag gets its own section on /tags/.
  3. Write. Start sections with "##" (the title above is already the page heading).
  Files in _drafts/ are never published. Preview drafts locally with: bundle exec jekyll serve --drafts
-->

This is a sample post that shows everything the site can render. Delete what you don't need.

## Math

Inline math goes between double dollar signs inside a sentence: the softmax of a vector $$z$$ is $$\sigma(z)_i = e^{z_i} / \sum_j e^{z_j}$$. (Single dollars like $x$ also work for short expressions, but double dollars are safer once there are underscores or backslashes.)

For an equation on its own line, leave a blank line before and after and use double dollars:

$$
\operatorname{Attention}(Q, K, V) = \operatorname{softmax}\!\left(\frac{Q K^\top}{\sqrt{d_k}}\right) V
$$

Number an equation with `\tag{}` and give it a `\label{}` to refer back to it:

$$
\mathcal{L}_{\text{CE}} = -\sum_{i=1}^{N} y_i \log \hat{y}_i \tag{1}\label{eq:ce}
$$

Equation $$\eqref{eq:ce}$$ is the cross-entropy loss. Multi-line derivations use `aligned`:

$$
\begin{aligned}
p(\theta \mid \mathcal{D}) &= \frac{p(\mathcal{D} \mid \theta)\, p(\theta)}{p(\mathcal{D})} \\
&\propto p(\mathcal{D} \mid \theta)\, p(\theta)
\end{aligned}
$$

## Code

```python
import numpy as np

def softmax(z: np.ndarray) -> np.ndarray:
    z = z - z.max()          # numerical stability
    e = np.exp(z)
    return e / e.sum()
```

Inline code looks like `df.groupBy("engine_id")`.

## Tables, quotes and images

| Model | Params | Context |
|-------|-------:|--------:|
| Small | 1B | 8k |
| Large | 70B | 128k |

> A quote or a key takeaway goes here.

Put images in `assets/img/posts/` and reference them like this:

![Description of the image for screen readers](/assets/img/christon.jpg){: width="200" }
*An optional caption in italics right under the image.*

## Footnotes

Claims can have a source.[^1]

[^1]: Vaswani et al., "Attention Is All You Need", NeurIPS 2017.
