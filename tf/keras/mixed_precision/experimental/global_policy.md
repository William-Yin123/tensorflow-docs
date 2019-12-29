<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.mixed_precision.experimental.global_policy" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.mixed_precision.experimental.global_policy

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/mixed_precision/experimental/policy.py">View source</a>



Returns the global Policy.

``` python
tf.keras.mixed_precision.experimental.global_policy()
```



<!-- Placeholder for "Used in" -->

The global policy is the default policy used for layers, if no policy is
passed to the layer constructor. If no policy has been set with
<a href="../../../../tf/keras/mixed_precision/experimental/set_policy.md"><code>keras.mixed_precision.experimental.set_policy</code></a>, this will return a policy
constructed from <a href="../../../../tf/keras/backend/floatx.md"><code>tf.keras.backend.floatx()</code></a> in TensorFlow 2 (floatx defaults
to float32), or an "infer" policy in TensorFlow 1.

See <a href="../../../../tf/keras/mixed_precision/experimental/Policy.md"><code>keras.mixed_precision.experimental.Policy</code></a> for more information.

#### Returns:

The global Policy.


## Compat aliases

* `tf.compat.v1.keras.mixed_precision.experimental.global_policy`
* `tf.compat.v2.keras.mixed_precision.experimental.global_policy`

