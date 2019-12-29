<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.callbacks.LearningRateScheduler" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="set_model"/>
<meta itemprop="property" content="set_params"/>
</div>

# tf.keras.callbacks.LearningRateScheduler

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/callbacks.py">View source</a>



## Class `LearningRateScheduler`

Learning rate scheduler.

Inherits From: [`Callback`](../../../tf/keras/callbacks/Callback.md)

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`schedule`</b>: a function that takes an epoch index as input
    (integer, indexed from 0) and returns a new
    learning rate as output (float).
* <b>`verbose`</b>: int. 0: quiet, 1: update messages.

```python
# This function keeps the learning rate at 0.001 for the first ten epochs
# and decreases it exponentially after that.
def scheduler(epoch):
  if epoch < 10:
    return 0.001
  else:
    return 0.001 * tf.math.exp(0.1 * (10 - epoch))

callback = tf.keras.callbacks.LearningRateScheduler(scheduler)
model.fit(data, labels, epochs=100, callbacks=[callback],
          validation_data=(val_data, val_labels))
```

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/callbacks.py">View source</a>

``` python
__init__(
    schedule,
    verbose=0
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

* `tf.compat.v1.keras.callbacks.LearningRateScheduler`
* `tf.compat.v2.keras.callbacks.LearningRateScheduler`

