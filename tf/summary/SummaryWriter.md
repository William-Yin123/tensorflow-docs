<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.summary.SummaryWriter" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="as_default"/>
<meta itemprop="property" content="close"/>
<meta itemprop="property" content="flush"/>
<meta itemprop="property" content="init"/>
<meta itemprop="property" content="set_as_default"/>
</div>

# tf.summary.SummaryWriter

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/summary_ops_v2.py">View source</a>



## Class `SummaryWriter`

Interface representing a stateful summary writer object.



<!-- Placeholder for "Used in" -->


## Methods

<h3 id="as_default"><code>as_default</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/summary_ops_v2.py">View source</a>

``` python
as_default()
```

Returns a context manager that enables summary writing.


<h3 id="close"><code>close</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/summary_ops_v2.py">View source</a>

``` python
close()
```

Flushes and closes the summary writer.


<h3 id="flush"><code>flush</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/summary_ops_v2.py">View source</a>

``` python
flush()
```

Flushes any buffered data.


<h3 id="init"><code>init</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/summary_ops_v2.py">View source</a>

``` python
init()
```

Initializes the summary writer.


<h3 id="set_as_default"><code>set_as_default</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/ops/summary_ops_v2.py">View source</a>

``` python
set_as_default()
```

Enables this summary writer for the current thread.






## Compat aliases

* `tf.compat.v2.summary.SummaryWriter`

