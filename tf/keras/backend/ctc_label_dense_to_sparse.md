<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.ctc_label_dense_to_sparse" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.ctc_label_dense_to_sparse

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Converts CTC labels from dense to sparse.

``` python
tf.keras.backend.ctc_label_dense_to_sparse(
    labels,
    label_lengths
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`labels`</b>: dense CTC labels.
* <b>`label_lengths`</b>: length of the labels.


#### Returns:

A sparse tensor representation of the labels.


## Compat aliases

* `tf.compat.v1.keras.backend.ctc_label_dense_to_sparse`
* `tf.compat.v2.keras.backend.ctc_label_dense_to_sparse`

