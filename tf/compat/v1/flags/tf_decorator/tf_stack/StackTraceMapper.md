<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.flags.tf_decorator.tf_stack.StackTraceMapper" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__enter__"/>
<meta itemprop="property" content="__exit__"/>
<meta itemprop="property" content="get_effective_source_map"/>
<meta itemprop="property" content="reset"/>
</div>

# tf.compat.v1.flags.tf_decorator.tf_stack.StackTraceMapper

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/util/tf_stack.py">View source</a>



## Class `StackTraceMapper`

Allows remapping traceback information to different source code.

Inherits From: [`StackTraceTransform`](../../../../../../tf/compat/v1/flags/tf_decorator/tf_stack/StackTraceTransform.md)

<!-- Placeholder for "Used in" -->


## Methods

<h3 id="__enter__"><code>__enter__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/util/tf_stack.py">View source</a>

``` python
__enter__()
```




<h3 id="__exit__"><code>__exit__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/util/tf_stack.py">View source</a>

``` python
__exit__(
    unused_type,
    unused_value,
    unused_traceback
)
```




<h3 id="get_effective_source_map"><code>get_effective_source_map</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/util/tf_stack.py">View source</a>

``` python
get_effective_source_map()
```

Returns a map (filename, lineno) -> (filename, lineno, function_name).


<h3 id="reset"><code>reset</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/util/tf_stack.py">View source</a>

``` python
reset()
```








## Compat aliases

* `tf.compat.v1.app.flags.tf_decorator.tf_stack.StackTraceMapper`

