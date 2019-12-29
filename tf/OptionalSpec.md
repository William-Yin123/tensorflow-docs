<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.OptionalSpec" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="value_type"/>
<meta itemprop="property" content="__eq__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__ne__"/>
<meta itemprop="property" content="from_value"/>
<meta itemprop="property" content="is_compatible_with"/>
<meta itemprop="property" content="most_specific_compatible_type"/>
</div>

# tf.OptionalSpec

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/optional_ops.py">View source</a>



## Class `OptionalSpec`

Represents an optional potentially containing a structured value.

Inherits From: [`TypeSpec`](../tf/TypeSpec.md)

<!-- Placeholder for "Used in" -->


<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/optional_ops.py">View source</a>

``` python
__init__(value_structure)
```

Initialize self.  See help(type(self)) for accurate signature.




## Properties

<h3 id="value_type"><code>value_type</code></h3>

The Python type for values that are compatible with this TypeSpec.




## Methods

<h3 id="__eq__"><code>__eq__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/framework/type_spec.py">View source</a>

``` python
__eq__(other)
```

Return self==value.


<h3 id="__ne__"><code>__ne__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/framework/type_spec.py">View source</a>

``` python
__ne__(other)
```

Return self!=value.


<h3 id="from_value"><code>from_value</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/data/ops/optional_ops.py">View source</a>

``` python
@staticmethod
from_value(value)
```




<h3 id="is_compatible_with"><code>is_compatible_with</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/framework/type_spec.py">View source</a>

``` python
is_compatible_with(spec_or_value)
```

Returns true if `spec_or_value` is compatible with this TypeSpec.


<h3 id="most_specific_compatible_type"><code>most_specific_compatible_type</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/framework/type_spec.py">View source</a>

``` python
most_specific_compatible_type(other)
```

Returns the most specific TypeSpec compatible with `self` and `other`.


#### Args:


* <b>`other`</b>: A `TypeSpec`.


#### Raises:


* <b>`ValueError`</b>: If there is no TypeSpec that is compatible with both `self`
  and `other`.





## Compat aliases

* `tf.compat.v1.OptionalSpec`
* `tf.compat.v1.data.experimental.OptionalStructure`
* `tf.compat.v2.OptionalSpec`

