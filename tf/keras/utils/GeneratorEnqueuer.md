<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.utils.GeneratorEnqueuer" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="get"/>
<meta itemprop="property" content="is_running"/>
<meta itemprop="property" content="start"/>
<meta itemprop="property" content="stop"/>
</div>

# tf.keras.utils.GeneratorEnqueuer

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/utils/data_utils.py">View source</a>



## Class `GeneratorEnqueuer`

Builds a queue out of a data generator.

Inherits From: [`SequenceEnqueuer`](../../../tf/keras/utils/SequenceEnqueuer.md)

<!-- Placeholder for "Used in" -->

The provided generator can be finite in which case the class will throw
a `StopIteration` exception.

Used in `fit_generator`, `evaluate_generator`, `predict_generator`.

#### Arguments:


* <b>`generator`</b>: a generator function which yields data
* <b>`use_multiprocessing`</b>: use multiprocessing if True, otherwise threading
* <b>`wait_time`</b>: time to sleep in-between calls to `put()`
* <b>`random_seed`</b>: Initial seed for workers,
    will be incremented by one for each worker.

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/utils/data_utils.py">View source</a>

``` python
__init__(
    sequence,
    use_multiprocessing=False,
    random_seed=None
)
```

Initialize self.  See help(type(self)) for accurate signature.




## Methods

<h3 id="get"><code>get</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/utils/data_utils.py">View source</a>

``` python
get()
```

Creates a generator to extract data from the queue.

Skip the data if it is `None`.

#### Yields:

The next element in the queue, i.e. a tuple
`(inputs, targets)` or
`(inputs, targets, sample_weights)`.


<h3 id="is_running"><code>is_running</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/utils/data_utils.py">View source</a>

``` python
is_running()
```




<h3 id="start"><code>start</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/utils/data_utils.py">View source</a>

``` python
start(
    workers=1,
    max_queue_size=10
)
```

Starts the handler's workers.


#### Arguments:


* <b>`workers`</b>: Number of workers.
* <b>`max_queue_size`</b>: queue size
    (when full, workers could block on `put()`)

<h3 id="stop"><code>stop</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/utils/data_utils.py">View source</a>

``` python
stop(timeout=None)
```

Stops running threads and wait for them to exit, if necessary.

Should be called by the same thread which called `start()`.

#### Arguments:


* <b>`timeout`</b>: maximum time to wait on `thread.join()`





## Compat aliases

* `tf.compat.v1.keras.utils.GeneratorEnqueuer`
* `tf.compat.v2.keras.utils.GeneratorEnqueuer`

