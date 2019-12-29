<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.config.experimental.enable_mlir_bridge" />
<meta itemprop="path" content="Stable" />
</div>

# tf.config.experimental.enable_mlir_bridge

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/framework/config.py">View source</a>



Enables experimental MLIR-Based TensorFlow Compiler Bridge.

``` python
tf.config.experimental.enable_mlir_bridge()
```



<!-- Placeholder for "Used in" -->

DO NOT USE, DEV AND TESTING ONLY AT THE MOMENT.

NOTE: MLIR-Based TensorFlow Compiler is under active development and has
missing features, please refrain from using. This API exists for development
and testing only.

TensorFlow Compiler Bridge (TF Bridge) is responsible for translating parts
of TensorFlow graph into a form that can be accepted as an input by a backend
compiler such as XLA.

## Compat aliases

* `tf.compat.v1.config.experimental.enable_mlir_bridge`
* `tf.compat.v2.config.experimental.enable_mlir_bridge`

