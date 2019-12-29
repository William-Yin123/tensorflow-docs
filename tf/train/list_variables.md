<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.train.list_variables" />
<meta itemprop="path" content="Stable" />
</div>

# tf.train.list_variables

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/training/checkpoint_utils.py">View source</a>



Returns list of all variables in the checkpoint.

``` python
tf.train.list_variables(ckpt_dir_or_file)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`ckpt_dir_or_file`</b>: Directory with checkpoints file or path to checkpoint.


#### Returns:

List of tuples `(name, shape)`.


## Compat aliases

* `tf.compat.v1.train.list_variables`
* `tf.compat.v2.train.list_variables`

