<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.saved_model.build_signature_def" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.saved_model.build_signature_def

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/saved_model/signature_def_utils_impl.py">View source</a>



Utility function to build a SignatureDef protocol buffer.

``` python
tf.compat.v1.saved_model.build_signature_def(
    inputs=None,
    outputs=None,
    method_name=None
)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`inputs`</b>: Inputs of the SignatureDef defined as a proto map of string to
    tensor info.
* <b>`outputs`</b>: Outputs of the SignatureDef defined as a proto map of string to
    tensor info.
* <b>`method_name`</b>: Method name of the SignatureDef as a string.


#### Returns:

A SignatureDef protocol buffer constructed based on the supplied arguments.


## Compat aliases

* `tf.compat.v1.saved_model.signature_def_utils.build_signature_def`

