<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.train.add_queue_runner" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.train.add_queue_runner

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/training/queue_runner_impl.py">View source</a>



Adds a `QueueRunner` to a collection in the graph. (deprecated)

``` python
tf.compat.v1.train.add_queue_runner(
    qr,
    collection=tf.GraphKeys.QUEUE_RUNNERS
)
```



<!-- Placeholder for "Used in" -->

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
To construct input pipelines, use the <a href="../../../../tf/data.md"><code>tf.data</code></a> module.

When building a complex model that uses many queues it is often difficult to
gather all the queue runners that need to be run.  This convenience function
allows you to add a queue runner to a well known collection in the graph.

The companion method `start_queue_runners()` can be used to start threads for
all the collected queue runners.

#### Args:


* <b>`qr`</b>: A `QueueRunner`.
* <b>`collection`</b>: A `GraphKey` specifying the graph collection to add
  the queue runner to.  Defaults to `GraphKeys.QUEUE_RUNNERS`.

## Compat aliases

* `tf.compat.v1.train.queue_runner.add_queue_runner`

