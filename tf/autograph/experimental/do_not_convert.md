<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.autograph.experimental.do_not_convert" />
<meta itemprop="path" content="Stable" />
</div>

# tf.autograph.experimental.do_not_convert

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/autograph/impl/api.py">View source</a>



Decorator that suppresses the conversion of a function.

``` python
tf.autograph.experimental.do_not_convert(func=None)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`func`</b>: function to decorate.


#### Returns:

If `func` is not None, returns a `Callable` which is equivalent to
`func`, but is not converted by AutoGraph.
If `func` is None, returns a decorator that, when invoked with a
single `func` argument, returns a `Callable` equivalent to the
above case.


## Compat aliases

* `tf.compat.v1.autograph.experimental.do_not_convert`
* `tf.compat.v2.autograph.experimental.do_not_convert`

