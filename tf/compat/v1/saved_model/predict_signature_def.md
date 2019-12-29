<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.saved_model.predict_signature_def" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.saved_model.predict_signature_def

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/saved_model/signature_def_utils_impl.py">View source</a>



Creates prediction signature from given inputs and outputs.

``` python
tf.compat.v1.saved_model.predict_signature_def(
    inputs,
    outputs
)
```



<!-- Placeholder for "Used in" -->

This function produces signatures intended for use with the TensorFlow Serving
Predict API (tensorflow_serving/apis/prediction_service.proto). This API
imposes no constraints on the input and output types.

#### Args:


* <b>`inputs`</b>: dict of string to `Tensor`.
* <b>`outputs`</b>: dict of string to `Tensor`.


#### Returns:

A prediction-flavored signature_def.



#### Raises:


* <b>`ValueError`</b>: If inputs or outputs is `None`.

## Compat aliases

* `tf.compat.v1.saved_model.signature_def_utils.predict_signature_def`

