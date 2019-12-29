<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.keras.callbacks.TensorBoard" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="set_model"/>
<meta itemprop="property" content="set_params"/>
</div>

# tf.compat.v1.keras.callbacks.TensorBoard

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/callbacks_v1.py">View source</a>



## Class `TensorBoard`

Enable visualizations for TensorBoard.

Inherits From: [`Callback`](../../../../../tf/keras/callbacks/Callback.md)

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
* <b>`write_grads`</b>: whether to visualize gradient histograms in TensorBoard.
  `histogram_freq` must be greater than 0.
* <b>`batch_size`</b>: size of batch of inputs to feed to the network for histograms
  computation.
* <b>`write_images`</b>: whether to write model weights to visualize as image in
  TensorBoard.
* <b>`embeddings_freq`</b>: frequency (in epochs) at which selected embedding layers
  will be saved. If set to 0, embeddings won't be computed. Data to be
  visualized in TensorBoard's Embedding tab must be passed as
  `embeddings_data`.
* <b>`embeddings_layer_names`</b>: a list of names of layers to keep eye on. If None
  or empty list all the embedding layer will be watched.
* <b>`embeddings_metadata`</b>: a dictionary which maps layer name to a file name in
  which metadata for this embedding layer is saved. See the
    [details](https://www.tensorflow.org/how_tos/embedding_viz/#metadata_optional)
      about metadata files format. In case if the same metadata file is
      used for all embedding layers, string can be passed.
* <b>`embeddings_data`</b>: data to be embedded at layers specified in
  `embeddings_layer_names`. Numpy array (if the model has a single input)
  or list of Numpy arrays (if the model has multiple inputs). Learn [more
  about
      embeddings](https://www.tensorflow.org/programmers_guide/embedding)
* <b>`update_freq`</b>: `'batch'` or `'epoch'` or integer. When using `'batch'`,
  writes the losses and metrics to TensorBoard after each batch. The same
  applies for `'epoch'`. If using an integer, let's say `1000`, the
  callback will write the metrics and losses to TensorBoard every 1000
  samples. Note that writing too frequently to TensorBoard can slow down
  your training.
* <b>`profile_batch`</b>: Profile the batch to sample compute characteristics. By
  default, it will profile the second batch. Set profile_batch=0 to
  disable profiling.


#### Raises:


* <b>`ValueError`</b>: If histogram_freq is set and no validation data is provided.



#### Eager Compatibility
Using the `TensorBoard` callback will work when eager execution is enabled,
with the restriction that outputting histogram summaries of weights and
gradients is not supported. Consequently, `histogram_freq` will be ignored.



<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/callbacks_v1.py">View source</a>

``` python
__init__(
    log_dir='./logs',
    histogram_freq=0,
    batch_size=32,
    write_graph=True,
    write_grads=False,
    write_images=False,
    embeddings_freq=0,
    embeddings_layer_names=None,
    embeddings_metadata=None,
    embeddings_data=None,
    update_freq='epoch',
    profile_batch=2
)
```

Initialize self.  See help(type(self)) for accurate signature.




## Methods

<h3 id="set_model"><code>set_model</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/callbacks_v1.py">View source</a>

``` python
set_model(model)
```

Sets Keras model and creates summary ops.


<h3 id="set_params"><code>set_params</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/callbacks.py">View source</a>

``` python
set_params(params)
```








