<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.random.set_global_generator" />
<meta itemprop="path" content="Stable" />
</div>

# tf.random.set_global_generator

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/stateful_random_ops.py">View source</a>



Replaces the global generator with another `Generator` object.

**Aliases**: `tf.random.experimental.set_global_generator`

``` python
tf.random.set_global_generator(generator)
```



<!-- Placeholder for "Used in" -->

This function creates a new Generator object (and the Variable object within),
which does not work well with tf.function because (1) tf.function puts
restrictions on Variable creation thus reset_global_generator can't be freely
used inside tf.function; (2) redirecting a global variable to
a new object is problematic with tf.function because the old object may be
captured by a 'tf.function'ed function and still be used by it.
A 'tf.function'ed function only keeps weak references to variables,
so deleting a variable and then calling that function again may raise an
error, as demonstrated by
random_test.py/RandomTest.testResetGlobalGeneratorBadWithDefun .

#### Args:


* <b>`generator`</b>: the new `Generator` object.

## Compat aliases

* `tf.compat.v1.random.experimental.set_global_generator`
* `tf.compat.v1.random.set_global_generator`
* `tf.compat.v2.random.experimental.set_global_generator`
* `tf.compat.v2.random.set_global_generator`

