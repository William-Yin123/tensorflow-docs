<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.debugging.assert_shapes" />
<meta itemprop="path" content="Stable" />
</div>

# tf.debugging.assert_shapes

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/check_ops.py">View source</a>



Assert tensor shapes and dimension size relationships between tensors.

``` python
tf.debugging.assert_shapes(
    shapes,
    data=None,
    summarize=None,
    message=None,
    name=None
)
```



<!-- Placeholder for "Used in" -->

This Op checks that a collection of tensors shape relationships
satisfies given constraints.

#### Example:



```
>>> n = 10
>>> q = 3
>>> d = 7
>>> x = tf.zeros([n,q]) 
>>> y = tf.ones([n,d])
>>> param = tf.Variable([1.0, 2.0, 3.0])
>>> scalar = 1.0
>>> tf.debugging.assert_shapes([
...  (x, ('N', 'Q')),
...  (y, ('N', 'D')),
...  (param, ('Q',)),
...  (scalar, ()),
... ])
```

```
>>> tf.debugging.assert_shapes([
...   (x, ('N', 'D')), 
...   (y, ('N', 'D'))
... ])
Traceback (most recent call last):
...
ValueError: ...
```

If `x`, `y`, `param` or `scalar` does not have a shape that satisfies
all specified constraints, `message`, as well as the first `summarize` entries
of the first encountered violating tensor are printed, and
`InvalidArgumentError` is raised.

Size entries in the specified shapes are checked against other entries by
their __hash__, except:
  - a size entry is interpreted as an explicit size if it can be parsed as an
    integer primitive.
  - a size entry is interpreted as *any* size if it is None or '.'.

If the first entry of a shape is `...` (type `Ellipsis`) or '*' that indicates
a variable number of outer dimensions of unspecified size, i.e. the constraint
applies to the inner-most dimensions only.

Scalar tensors and specified shapes of length zero (excluding the 'inner-most'
prefix) are both treated as having a single dimension of size one.

#### Args:


* <b>`shapes`</b>: dictionary with (`Tensor` to shape) items. A shape must be an
  iterable.
* <b>`data`</b>: The tensors to print out if the condition is False.  Defaults to error
  message and first few entries of the violating tensor.
* <b>`summarize`</b>: Print this many entries of the tensor.
* <b>`message`</b>: A string to prefix to the default message.
* <b>`name`</b>: A name for this operation (optional).  Defaults to "assert_shapes".


#### Raises:


* <b>`ValueError`</b>:  If static checks determine any shape constraint is violated.

## Compat aliases

* `tf.compat.v2.debugging.assert_shapes`

