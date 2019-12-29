<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.callbacks.TensorBoard" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="set_model"/>
<meta itemprop="property" content="set_params"/>
</div>

# tf.keras.callbacks.TensorBoard

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/callbacks.py">View source</a>



## Class `TensorBoard`

Enable visualizations for TensorBoard.

Inherits From: [`Callback`](../../../tf/keras/callbacks/Callback.md)

<!-- Placeholder for "Used in" -->

TensorBoard is a visualization tool provided with TensorFlow.

This callback logs events for TensorBoard, including:

* Metrics summary plots
* Training graph visualization
* Activation histograms
* Sampled profiling

If you have installed TensorFlow with pip, you should be able
to launch TensorBoard from the command line:

```sh
tensorboard --logdir=path_to_your_logs
```

You can find more information about TensorBoard
[here](https://www.tensorflow.org/get_started/summaries_and_tensorboard).

#### Arguments:


* <b>`log_dir`</b>: the path of the directory where to save the log files to be
  parsed by TensorBoard.
* <b>`histogram_freq`</b>: frequency (in epochs) at which to compute activation and
  weight histograms for the layers of the model. If set to 0, histograms
  won't be computed. Validation data (or split) must be specified for
  histogram visualizations.
* <b>`write_graph`</b>: whether to visualize the graph in TensorBoard. The log file
  can become quite large when write_graph is set to True.
* <b>`write_images`</b>: whether to write model weights to visualize as image in
  TensorBoard.
* <b>`update_freq`</b>: `'batch'` or `'epoch'` or integer. When using `'batch'`,
  writes the losses and metrics to TensorBoard after each batch. The same
  applies for `'epoch'`. If using an integer, let's say `1000`, the
  callback will write the metrics and losses to TensorBoard every 1000
  batches. Note that writing too frequently to TensorBoard can slow down
  your training.
* <b>`profile_batch`</b>: Profile the batch to sample compute characteristics. By
  default, it will profile the second batch. Set profile_batch=0 to
  disable profiling. Must run in TensorFlow eager mode.
* <b>`embeddings_freq`</b>: frequency (in epochs) at which embedding layers will
  be visualized. If set to 0, embeddings won't be visualized.
* <b>`embeddings_metadata`</b>: a dictionary which maps layer name to a file name in
  which metadata for this embedding layer is saved. See the
  [details](
    https://www.tensorflow.org/how_tos/embedding_viz/#metadata_optional)
  about metadata files format. In case if the same metadata file is
  used for all embedding layers, string can be passed.


#### Raises:


* <b>`ValueError`</b>: If histogram_freq is set and no validation data is provided.

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/callbacks.py">View source</a>

``` python
__init__(
    log_dir='logs',
    histogram_freq=0,
    write_graph=True,
    write_images=False,
    update_freq='epoch',
    profile_batch=2,
    embeddings_freq=0,
    embeddings_metadata=None,
    **kwargs
)
```

Initialize self.  See help(type(self)) for accurate signature.




## Methods

<h3 id="set_model"><code>set_model</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/callbacks.py">View source</a>

``` python
set_model(model)
```

Sets Keras model and writes graph if specified.


<h3 id="set_params"><code>set_params</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/callbacks.py">View source</a>

``` python
set_params(params)
```








## Compat aliases

* `tf.compat.v2.keras.callbacks.TensorBoard`

