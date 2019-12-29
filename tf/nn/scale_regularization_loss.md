<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.scale_regularization_loss" />
<meta itemprop="path" content="Stable" />
</div>

# tf.nn.scale_regularization_loss

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/nn_impl.py">View source</a>



Scales the sum of the given regularization losses by number of replicas.

``` python
tf.nn.scale_regularization_loss(regularization_loss)
```



<!-- Placeholder for "Used in" -->

Usage with distribution strategy and custom training loop:

```python
with strategy.scope():
  def compute_loss(self, label, predictions):
    per_example_loss = tf.keras.losses.sparse_categorical_crossentropy(
        labels, predictions)

    # Compute loss that is scaled by sample_weight and by global batch size.
    loss = tf.compute_average_loss(
        per_example_loss,
        sample_weight=sample_weight,
        global_batch_size=GLOBAL_BATCH_SIZE)

    # Add scaled regularization losses.
    loss += tf.scale_regularization_loss(tf.nn.l2_loss(weights))
    return loss
```

#### Args:


* <b>`regularization_loss`</b>: Regularization loss.


#### Returns:

Scalar loss value.


## Compat aliases

* `tf.compat.v1.nn.scale_regularization_loss`
* `tf.compat.v2.nn.scale_regularization_loss`

