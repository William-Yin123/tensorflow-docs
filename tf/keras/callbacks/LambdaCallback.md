<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.callbacks.LambdaCallback" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="set_model"/>
<meta itemprop="property" content="set_params"/>
</div>

# tf.keras.callbacks.LambdaCallback

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/callbacks.py">View source</a>



## Class `LambdaCallback`

Callback for creating simple, custom callbacks on-the-fly.

Inherits From: [`Callback`](../../../tf/keras/callbacks/Callback.md)

<!-- Placeholder for "Used in" -->

This callback is constructed with anonymous functions that will be called
at the appropriate time. Note that the callbacks expects positional
arguments, as:

 - `on_epoch_begin` and `on_epoch_end` expect two positional arguments:
    `epoch`, `logs`
 - `on_batch_begin` and `on_batch_end` expect two positional arguments:
    `batch`, `logs`
 - `on_train_begin` and `on_train_end` expect one positional argument:
    `logs`

#### Arguments:


* <b>`on_epoch_begin`</b>: called at the beginning of every epoch.
* <b>`on_epoch_end`</b>: called at the end of every epoch.
* <b>`on_batch_begin`</b>: called at the beginning of every batch.
* <b>`on_batch_end`</b>: called at the end of every batch.
* <b>`on_train_begin`</b>: called at the beginning of model training.
* <b>`on_train_end`</b>: called at the end of model training.


#### Example:



```python
# Print the batch number at the beginning of every batch.
batch_print_callback = LambdaCallback(
    on_batch_begin=lambda batch,logs: print(batch))

# Stream the epoch loss to a file in JSON format. The file content
# is not well-formed JSON but rather has a JSON object per line.
import json
json_log = open('loss_log.json', mode='wt', buffering=1)
json_logging_callback = LambdaCallback(
    on_epoch_end=lambda epoch, logs: json_log.write(
        json.dumps({'epoch': epoch, 'loss': logs['loss']}) + '\n'),
    on_train_end=lambda logs: json_log.close()
)

# Terminate some processes after having finished model training.
processes = ...
cleanup_callback = LambdaCallback(
    on_train_end=lambda logs: [
        p.terminate() for p in processes if p.is_alive()])

model.fit(...,
          callbacks=[batch_print_callback,
                     json_logging_callback,
                     cleanup_callback])
```

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/callbacks.py">View source</a>

``` python
__init__(
    on_epoch_begin=None,
    on_epoch_end=None,
    on_batch_begin=None,
    on_batch_end=None,
    on_train_begin=None,
    on_train_end=None,
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

* `tf.compat.v1.keras.callbacks.LambdaCallback`
* `tf.compat.v2.keras.callbacks.LambdaCallback`

