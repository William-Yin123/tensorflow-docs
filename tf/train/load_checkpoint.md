<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.train.load_checkpoint" />
<meta itemprop="path" content="Stable" />
</div>

# tf.train.load_checkpoint

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/training/checkpoint_utils.py">View source</a>



Returns `CheckpointReader` for checkpoint found in `ckpt_dir_or_file`.

``` python
tf.train.load_checkpoint(ckpt_dir_or_file)
```



<!-- Placeholder for "Used in" -->

If `ckpt_dir_or_file` resolves to a directory with multiple checkpoints,
reader for the latest checkpoint is returned.

#### Args:


* <b>`ckpt_dir_or_file`</b>: Directory with checkpoints file or path to checkpoint
  file.


#### Returns:

`CheckpointReader` object.



#### Raises:


* <b>`ValueError`</b>: If `ckpt_dir_or_file` resolves to a directory with no
  checkpoints.

## Compat aliases

* `tf.compat.v1.train.load_checkpoint`
* `tf.compat.v2.train.load_checkpoint`

