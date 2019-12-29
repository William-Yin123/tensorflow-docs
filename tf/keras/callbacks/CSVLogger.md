<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.callbacks.CSVLogger" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="set_model"/>
<meta itemprop="property" content="set_params"/>
</div>

# tf.keras.callbacks.CSVLogger

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/callbacks.py">View source</a>



## Class `CSVLogger`

Callback that streams epoch results to a csv file.

Inherits From: [`Callback`](../../../tf/keras/callbacks/Callback.md)

<!-- Placeholder for "Used in" -->

Supports all values that can be represented as a string,
including 1D iterables such as np.ndarray.

#### Example:



```python
csv_logger = CSVLogger('training.log')
model.fit(X_train, Y_train, callbacks=[csv_logger])
```

#### Arguments:


* <b>`filename`</b>: filename of the csv file, e.g. 'run/log.csv'.
* <b>`separator`</b>: string used to separate elements in the csv file.
* <b>`append`</b>: True: append if file exists (useful for continuing
    training). False: overwrite existing file,

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/callbacks.py">View source</a>

``` python
__init__(
    filename,
    separator=',',
    append=False
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

* `tf.compat.v1.keras.callbacks.CSVLogger`
* `tf.compat.v2.keras.callbacks.CSVLogger`

