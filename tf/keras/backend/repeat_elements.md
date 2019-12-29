<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.repeat_elements" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.repeat_elements

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Repeats the elements of a tensor along an axis, like `np.repeat`.

``` python
tf.keras.backend.repeat_elements(
    x,
    rep,
    axis
)
```



<!-- Placeholder for "Used in" -->

If `x` has shape `(s1, s2, s3)` and `axis` is `1`, the output
will have shape `(s1, s2 * rep, s3)`.

#### Arguments:


* <b>`x`</b>: Tensor or variable.
* <b>`rep`</b>: Python integer, number of times to repeat.
* <b>`axis`</b>: Axis along which to repeat.


#### Returns:

A tensor.



#### Example:


```
>>> b = tf.constant([1, 2, 3])
>>> tf.keras.backend.repeat_elements(b, rep=2, axis=0)
<tf.Tensor: shape=(6,), dtype=int32,
    numpy=array([1, 1, 2, 2, 3, 3], dtype=int32)>
```


## Compat aliases

* `tf.compat.v1.keras.backend.repeat_elements`
* `tf.compat.v2.keras.backend.repeat_elements`

