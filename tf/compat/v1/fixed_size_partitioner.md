<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.fixed_size_partitioner" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.fixed_size_partitioner

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/partitioned_variables.py">View source</a>



Partitioner to specify a fixed number of shards along given axis.

``` python
tf.compat.v1.fixed_size_partitioner(
    num_shards,
    axis=0
)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`num_shards`</b>: `int`, number of shards to partition variable.
* <b>`axis`</b>: `int`, axis to partition on.


#### Returns:

A partition function usable as the `partitioner` argument to
`variable_scope` and `get_variable`.


