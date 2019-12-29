<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.constant" />
<meta itemprop="path" content="Stable" />
</div>

# tf.constant

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/framework/constant_op.py">View source</a>



Creates a constant tensor from a tensor-like object.

``` python
tf.constant(
    value,
    dtype=None,
    shape=None,
    name='Const'
)
```



<!-- Placeholder for "Used in" -->

Note: All eager <a href="../tf/Tensor.md"><code>tf.Tensor</code></a> values are immutable (in contrast to
<a href="../tf/Variable.md"><code>tf.Variable</code></a>). There is nothing especially _constant_ about the value
returned from <a href="../tf/constant.md"><code>tf.constant</code></a>. This function it is not fundamentally different
from <a href="../tf/convert_to_tensor.md"><code>tf.convert_to_tensor</code></a>. The name <a href="../tf/constant.md"><code>tf.constant</code></a> comes from the symbolic
APIs (like <a href="../tf/data.md"><code>tf.data</code></a> or keras functional models) where the `value` is embeded
in a `Const` node in the <a href="../tf/Graph.md"><code>tf.Graph</code></a>. <a href="../tf/constant.md"><code>tf.constant</code></a> is useful for asserting
that the value can be embedded that way.

If the argument `dtype` is not specified, then the type is inferred from
the type of `value`.

```
>>> # Constant 1-D Tensor from a python list.
>>> tf.constant([1, 2, 3, 4, 5, 6])
<tf.Tensor: shape=(6,), dtype=int32,
    numpy=array([1, 2, 3, 4, 5, 6], dtype=int32)>
>>> # Or a numpy array
>>> a = np.array([[1, 2, 3], [4, 5, 6]])
>>> tf.constant(a)
<tf.Tensor: shape=(2, 3), dtype=int64, numpy=
  array([[1, 2, 3],
         [4, 5, 6]])>
```

If `dtype` is specified the resulting tensor values are cast to the requested
`dtype`.

```
>>> tf.constant([1, 2, 3, 4, 5, 6], dtype=tf.float64)
<tf.Tensor: shape=(6,), dtype=float64,
    numpy=array([1., 2., 3., 4., 5., 6.])>
```

If `shape` is set, the `value` is reshaped to match. Scalars are expanded to
fill the `shape`:

```
>>> tf.constant(0, shape=(2, 3))
  <tf.Tensor: shape=(2, 3), dtype=int32, numpy=
  array([[0, 0, 0],
         [0, 0, 0]], dtype=int32)>
>>> tf.constant([1, 2, 3, 4, 5, 6], shape=[2, 3])
<tf.Tensor: shape=(2, 3), dtype=int32, numpy=
  array([[1, 2, 3],
         [4, 5, 6]], dtype=int32)>
```

<a href="../tf/constant.md"><code>tf.constant</code></a> has no effect if an eager Tensor is passed as the `value`, it
even transmits gradients:

```
>>> v = tf.Variable([0.0])
>>> with tf.GradientTape() as g:
...     loss = tf.constant(v + v)
>>> g.gradient(loss, v).numpy()
array([2.], dtype=float32)
```

But, since <a href="../tf/constant.md"><code>tf.constant</code></a> embeds the value in the <a href="../tf/Graph.md"><code>tf.Graph</code></a> this fails for
symbolic tensors:

```
>>> i = tf.keras.layers.Input(shape=[None, None])
>>> t = tf.constant(i)
Traceback (most recent call last):
...
ValueError: ...
```

#### Related Ops:



* <a href="../tf/convert_to_tensor.md"><code>tf.convert_to_tensor</code></a> is similar but:
  * It has no `shape` argument.
  * Symbolic tensors are allowed to pass through.

    ```
    >>> i = tf.keras.layers.Input(shape=[None, None])
    >>> t = tf.convert_to_tensor(i)
    ```

* <a href="../tf/fill.md"><code>tf.fill</code></a>: differs in a few ways:
  *   <a href="../tf/constant.md"><code>tf.constant</code></a> supports arbitrary constants, not just uniform scalar
      Tensors like <a href="../tf/fill.md"><code>tf.fill</code></a>.
  *   <a href="../tf/fill.md"><code>tf.fill</code></a> creates an Op in the graph that is expanded at runtime, so it
      can efficiently represent large tensors.
  *   Since <a href="../tf/fill.md"><code>tf.fill</code></a> does not embed the value, it can produce dynamically
      sized outputs.

#### Args:


* <b>`value`</b>: A constant value (or list) of output type `dtype`.
* <b>`dtype`</b>: The type of the elements of the resulting tensor.
* <b>`shape`</b>: Optional dimensions of resulting tensor.
* <b>`name`</b>: Optional name for the tensor.


#### Returns:

A Constant Tensor.



#### Raises:


* <b>`TypeError`</b>: if shape is incorrectly specified or unsupported.
* <b>`ValueError`</b>: if called on a symbolic tensor.

## Compat aliases

* `tf.compat.v2.constant`

