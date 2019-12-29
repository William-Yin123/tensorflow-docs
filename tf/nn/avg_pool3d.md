<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.avg_pool3d" />
<meta itemprop="path" content="Stable" />
</div>

# tf.nn.avg_pool3d

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/nn_ops.py">View source</a>



Performs the average pooling on the input.

``` python
tf.nn.avg_pool3d(
    input,
    ksize,
    strides,
    padding,
    data_format='NDHWC',
    name=None
)
```



<!-- Placeholder for "Used in" -->

Each entry in `output` is the mean of the corresponding size `ksize`
window in `value`.

#### Args:


* <b>`input`</b>: A 5-D `Tensor` of shape `[batch, height, width, channels]` and type
  `float32`, `float64`, `qint8`, `quint8`, or `qint32`.
* <b>`ksize`</b>: An int or list of `ints` that has length `1`, `3` or `5`. The size of
  the window for each dimension of the input tensor.
* <b>`strides`</b>: An int or list of `ints` that has length `1`, `3` or `5`. The
  stride of the sliding window for each dimension of the input tensor.
* <b>`padding`</b>: A string, either `'VALID'` or `'SAME'`. The padding algorithm.
  See the "returns" section of <a href="../../tf/nn/convolution.md"><code>tf.nn.convolution</code></a> for details.
* <b>`data_format`</b>: A string. 'NDHWC' and 'NCDHW' are supported.
* <b>`name`</b>: Optional name for the operation.


#### Returns:

A `Tensor` with the same type as `value`.  The average pooled output tensor.


## Compat aliases

* `tf.compat.v1.nn.avg_pool3d`
* `tf.compat.v2.nn.avg_pool3d`

