<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.grad_pass_through" />
<meta itemprop="path" content="Stable" />
</div>

# tf.grad_pass_through

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/custom_gradient.py">View source</a>



Creates a grad-pass-through op with the forward behavior provided in f.

``` python
tf.grad_pass_through(f)
```



<!-- Placeholder for "Used in" -->

Use this function to wrap any op, maintaining its behavior in the forward
pass, but replacing the original op in the backward graph with an identity.
For example:

```python
x = tf.Variable(1.0, name="x")
z = tf.Variable(3.0, name="z")

with tf.GradientTape() as tape:
  # y will evaluate to 9.0
  y = tf.grad_pass_through(x.assign)(z**2)
# grads will evaluate to 6.0
grads = tape.gradient(y, z)
```

Another example is a 'differentiable' moving average approximation, where
gradients are allowed to flow into the last value fed to the moving average,
but the moving average is still used for the forward pass:

```python
x = ... # Some scalar value
# A moving average object, we don't need to know how this is implemented
moving_average = MovingAverage()
with backprop.GradientTape() as tape:
  # mavg_x will evaluate to the current running average value
  mavg_x = tf.grad_pass_through(moving_average)(x)
grads = tape.gradient(mavg_x, x) # grads will evaluate to 1.0
```

#### Args:


* <b>`f`</b>: function `f(*x)` that returns a `Tensor` or nested structure of `Tensor`
  outputs.


#### Returns:

A function `h(x)` which returns the same values as `f(x)` and whose
gradients are the same as those of an identity function.


## Compat aliases

* `tf.compat.v1.grad_pass_through`
* `tf.compat.v2.grad_pass_through`

