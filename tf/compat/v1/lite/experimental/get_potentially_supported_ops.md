<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.lite.experimental.get_potentially_supported_ops" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.lite.experimental.get_potentially_supported_ops

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/lite/experimental/tensorboard/ops_util.py">View source</a>



Returns operations potentially supported by TensorFlow Lite.

``` python
tf.compat.v1.lite.experimental.get_potentially_supported_ops()
```



<!-- Placeholder for "Used in" -->

The potentially support list contains a list of ops that are partially or
fully supported, which is derived by simply scanning op names to check whether
they can be handled without real conversion and specific parameters.

Given that some ops may be partially supported, the optimal way to determine
if a model's operations are supported is by converting using the TensorFlow
Lite converter.

#### Returns:

A list of SupportedOp.


