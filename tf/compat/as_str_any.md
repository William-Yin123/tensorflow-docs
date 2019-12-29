<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.as_str_any" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.as_str_any

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/util/compat.py">View source</a>



Converts input to `str` type.

``` python
tf.compat.as_str_any(value)
```



<!-- Placeholder for "Used in" -->

   Uses `str(value)`, except for `bytes` typed inputs, which are converted
   using `as_str`.

#### Args:


* <b>`value`</b>: A object that can be converted to `str`.


#### Returns:

A `str` object.


## Compat aliases

* `tf.compat.v1.compat.as_str_any`
* `tf.compat.v2.compat.as_str_any`

