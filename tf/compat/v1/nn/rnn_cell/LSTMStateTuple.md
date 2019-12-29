<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.nn.rnn_cell.LSTMStateTuple" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="c"/>
<meta itemprop="property" content="h"/>
<meta itemprop="property" content="dtype"/>
<meta itemprop="property" content="__new__"/>
</div>

# tf.compat.v1.nn.rnn_cell.LSTMStateTuple

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/rnn_cell_impl.py">View source</a>



## Class `LSTMStateTuple`

Tuple used by LSTM Cells for `state_size`, `zero_state`, and output state.



<!-- Placeholder for "Used in" -->

Stores two elements: `(c, h)`, in that order. Where `c` is the hidden state
and `h` is the output.

Only used when `state_is_tuple=True`.

<h2 id="__new__"><code>__new__</code></h2>

``` python
__new__(
    _cls,
    c,
    h
)
```

Create new instance of LSTMStateTuple(c, h)




## Properties

<h3 id="c"><code>c</code></h3>




<h3 id="h"><code>h</code></h3>




<h3 id="dtype"><code>dtype</code></h3>








