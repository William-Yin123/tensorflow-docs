<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.flags.tf_decorator.unwrap" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.flags.tf_decorator.unwrap

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/util/tf_decorator.py">View source</a>



Unwraps an object into a list of TFDecorators and a final target.

``` python
tf.compat.v1.flags.tf_decorator.unwrap(maybe_tf_decorator)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`maybe_tf_decorator`</b>: Any callable object.


#### Returns:

A tuple whose first element is an list of TFDecorator-derived objects that
were applied to the final callable target, and whose second element is the
final undecorated callable target. If the `maybe_tf_decorator` parameter is
not decorated by any TFDecorators, the first tuple element will be an empty
list. The `TFDecorator` list is ordered from outermost to innermost
decorators.


## Compat aliases

* `tf.compat.v1.app.flags.tf_decorator.unwrap`

