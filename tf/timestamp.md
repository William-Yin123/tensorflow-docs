<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.timestamp" />
<meta itemprop="path" content="Stable" />
</div>

# tf.timestamp

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>



Provides the time since epoch in seconds.

``` python
tf.timestamp(name=None)
```



<!-- Placeholder for "Used in" -->

Returns the timestamp as a `float64` for seconds since the Unix epoch.

Note: the timestamp is computed when the op is executed, not when it is added
to the graph.

#### Args:


* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `float64`.


## Compat aliases

* `tf.compat.v1.timestamp`
* `tf.compat.v2.timestamp`

