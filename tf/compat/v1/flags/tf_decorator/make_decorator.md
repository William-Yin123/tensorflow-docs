<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.flags.tf_decorator.make_decorator" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.flags.tf_decorator.make_decorator

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/util/tf_decorator.py">View source</a>



Make a decorator from a wrapper and a target.

``` python
tf.compat.v1.flags.tf_decorator.make_decorator(
    target,
    decorator_func,
    decorator_name=None,
    decorator_doc='',
    decorator_argspec=None
)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`target`</b>: The final callable to be wrapped.
* <b>`decorator_func`</b>: The wrapper function.
* <b>`decorator_name`</b>: The name of the decorator. If `None`, the name of the
  function calling make_decorator.
* <b>`decorator_doc`</b>: Documentation specific to this application of
  `decorator_func` to `target`.
* <b>`decorator_argspec`</b>: The new callable signature of this decorator.


#### Returns:

The `decorator_func` argument with new metadata attached.


## Compat aliases

* `tf.compat.v1.app.flags.tf_decorator.make_decorator`

