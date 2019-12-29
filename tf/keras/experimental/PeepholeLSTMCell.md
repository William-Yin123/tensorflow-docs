<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.experimental.PeepholeLSTMCell" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.experimental.PeepholeLSTMCell

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/recurrent.py">View source</a>



## Class `PeepholeLSTMCell`

Equivalent to LSTMCell class but adds peephole connections.

Inherits From: [`LSTMCell`](../../../tf/compat/v1/keras/layers/LSTMCell.md)

<!-- Placeholder for "Used in" -->

Peephole connections allow the gates to utilize the previous internal state as
well as the previous hidden state (which is what LSTMCell is limited to).
This allows PeepholeLSTMCell to better learn precise timings over LSTMCell.

From [Gers et al.](http://www.jmlr.org/papers/volume3/gers02a/gers02a.pdf):

"We find that LSTM augmented by 'peephole connections' from its internal
cells to its multiplicative gates can learn the fine distinction between
sequences of spikes spaced either 50 or 49 time steps apart without the help
of any short training exemplars."

The peephole implementation is based on:

[Long short-term memory recurrent neural network architectures for
 large scale acoustic modeling.
](https://research.google.com/pubs/archive/43905.pdf)

#### Example:



```python
# Create 2 PeepholeLSTMCells
peephole_lstm_cells = [PeepholeLSTMCell(size) for size in [128, 256]]
# Create a layer composed sequentially of the peephole LSTM cells.
layer = RNN(peephole_lstm_cells)
input = keras.Input((timesteps, input_dim))
output = layer(input)
```



## Compat aliases

* `tf.compat.v1.keras.experimental.PeepholeLSTMCell`
* `tf.compat.v2.keras.experimental.PeepholeLSTMCell`

