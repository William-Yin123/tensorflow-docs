<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.test.compute_gradient" />
<meta itemprop="path" content="Stable" />
</div>

# tf.test.compute_gradient

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/gradient_checker_v2.py">View source</a>



Computes the theoretical and numeric Jacobian of `f`.

``` python
tf.test.compute_gradient(
    f,
    x,
    delta=0.001
)
```



<!-- Placeholder for "Used in" -->

With y = f(x), computes the theoretical and numeric Jacobian dy/dx.

#### Args:


* <b>`f`</b>: the function.
* <b>`x`</b>: a list arguments for the function
* <b>`delta`</b>: (optional) perturbation used to compute numeric Jacobian.


#### Returns:

A pair of lists, where the first is a list of 2-d numpy arrays representing
the theoretical Jacobians for each argument, and the second list is the
numerical ones. Each 2-d array has "y_size" rows
and "x_size" columns where "x_size" is the number of elements in the
corresponding argument and "y_size" is the number of elements in f(x).



#### Raises:


* <b>`ValueError`</b>: If result is empty but the gradient is nonzero.
* <b>`ValueError`</b>: If x is not list, but any other type.


#### Example:


```python
@tf.function
def test_func(x):
  return x*x

theoretical, numerical = tf.test.compute_gradient(test_func, [1.0])
theoretical, numerical
# ((array([[2.]], dtype=float32),), (array([[2.000004]], dtype=float32),))
```

## Compat aliases

* `tf.compat.v2.test.compute_gradient`

