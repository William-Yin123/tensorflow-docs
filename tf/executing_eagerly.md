<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.executing_eagerly" />
<meta itemprop="path" content="Stable" />
</div>

# tf.executing_eagerly

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/eager/context.py">View source</a>



Checks whether the current thread has eager execution enabled.

``` python
tf.executing_eagerly()
```



<!-- Placeholder for "Used in" -->

Eager execution is enabled by default and this API returns `True`
in most of cases. However, this API might return `False` in the following use
cases.

*  Executing inside <a href="../tf/function.md"><code>tf.function</code></a>, unless under <a href="../tf/init_scope.md"><code>tf.init_scope</code></a> or
   <a href="../tf/config/experimental_run_functions_eagerly.md"><code>tf.config.experimental_run_functions_eagerly(True)</code></a> is previously called.
*  Executing inside a transformation function for `tf.dataset`.
*  <a href="../tf/compat/v1/disable_eager_execution.md"><code>tf.compat.v1.disable_eager_execution()</code></a> is called.

#### General case:



```
>>> print(tf.executing_eagerly())
True
```

Inside <a href="../tf/function.md"><code>tf.function</code></a>:

```
>>> @tf.function
... def fn():
...   with tf.init_scope():
...     print(tf.executing_eagerly())
...   print(tf.executing_eagerly())
>>> fn()
True
False
```

Inside <a href="../tf/function.md"><code>tf.function</code></a> after

<a href="../tf/config/experimental_run_functions_eagerly.md"><code>tf.config.experimental_run_functions_eagerly(True)</code></a> is called:
>>> tf.config.experimental_run_functions_eagerly(True)
>>> @tf.function
... def fn():
...   with tf.init_scope():
...     print(tf.executing_eagerly())
...   print(tf.executing_eagerly())
>>> fn()
True
True
>>> tf.config.experimental_run_functions_eagerly(False)

Inside a transformation function for `tf.dataset`:

```
>>> def data_fn(x):
...   print(tf.executing_eagerly())
...   return x
>>> dataset = tf.data.Dataset.range(100)
>>> dataset = dataset.map(data_fn)
False
```

#### Returns:

`True` if the current thread has eager execution enabled.


## Compat aliases

* `tf.compat.v2.executing_eagerly`

