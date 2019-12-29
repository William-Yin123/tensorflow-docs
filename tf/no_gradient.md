<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.no_gradient" />
<meta itemprop="path" content="Stable" />
</div>

# tf.no_gradient

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/framework/ops.py">View source</a>



Specifies that ops of type `op_type` is not differentiable.

``` python
tf.no_gradient(op_type)
```



<!-- Placeholder for "Used in" -->

This function should *not* be used for operations that have a
well-defined gradient that is not yet implemented.

This function is only used when defining a new op type. It may be
used for ops such as <a href="../tf/size.md"><code>tf.size()</code></a> that are not differentiable.  For
example:

```python
tf.no_gradient("Size")
```

The gradient computed for 'op_type' will then propagate zeros.

For ops that have a well-defined gradient but are not yet implemented,
no declaration should be made, and an error *must* be thrown if
an attempt to request its gradient is made.

#### Args:


* <b>`op_type`</b>: The string type of an operation. This corresponds to the
  `OpDef.name` field for the proto that defines the operation.


#### Raises:


* <b>`TypeError`</b>: If `op_type` is not a string.

## Compat aliases

* `tf.compat.v1.NoGradient`
* `tf.compat.v1.NotDifferentiable`
* `tf.compat.v1.no_gradient`
* `tf.compat.v2.no_gradient`

