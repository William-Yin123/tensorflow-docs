<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.switch" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.switch

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Switches between two operations depending on a scalar value.

``` python
tf.keras.backend.switch(
    condition,
    then_expression,
    else_expression
)
```



<!-- Placeholder for "Used in" -->

Note that both `then_expression` and `else_expression`
should be symbolic tensors of the *same shape*.

#### Arguments:


* <b>`condition`</b>: tensor (`int` or `bool`).
* <b>`then_expression`</b>: either a tensor, or a callable that returns a tensor.
* <b>`else_expression`</b>: either a tensor, or a callable that returns a tensor.


#### Returns:

The selected tensor.



#### Raises:


* <b>`ValueError`</b>: If rank of `condition` is greater than rank of expressions.

## Compat aliases

* `tf.compat.v1.keras.backend.switch`
* `tf.compat.v2.keras.backend.switch`

