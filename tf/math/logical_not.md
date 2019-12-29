<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.logical_not" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.logical_not

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Returns the truth value of `NOT x` element-wise.

**Aliases**: `tf.logical_not`

``` python
tf.math.logical_not(
    x,
    name=None
)
```



<!-- Placeholder for "Used in" -->


#### Example:



```
>>> tf.math.logical_not(tf.constant([True, False]))
<tf.Tensor: shape=(2,), dtype=bool, numpy=array([False,  True])>
```

#### Args:


* <b>`x`</b>: A `Tensor` of type `bool`. A `Tensor` of type `bool`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `bool`.


## Compat aliases

* `tf.compat.v1.logical_not`
* `tf.compat.v1.math.logical_not`
* `tf.compat.v2.logical_not`
* `tf.compat.v2.math.logical_not`

