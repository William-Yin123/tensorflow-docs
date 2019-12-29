<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.real" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.real

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/math_ops.py">View source</a>



Returns the real part of a complex (or real) tensor.

``` python
tf.math.real(
    input,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Given a tensor `input`, this operation returns a tensor of type `float` that
is the real part of each element in `input` considered as a complex number.

#### For example:



```python
x = tf.constant([-2.25 + 4.75j, 3.25 + 5.75j])
tf.math.real(x)  # [-2.25, 3.25]
```

If `input` is already real, it is returned unchanged.

#### Args:


* <b>`input`</b>: A `Tensor`. Must have numeric type.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `float32` or `float64`.


## Compat aliases

* `tf.compat.v1.math.real`
* `tf.compat.v1.real`
* `tf.compat.v2.math.real`

