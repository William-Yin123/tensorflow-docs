<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.lookup.KeyValueTensorInitializer" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="key_dtype"/>
<meta itemprop="property" content="value_dtype"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="initialize"/>
</div>

# tf.lookup.KeyValueTensorInitializer

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/lookup_ops.py">View source</a>



## Class `KeyValueTensorInitializer`

Table initializers given `keys` and `values` tensors.



<!-- Placeholder for "Used in" -->


<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/ops/lookup_ops.py">View source</a>

``` python
__init__(
    keys,
    values,
    key_dtype=None,
    value_dtype=None,
    name=None
)
```

Constructs a table initializer object based on keys and values tensors.


#### Args:


* <b>`keys`</b>: The tensor for the keys.
* <b>`values`</b>: The tensor for the values.
* <b>`key_dtype`</b>: The `keys` data type. Used when `keys` is a python array.
* <b>`value_dtype`</b>: The `values` data type. Used when `values` is a python array.
* <b>`name`</b>: A name for the operation (optional).



## Properties

<h3 id="key_dtype"><code>key_dtype</code></h3>

The expected table key dtype.


<h3 id="value_dtype"><code>value_dtype</code></h3>

The expected table value dtype.




## Methods

<h3 id="initialize"><code>initialize</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/lookup_ops.py">View source</a>

``` python
initialize(table)
```

Initializes the given `table` with `keys` and `values` tensors.


#### Args:


* <b>`table`</b>: The table to initialize.


#### Returns:

The operation that initializes the table.



#### Raises:


* <b>`TypeError`</b>: when the keys and values data types do not match the table
key and value data types.





## Compat aliases

* `tf.compat.v1.lookup.KeyValueTensorInitializer`
* `tf.compat.v2.lookup.KeyValueTensorInitializer`

