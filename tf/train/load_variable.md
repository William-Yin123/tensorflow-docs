<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.train.load_variable" />
<meta itemprop="path" content="Stable" />
</div>

# tf.train.load_variable

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/training/checkpoint_utils.py">View source</a>



Returns the tensor value of the given variable in the checkpoint.

``` python
tf.train.load_variable(
    ckpt_dir_or_file,
    name
)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`ckpt_dir_or_file`</b>: Directory with checkpoints file or path to checkpoint.
* <b>`name`</b>: Name of the variable to return.


#### Returns:

A numpy `ndarray` with a copy of the value of this variable.


## Compat aliases

* `tf.compat.v1.train.load_variable`
* `tf.compat.v2.train.load_variable`

