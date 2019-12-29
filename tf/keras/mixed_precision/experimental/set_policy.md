<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.mixed_precision.experimental.set_policy" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.mixed_precision.experimental.set_policy

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/mixed_precision/experimental/policy.py">View source</a>



Sets the global Policy.

``` python
tf.keras.mixed_precision.experimental.set_policy(policy)
```



<!-- Placeholder for "Used in" -->

The global policy is the default policy used for layers, if no policy is
passed to the layer constructor. If no global policy is set, layers will
instead default to a Policy constructed from <a href="../../../../tf/keras/backend/floatx.md"><code>tf.keras.backend.floatx()</code></a> in
TensorFlow 2. In TensorFlow 1, layers default to an "infer" policy.

See <a href="../../../../tf/keras/mixed_precision/experimental/Policy.md"><code>keras.mixed_precision.experimental.Policy</code></a> for more information.

#### Args:


* <b>`policy`</b>: A Policy, or a string that will be converted to a Policy..

## Compat aliases

* `tf.compat.v1.keras.mixed_precision.experimental.set_policy`
* `tf.compat.v2.keras.mixed_precision.experimental.set_policy`

