<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.estimator.experimental.build_raw_supervised_input_receiver_fn" />
<meta itemprop="path" content="Stable" />
</div>

# tf.estimator.experimental.build_raw_supervised_input_receiver_fn

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">

<td>
  <a target="_blank" href="https://github.com/tensorflow/estimator/tree/master/tensorflow_estimator/python/estimator/export/export.py">
    <img src="https://www.tensorflow.org/images/GitHub-Mark-32px.png" />
    View source on GitHub
  </a>
</td></table>



Build a supervised_input_receiver_fn for raw features and labels.

``` python
tf.estimator.experimental.build_raw_supervised_input_receiver_fn(
    features,
    labels,
    default_batch_size=None
)
```



<!-- Placeholder for "Used in" -->

This function wraps tensor placeholders in a supervised_receiver_fn
with the expectation that the features and labels appear precisely as
the model_fn expects them. Features and labels can therefore be dicts of
tensors, or raw tensors.

#### Args:


* <b>`features`</b>: a dict of string to `Tensor` or `Tensor`.
* <b>`labels`</b>: a dict of string to `Tensor` or `Tensor`.
* <b>`default_batch_size`</b>: the number of query examples expected per batch.
    Leave unset for variable batch size (recommended).


#### Returns:

A supervised_input_receiver_fn.



#### Raises:


* <b>`ValueError`</b>: if features and labels have overlapping keys.

## Compat aliases

* `tf.compat.v1.estimator.experimental.build_raw_supervised_input_receiver_fn`
* `tf.compat.v2.estimator.experimental.build_raw_supervised_input_receiver_fn`

