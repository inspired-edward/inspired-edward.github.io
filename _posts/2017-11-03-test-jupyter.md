---
mathjax: true
---

## Welcome to Colaboratory!

Colaboratory is a data analysis tool that **combines** text, code, and code outputs into a single collaborative document.

|   |   |   |   |   |
|---|---|---|---|---|
|   |  22 | 56  |   |   |
|   a|b   |d   |   |   |
|   |   |   |   |   |
[link](#)

$a+b$



```python
import tensorflow as tf
import numpy as np
import pandas as pd
```


```python
print 'Hello, Colaboratory!'
```

    Hello, Colaboratory!


Colaboratory allows you to execute TensorFlow code in your browser with a single click. The example below adds two matrices.

$\begin{bmatrix}
  1. & 1. & 1. \\
  1. & 1. & 1. \\
\end{bmatrix} +
\begin{bmatrix}
  1. & 2. & 3. \\
  4. & 5. & 6. \\
\end{bmatrix} =
\begin{bmatrix}
  2. & 3. & 4. \\
  5. & 6. & 7. \\
\end{bmatrix}$


```python
import tensorflow as tf
import numpy as np

with tf.Session():
  input1 = tf.constant(1.0, shape=[2, 3])
  input2 = tf.constant(np.reshape(np.arange(1.0, 7.0, dtype=np.float32), (2, 3)))
  output = tf.add(input1, input2)
  result = output.eval()
  print result
```

    [[ 2.  3.  4.]
     [ 5.  6.  7.]]


Colaboratory includes widely used libraries like [matplotlib](https://matplotlib.org/), simplifying visualization.


```python
import matplotlib.pyplot as plt
import numpy as np

x = np.arange(20)
y = map(lambda x: x + np.random.randn(1), x)
a, b = np.polyfit(x, y, 1)
plt.plot(x, y, 'o', np.arange(20), a*np.arange(20)+b, '-');
```


![png](output_6_0.png)


Want to use a new library?  `pip install` it.


```python
# Only needs to be run once at the top of the notebook.
!pip install -q matplotlib-venn

# Now the newly-installed library can be used anywhere else in the notebook.
from matplotlib_venn import venn2
venn2(subsets = (3, 2, 1))
```




    <matplotlib_venn._common.VennDiagram instance at 0x7fbe945fbc20>




![png](output_8_1.png)


## For more information:
- [Overview of Colaboratory](/notebook#fileId=/v2/external/notebooks/basic_features_overview.ipynb)
- [Markdown guide](/notebook#fileId=/v2/external/notebooks/markdown_guide.ipynb)
- [Charts](/notebook#fileId=/v2/external/notebooks/charts.ipynb)
- [Loading and saving data: Drive, Sheets, Google Cloud Storage](/notebook#fileId=/v2/external/notebooks/io.ipynb)
- [Example Google Cloud BigQuery notebook](/notebook#fileId=/v2/external/notebooks/bigquery.ipynb)

