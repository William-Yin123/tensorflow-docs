<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.train.latest_checkpoint" />
<meta itemprop="path" content="Stable" />
</div>

# tf.train.latest_checkpoint

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/training/checkpoint_management.py">View source</a>



Finds the filename of latest saved checkpoint file.

``` python
tf.train.latest_checkpoint(
    checkpoint_dir,
    latest_filename=None
)
```



<!-- Placeholder for "Used in" -->

Gets the checkpoint state given the provided checkpoint_dir and looks for a
corresponding TensorFlow 2 (preferred) or TensorFlow 1.x checkpoint path.
The latest_filename argument is only applicable if you are saving checkpoint
using `v1.Saver.save`


See the [Training Checkpoints
Guide](https://www.tensorflow.org/guide/checkpoint) for more details and
examples.`

#### Args:


* <b>`checkpoint_dir`</b>: Directory where the variables were saved.
* <b>`latest_filename`</b>: Optional name for the protocol buffer file that
  contains the list of most recent checkpoint filenames.
  See the corresponding argument to `v1.Saver.save`.


#### Returns:

The full path to the latest checkpoint or `None` if no checkpoint was found.


## Compat aliases

* `tf.compat.v1.train.latest_checkpoint`
* `tf.compat.v2.train.latest_checkpoint`

