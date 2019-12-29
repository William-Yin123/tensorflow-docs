<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.metrics.sparse_categorical_accuracy" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.metrics.sparse_categorical_accuracy

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/metrics.py">View source</a>



Calculates how often predictions matches integer labels.

**Aliases**: `tf.metrics.sparse_categorical_accuracy`

``` python
tf.keras.metrics.sparse_categorical_accuracy(
    y_true,
    y_pred
)
```



<!-- Placeholder for "Used in" -->

You can provide logits of classes as `y_pred`, since argmax of
logits and probabilities are same.

#### Args:


* <b>`y_true`</b>: Integer ground truth values.
* <b>`y_pred`</b>: The prediction values.


#### Returns:

Sparse categorical accuracy values.


## Compat aliases

* `tf.compat.v1.keras.metrics.sparse_categorical_accuracy`
* `tf.compat.v2.keras.metrics.sparse_categorical_accuracy`
* `tf.compat.v2.metrics.sparse_categorical_accuracy`

