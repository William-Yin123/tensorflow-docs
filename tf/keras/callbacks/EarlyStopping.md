<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.callbacks.EarlyStopping" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="get_monitor_value"/>
<meta itemprop="property" content="set_model"/>
<meta itemprop="property" content="set_params"/>
</div>

# tf.keras.callbacks.EarlyStopping

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/callbacks.py">View source</a>



## Class `EarlyStopping`

Stop training when a monitored quantity has stopped improving.

Inherits From: [`Callback`](../../../tf/keras/callbacks/Callback.md)

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`monitor`</b>: Quantity to be monitored.
* <b>`min_delta`</b>: Minimum change in the monitored quantity
    to qualify as an improvement, i.e. an absolute
    change of less than min_delta, will count as no
    improvement.
* <b>`patience`</b>: Number of epochs with no improvement
    after which training will be stopped.
* <b>`verbose`</b>: verbosity mode.
* <b>`mode`</b>: One of `{"auto", "min", "max"}`. In `min` mode,
    training will stop when the quantity
    monitored has stopped decreasing; in `max`
    mode it will stop when the quantity
    monitored has stopped increasing; in `auto`
    mode, the direction is automatically inferred
    from the name of the monitored quantity.
* <b>`baseline`</b>: Baseline value for the monitored quantity.
    Training will stop if the model doesn't show improvement over the
    baseline.
* <b>`restore_best_weights`</b>: Whether to restore model weights from
    the epoch with the best value of the monitored quantity.
    If False, the model weights obtained at the last step of
    training are used.


#### Example:



```python
callback = tf.keras.callbacks.EarlyStopping(monitor='val_loss', patience=3)
# This callback will stop the training when there is no improvement in
# the validation loss for three consecutive epochs.
model.fit(data, labels, epochs=100, callbacks=[callback],
    validation_data=(val_data, val_labels))
```

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/callbacks.py">View source</a>

``` python
__init__(
    monitor='val_loss',
    min_delta=0,
    patience=0,
    verbose=0,
    mode='auto',
    baseline=None,
    restore_best_weights=False
)
```

Initialize self.  See help(type(self)) for accurate signature.




## Methods

<h3 id="get_monitor_value"><code>get_monitor_value</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/callbacks.py">View source</a>

``` python
get_monitor_value(logs)
```




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

* `tf.compat.v1.keras.callbacks.EarlyStopping`
* `tf.compat.v2.keras.callbacks.EarlyStopping`

