<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.callbacks.ProgbarLogger" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="set_model"/>
<meta itemprop="property" content="set_params"/>
</div>

# tf.keras.callbacks.ProgbarLogger

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/callbacks.py">View source</a>



## Class `ProgbarLogger`

Callback that prints metrics to stdout.

Inherits From: [`Callback`](../../../tf/keras/callbacks/Callback.md)

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`count_mode`</b>: One of "steps" or "samples".
    Whether the progress bar should
    count samples seen or steps (batches) seen.
* <b>`stateful_metrics`</b>: Iterable of string names of metrics that
    should *not* be averaged over an epoch.
    Metrics in this list will be logged as-is.
    All others will be averaged over time (e.g. loss, etc).


#### Raises:


* <b>`ValueError`</b>: In case of invalid `count_mode`.

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/callbacks.py">View source</a>

``` python
__init__(
    count_mode='samples',
    stateful_metrics=None
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

* `tf.compat.v1.keras.callbacks.ProgbarLogger`
* `tf.compat.v2.keras.callbacks.ProgbarLogger`

