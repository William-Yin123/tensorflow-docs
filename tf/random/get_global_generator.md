<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.random.get_global_generator" />
<meta itemprop="path" content="Stable" />
</div>

# tf.random.get_global_generator

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/stateful_random_ops.py">View source</a>



Retrieves the global generator.

**Aliases**: `tf.random.experimental.get_global_generator`

``` python
tf.random.get_global_generator()
```



<!-- Placeholder for "Used in" -->

This function will create the global generator the first time it is called,
and the generator will be placed at the default device at that time, so one
needs to be careful when this function is first called. Using a generator
placed on a less-ideal device will incur performance regression.

#### Returns:

The global <a href="../../tf/random/Generator.md"><code>tf.random.Generator</code></a> object.


## Compat aliases

* `tf.compat.v1.random.experimental.get_global_generator`
* `tf.compat.v1.random.get_global_generator`
* `tf.compat.v2.random.experimental.get_global_generator`
* `tf.compat.v2.random.get_global_generator`

