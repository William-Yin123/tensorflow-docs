<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.max_pool2d" />
<meta itemprop="path" content="Stable" />
</div>

# tf.nn.max_pool2d

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/nn_ops.py">View source</a>



Performs the max pooling on the input.

``` python
tf.nn.max_pool2d(
    input,
    ksize,
    strides,
    padding,
    data_format='NHWC',
    name=None
)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`input`</b>: A 4-D `Tensor` of the format specified by `data_format`.
* <b>`ksize`</b>: An int or list of `ints` that has length `1`, `2` or `4`. The size of
  the window for each dimension of the input tensor.
* <b>`strides`</b>: An int or list of `ints` that has length `1`, `2` or `4`. The
  stride of the sliding window for each dimension of the input tensor.
* <b>`padding`</b>: A string, either `'VALID'` or `'SAME'`. The padding algorithm. See
  the "returns" section of <a href="../../tf/nn/convolution.md"><code>tf.nn.convolution</code></a> for details.
* <b>`data_format`</b>: A string. 'NHWC', 'NCHW' and 'NCHW_VECT_C' are supported.
* <b>`name`</b>: Optional name for the operation.


#### Returns:

A `Tensor` of format specified by `data_format`.
The max pooled output tensor.


## Compat aliases

* `tf.compat.v1.nn.max_pool2d`
* `tf.compat.v2.nn.max_pool2d`

