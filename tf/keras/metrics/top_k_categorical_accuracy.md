<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.metrics.top_k_categorical_accuracy" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.metrics.top_k_categorical_accuracy

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/metrics.py">View source</a>



Computes how often targets are in the top `K` predictions.

**Aliases**: `tf.metrics.top_k_categorical_accuracy`

``` python
tf.keras.metrics.top_k_categorical_accuracy(
    y_true,
    y_pred,
    k=5
)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`y_true`</b>: The ground truth values.
* <b>`y_pred`</b>: The prediction values.
* <b>`k`</b>: (Optional) Number of top elements to look at for computing accuracy.
  Defaults to 5.


#### Returns:

Top K categorical accuracy value.


## Compat aliases

* `tf.compat.v1.keras.metrics.top_k_categorical_accuracy`
* `tf.compat.v2.keras.metrics.top_k_categorical_accuracy`
* `tf.compat.v2.metrics.top_k_categorical_accuracy`

