<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.nn.rnn_cell.DeviceWrapper" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="graph"/>
<meta itemprop="property" content="output_size"/>
<meta itemprop="property" content="scope_name"/>
<meta itemprop="property" content="state_size"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="get_initial_state"/>
<meta itemprop="property" content="zero_state"/>
</div>

# tf.compat.v1.nn.rnn_cell.DeviceWrapper

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/rnn_cell_impl.py">View source</a>



## Class `DeviceWrapper`

Operator that ensures an RNNCell runs on a particular device.



<!-- Placeholder for "Used in" -->


<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/ops/rnn_cell_impl.py">View source</a>

``` python
__init__(
    *args,
    **kwargs
)
```

Construct a `DeviceWrapper` for `cell` with device `device`.

Ensures the wrapped `cell` is called with <a href="../../../../../tf/device.md"><code>tf.device(device)</code></a>.

#### Args:


* <b>`cell`</b>: An instance of `RNNCell`.
* <b>`device`</b>: A device string or function, for passing to <a href="../../../../../tf/device.md"><code>tf.device</code></a>.
* <b>`**kwargs`</b>: dict of keyword arguments for base layer.



## Properties

<h3 id="graph"><code>graph</code></h3>

DEPRECATED FUNCTION

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Stop using this property because tf.layers layers no longer track their graph.

<h3 id="output_size"><code>output_size</code></h3>




<h3 id="scope_name"><code>scope_name</code></h3>




<h3 id="state_size"><code>state_size</code></h3>






## Methods

<h3 id="get_initial_state"><code>get_initial_state</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/rnn_cell_impl.py">View source</a>

``` python
get_initial_state(
    inputs=None,
    batch_size=None,
    dtype=None
)
```




<h3 id="zero_state"><code>zero_state</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/rnn_cell_wrapper_impl.py">View source</a>

``` python
zero_state(
    batch_size,
    dtype
)
```








