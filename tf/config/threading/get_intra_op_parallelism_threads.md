<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.config.threading.get_intra_op_parallelism_threads" />
<meta itemprop="path" content="Stable" />
</div>

# tf.config.threading.get_intra_op_parallelism_threads

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/framework/config.py">View source</a>



Get number of threads used within an individual op for parallelism.

``` python
tf.config.threading.get_intra_op_parallelism_threads()
```



<!-- Placeholder for "Used in" -->

Certain operations like matrix multiplication and reductions can utilize
parallel threads for speed ups. A value of 0 means the system picks an
appropriate number.

#### Returns:

Number of parallel threads


## Compat aliases

* `tf.compat.v1.config.threading.get_intra_op_parallelism_threads`
* `tf.compat.v2.config.threading.get_intra_op_parallelism_threads`

