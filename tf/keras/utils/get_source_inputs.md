<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.utils.get_source_inputs" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.utils.get_source_inputs

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/utils/layer_utils.py">View source</a>



Returns the list of input tensors necessary to compute `tensor`.

``` python
tf.keras.utils.get_source_inputs(
    tensor,
    layer=None,
    node_index=None
)
```



<!-- Placeholder for "Used in" -->

Output will always be a list of tensors
(potentially with 1 element).

#### Arguments:


* <b>`tensor`</b>: The tensor to start from.
* <b>`layer`</b>: Origin layer of the tensor. Will be
    determined via tensor._keras_history if not provided.
* <b>`node_index`</b>: Origin node index of the tensor.


#### Returns:

List of input tensors.


## Compat aliases

* `tf.compat.v1.keras.utils.get_source_inputs`
* `tf.compat.v2.keras.utils.get_source_inputs`

