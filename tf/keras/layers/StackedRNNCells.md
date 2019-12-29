<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.StackedRNNCells" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="output_size"/>
<meta itemprop="property" content="state_size"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="get_initial_state"/>
</div>

# tf.keras.layers.StackedRNNCells

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/recurrent.py">View source</a>



## Class `StackedRNNCells`

Wrapper allowing a stack of RNN cells to behave as a single cell.

Inherits From: [`Layer`](../../../tf/keras/layers/Layer.md)

<!-- Placeholder for "Used in" -->

Used to implement efficient stacked RNNs.

#### Arguments:


* <b>`cells`</b>: List of RNN cell instances.


#### Examples:



```python
batch_size = 3
sentence_max_length = 5
n_features = 2
new_shape = (batch_size, sentence_max_length, n_features)
x = tf.constant(np.reshape(np.arange(30), new_shape), dtype = tf.float32)

rnn_cells = [tf.keras.layers.LSTMCell(128) for _ in range(2)]
stacked_lstm = tf.keras.layers.StackedRNNCells(rnn_cells)
lstm_layer = tf.keras.layers.RNN(stacked_lstm)

result = lstm_layer(x)
```

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/recurrent.py">View source</a>

``` python
__init__(
    cells,
    **kwargs
)
```






## Properties

<h3 id="output_size"><code>output_size</code></h3>




<h3 id="state_size"><code>state_size</code></h3>






## Methods

<h3 id="get_initial_state"><code>get_initial_state</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/recurrent.py">View source</a>

``` python
get_initial_state(
    inputs=None,
    batch_size=None,
    dtype=None
)
```








## Compat aliases

* `tf.compat.v1.keras.layers.StackedRNNCells`
* `tf.compat.v2.keras.layers.StackedRNNCells`

