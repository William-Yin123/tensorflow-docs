<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.linalg.lu_reconstruct" />
<meta itemprop="path" content="Stable" />
</div>

# tf.linalg.lu_reconstruct

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/linalg/linalg_impl.py">View source</a>



The reconstruct one or more matrices from their LU decomposition(s).

``` python
tf.linalg.lu_reconstruct(
    lower_upper,
    perm,
    validate_args=False,
    name=None
)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`lower_upper`</b>: `lu` as returned by <a href="../../tf/linalg/lu.md"><code>tf.linalg.lu</code></a>, i.e., if `matmul(P,
  matmul(L, U)) = X` then `lower_upper = L + U - eye`.
* <b>`perm`</b>: `p` as returned by `tf.linag.lu`, i.e., if `matmul(P, matmul(L, U)) =
  X` then `perm = argmax(P)`.
* <b>`validate_args`</b>: Python `bool` indicating whether arguments should be checked
  for correctness.
  Default value: `False` (i.e., don't validate arguments).
* <b>`name`</b>: Python `str` name given to ops managed by this object.
  Default value: `None` (i.e., 'lu_reconstruct').


#### Returns:


* <b>`x`</b>: The original input to <a href="../../tf/linalg/lu.md"><code>tf.linalg.lu</code></a>, i.e., `x` as in,
  `lu_reconstruct(*tf.linalg.lu(x))`.

#### Examples

```python
import numpy as np
import tensorflow as tf
import tensorflow_probability as tfp

x = [[[3., 4], [1, 2]],
     [[7., 8], [3, 4]]]
x_reconstructed = tf.linalg.lu_reconstruct(*tf.linalg.lu(x))
tf.assert_near(x, x_reconstructed)
# ==> True
```

## Compat aliases

* `tf.compat.v1.linalg.lu_reconstruct`
* `tf.compat.v2.linalg.lu_reconstruct`

