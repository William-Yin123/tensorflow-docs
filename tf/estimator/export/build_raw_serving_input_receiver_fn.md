<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.estimator.export.build_raw_serving_input_receiver_fn" />
<meta itemprop="path" content="Stable" />
</div>

# tf.estimator.export.build_raw_serving_input_receiver_fn

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">

<td>
  <a target="_blank" href="https://github.com/tensorflow/estimator/tree/master/tensorflow_estimator/python/estimator/export/export.py">
    <img src="https://www.tensorflow.org/images/GitHub-Mark-32px.png" />
    View source on GitHub
  </a>
</td></table>



Build a serving_input_receiver_fn expecting feature Tensors.

``` python
tf.estimator.export.build_raw_serving_input_receiver_fn(
    features,
    default_batch_size=None
)
```



<!-- Placeholder for "Used in" -->

Creates an serving_input_receiver_fn that expects all features to be fed
directly.

#### Args:


* <b>`features`</b>: a dict of string to `Tensor`.
* <b>`default_batch_size`</b>: the number of query examples expected per batch.
    Leave unset for variable batch size (recommended).


#### Returns:

A serving_input_receiver_fn.


## Compat aliases

* `tf.compat.v1.estimator.export.build_raw_serving_input_receiver_fn`
* `tf.compat.v2.estimator.export.build_raw_serving_input_receiver_fn`

