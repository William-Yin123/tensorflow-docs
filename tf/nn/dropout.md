<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.dropout" />
<meta itemprop="path" content="Stable" />
</div>

# tf.nn.dropout

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/nn_ops.py">View source</a>



Computes dropout: randomly sets elements to zero to prevent overfitting.

``` python
tf.nn.dropout(
    x,
    rate,
    noise_shape=None,
    seed=None,
    name=None
)
```



<!-- Placeholder for "Used in" -->

Note: The behavior of dropout has changed between TensorFlow 1.x and 2.x.
When converting 1.x code, please use named arguments to ensure behavior stays
consistent.

See also: <a href="../../tf/keras/layers/Dropout.md"><code>tf.keras.layers.Dropout</code></a> for a dropout layer.

[Dropout](https://arxiv.org/abs/1207.0580) is useful for regularizing DNN
models. Inputs elements are randomly set to zero (and the other elements are
rescaled). This encourages each node to be independently useful, as it cannot
rely on the output of other nodes.

More precisely: With probability `rate` elements of `x` are set to `0`.
The remaining elemenst are scaled up by `1.0 / (1 - rate)`, so that the
expected value is preserved.

```
>>> tf.random.set_seed(0)
>>> x = tf.ones([3,5])
>>> tf.nn.dropout(x, rate = 0.5, seed = 1).numpy()
array([[2., 0., 0., 2., 2.],
     [2., 2., 2., 2., 2.],
     [2., 0., 2., 0., 2.]], dtype=float32)
```

```
>>> tf.random.set_seed(0)
>>> x = tf.ones([3,5])
>>> tf.nn.dropout(x, rate = 0.8, seed = 1).numpy()
array([[0., 0., 0., 5., 5.],
     [0., 5., 0., 5., 0.],
     [5., 0., 5., 0., 5.]], dtype=float32)
```

```
>>> tf.nn.dropout(x, rate = 0.0) == x
<tf.Tensor: shape=(3, 5), dtype=bool, numpy=
  array([[ True,  True,  True,  True,  True],
         [ True,  True,  True,  True,  True],
         [ True,  True,  True,  True,  True]])>
```


By default, each element is kept or dropped independently.  If `noise_shape`
is specified, it must be
[broadcastable](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)
to the shape of `x`, and only dimensions with `noise_shape[i] == shape(x)[i]`
will make independent decisions. This is useful for dropping whole
channels from an image or sequence. For example:

```
>>> tf.random.set_seed(0)
>>> x = tf.ones([3,10])
>>> tf.nn.dropout(x, rate = 2/3, noise_shape=[1,10], seed=1).numpy()
array([[0., 0., 0., 3., 3., 0., 3., 3., 3., 0.],
     [0., 0., 0., 3., 3., 0., 3., 3., 3., 0.],
     [0., 0., 0., 3., 3., 0., 3., 3., 3., 0.]], dtype=float32)
```

#### Args:


* <b>`x`</b>: A floating point tensor.
* <b>`rate`</b>: A scalar `Tensor` with the same type as x. The probability
  that each element is dropped. For example, setting rate=0.1 would drop
  10% of input elements.
* <b>`noise_shape`</b>: A 1-D `Tensor` of type `int32`, representing the
  shape for randomly generated keep/drop flags.
* <b>`seed`</b>: A Python integer. Used to create random seeds. See
  <a href="../../tf/random/set_seed.md"><code>tf.random.set_seed</code></a> for behavior.
* <b>`name`</b>: A name for this operation (optional).


#### Returns:

A Tensor of the same shape of `x`.



#### Raises:


* <b>`ValueError`</b>: If `rate` is not in `[0, 1)` or if `x` is not a floating point
  tensor. `rate=1` is disallowed, because theoutput would be all zeros,
  which is likely not what was intended.

## Compat aliases

* `tf.compat.v2.nn.dropout`

