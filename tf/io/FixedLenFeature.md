<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.io.FixedLenFeature" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="shape"/>
<meta itemprop="property" content="dtype"/>
<meta itemprop="property" content="default_value"/>
<meta itemprop="property" content="__new__"/>
</div>

# tf.io.FixedLenFeature

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/parsing_config.py">View source</a>



## Class `FixedLenFeature`

Configuration for parsing a fixed-length input feature.



<!-- Placeholder for "Used in" -->

To treat sparse input as dense, provide a `default_value`; otherwise,
the parse functions will fail on any examples missing this feature.

#### Fields:


* <b>`shape`</b>: Shape of input data.
* <b>`dtype`</b>: Data type of input.
* <b>`default_value`</b>: Value to be used if an example is missing this feature. It
    must be compatible with `dtype` and of the specified `shape`.

<h2 id="__new__"><code>__new__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/ops/parsing_config.py">View source</a>

``` python
@staticmethod
__new__(
    cls,
    shape,
    dtype,
    default_value=None
)
```

Create new instance of FixedLenFeature(shape, dtype, default_value)




## Properties

<h3 id="shape"><code>shape</code></h3>




<h3 id="dtype"><code>dtype</code></h3>




<h3 id="default_value"><code>default_value</code></h3>








## Compat aliases

* `tf.compat.v1.FixedLenFeature`
* `tf.compat.v1.io.FixedLenFeature`
* `tf.compat.v2.io.FixedLenFeature`

