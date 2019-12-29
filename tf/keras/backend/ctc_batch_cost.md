<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.ctc_batch_cost" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.ctc_batch_cost

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Runs CTC loss algorithm on each batch element.

``` python
tf.keras.backend.ctc_batch_cost(
    y_true,
    y_pred,
    input_length,
    label_length
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`y_true`</b>: tensor `(samples, max_string_length)`
    containing the truth labels.
* <b>`y_pred`</b>: tensor `(samples, time_steps, num_categories)`
    containing the prediction, or output of the softmax.
* <b>`input_length`</b>: tensor `(samples, 1)` containing the sequence length for
    each batch item in `y_pred`.
* <b>`label_length`</b>: tensor `(samples, 1)` containing the sequence length for
    each batch item in `y_true`.


#### Returns:

Tensor with shape (samples,1) containing the
    CTC loss of each element.


## Compat aliases

* `tf.compat.v1.keras.backend.ctc_batch_cost`
* `tf.compat.v2.keras.backend.ctc_batch_cost`

