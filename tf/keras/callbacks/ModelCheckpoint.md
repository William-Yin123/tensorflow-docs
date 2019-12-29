<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.callbacks.ModelCheckpoint" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="set_model"/>
<meta itemprop="property" content="set_params"/>
</div>

# tf.keras.callbacks.ModelCheckpoint

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/callbacks.py">View source</a>



## Class `ModelCheckpoint`

Callback to save the Keras model or model weights at some frequency.

Inherits From: [`Callback`](../../../tf/keras/callbacks/Callback.md)

<!-- Placeholder for "Used in" -->

`ModelCheckpoint` callback is used in conjunction with training using
`model.fit()` to save a model or weights (in a checkpoint file) at some
interval, so the model or weights can be loaded later to continue the training
from the state saved.

A few options this callback provides include:

- Whether to only keep the model that has achieved the "best performance" so
  far, or whether to save the model at the end of every epoch regardless of
  performance.
- Definition of 'best'; which quantity to monitor and whether it should be
  maximized or minimized.
- The frequency it should save at. Currently, the callback supports saving at
  the end of every epoch, or after a fixed number of training samples.
- Whether only weights are saved, or the whole model is saved.

#### Example:



```python
EPOCHS = 10
checkpoint_filepath = '/tmp/checkpoint'
model_checkpoint_callback = tf.keras.callbacks.ModelCheckpoint(
    filepath=checkpoint_filepath,
    save_weights_only=True,
    monitor='val_acc',
    mode='max',
    save_best_only=True)

# Model weights are saved at the end of every epoch, if it's the best seen
# so far.
model.fit(epochs=EPOCHS, callbacks=[model_checkpoint_callback])

# The model weights (that are considered the best) are loaded into the model.
model.load_weights(checkpoint_filepath)
```

#### Arguments:


* <b>`filepath`</b>: string, path to save the model file. `filepath` can contain
  named formatting options, which will be filled the value of `epoch` and
  keys in `logs` (passed in `on_epoch_end`). For example: if `filepath` is
  `weights.{epoch:02d}-{val_loss:.2f}.hdf5`, then the model checkpoints
  will be saved with the epoch number and the validation loss in the
  filename.
* <b>`monitor`</b>: quantity to monitor.
* <b>`verbose`</b>: verbosity mode, 0 or 1.
* <b>`save_best_only`</b>: if `save_best_only=True`, the latest best model according
  to the quantity monitored will not be overwritten.
  If `filepath` doesn't contain formatting options like `{epoch}` then
  `filepath` will be overwritten by each new better model.
* <b>`mode`</b>: one of {auto, min, max}. If `save_best_only=True`, the decision to
  overwrite the current save file is made based on either the maximization
  or the minimization of the monitored quantity. For `val_acc`, this
  should be `max`, for `val_loss` this should be `min`, etc. In `auto`
  mode, the direction is automatically inferred from the name of the
  monitored quantity.
* <b>`save_weights_only`</b>: if True, then only the model's weights will be saved
  (`model.save_weights(filepath)`), else the full model is saved
  (`model.save(filepath)`).
* <b>`save_freq`</b>: `'epoch'` or integer. When using `'epoch'`, the callback saves
  the model after each epoch. When using integer, the callback saves the
  model at end of a batch at which this many samples have been seen since
  last saving. Note that if the saving isn't aligned to epochs, the
  monitored metric may potentially be less reliable (it could reflect as
  little as 1 batch, since the metrics get reset every epoch). Defaults to
  `'epoch'`
* <b>`**kwargs`</b>: Additional arguments for backwards compatibility. Possible key
  is `period`.

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/callbacks.py">View source</a>

``` python
__init__(
    filepath,
    monitor='val_loss',
    verbose=0,
    save_best_only=False,
    save_weights_only=False,
    mode='auto',
    save_freq='epoch',
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




<h3 id="set_params"><code>set_params</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/callbacks.py">View source</a>

``` python
set_params(params)
```








## Compat aliases

* `tf.compat.v1.keras.callbacks.ModelCheckpoint`
* `tf.compat.v2.keras.callbacks.ModelCheckpoint`

