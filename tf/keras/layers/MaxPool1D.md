<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.MaxPool1D" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.keras.layers.MaxPool1D

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/pooling.py">View source</a>



## Class `MaxPool1D`

Max pooling operation for 1D temporal data.



**Aliases**: `tf.keras.layers.MaxPooling1D`

<!-- Placeholder for "Used in" -->

Downsamples the input representation by taking the maximum value over the
window defined by `pool_size`. The window is shifted by `strides`.  The
resulting output when using "valid" padding option has a shape of:
`output_shape = (input_shape - pool_size + 1) / strides)`

The resulting output shape when using the "same" padding option is:
`output_shape = input_shape / strides`

For example, for strides=1 and padding="valid":

```
>>> x = tf.constant([1., 2., 3., 4., 5.])
>>> x = tf.reshape(x, [1, 5, 1])
>>> max_pool_1d = tf.keras.layers.MaxPooling1D(pool_size=2,
...    strides=1, padding='valid')
>>> max_pool_1d(x)
<tf.Tensor: shape=(1, 4, 1), dtype=float32, numpy=
array([[[2.],
        [3.],
        [4.],
        [5.]]], dtype=float32)>
```

For example, for strides=2 and padding="valid":

```
>>> x = tf.constant([1., 2., 3., 4., 5.])
>>> x = tf.reshape(x, [1, 5, 1])
>>> max_pool_1d = tf.keras.layers.MaxPooling1D(pool_size=2,
...    strides=2, padding='valid')
>>> max_pool_1d(x)
<tf.Tensor: shape=(1, 2, 1), dtype=float32, numpy=
array([[[2.],
        [4.]]], dtype=float32)>
```

For example, for strides=1 and padding="same":

```
>>> x = tf.constant([1., 2., 3., 4., 5.])
>>> x = tf.reshape(x, [1, 5, 1])
>>> max_pool_1d = tf.keras.layers.MaxPooling1D(pool_size=2,
...    strides=1, padding='same')
>>> max_pool_1d(x)
<tf.Tensor: shape=(1, 5, 1), dtype=float32, numpy=
array([[[2.],
        [3.],
        [4.],
        [5.],
        [5.]]], dtype=float32)>
```

#### Arguments:


* <b>`pool_size`</b>: Integer, size of the max pooling window.
* <b>`strides`</b>: Integer, or None. Specifies how much the pooling window moves
  for each pooling step.
  If None, it will default to `pool_size`.
* <b>`padding`</b>: One of `"valid"` or `"same"` (case-insensitive).
  "valid" adds no padding.  "same" adds padding such that if the stride
  is 1, the output shape is the same as the input shape.
* <b>`data_format`</b>: A string,
  one of `channels_last` (default) or `channels_first`.
  The ordering of the dimensions in the inputs.
  `channels_last` corresponds to inputs with shape
  `(batch, steps, features)` while `channels_first`
  corresponds to inputs with shape
  `(batch, features, steps)`.


#### Input shape:

- If `data_format='channels_last'`:
  3D tensor with shape `(batch_size, steps, features)`.
- If `data_format='channels_first'`:
  3D tensor with shape `(batch_size, features, steps)`.



#### Output shape:

- If `data_format='channels_last'`:
  3D tensor with shape `(batch_size, downsampled_steps, features)`.
- If `data_format='channels_first'`:
  3D tensor with shape `(batch_size, features, downsampled_steps)`.


<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/pooling.py">View source</a>

``` python
__init__(
    pool_size=2,
    strides=None,
    padding='valid',
    data_format='channels_last',
    **kwargs
)
```








## Compat aliases

* `tf.compat.v1.keras.layers.MaxPool1D`
* `tf.compat.v1.keras.layers.MaxPooling1D`
* `tf.compat.v2.keras.layers.MaxPool1D`
* `tf.compat.v2.keras.layers.MaxPooling1D`

