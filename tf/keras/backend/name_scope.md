<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.name_scope" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.name_scope

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



A context manager for use when defining a Python op.

``` python
tf.keras.backend.name_scope(name)
```



<!-- Placeholder for "Used in" -->

This context manager pushes a name scope, which will make the name of all
operations added within it have a prefix.

For example, to define a new Python op called `my_op`:


def my_op(a):
  with tf.name_scope("MyOp") as scope:
    a = tf.convert_to_tensor(a, name="a")
    # Define some computation that uses `a`.
    return foo_op(..., name=scope)


When executed, the Tensor `a` will have the name `MyOp/a`.

#### Args:


* <b>`name`</b>: The prefix to use on all names created within the name scope.


#### Returns:

Name scope context manager.


## Compat aliases

* `tf.compat.v2.keras.backend.name_scope`

