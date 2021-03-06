<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.estimator.SessionRunArgs" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="fetches"/>
<meta itemprop="property" content="feed_dict"/>
<meta itemprop="property" content="options"/>
<meta itemprop="property" content="__new__"/>
</div>

# tf.estimator.SessionRunArgs

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/training/session_run_hook.py">View source</a>



## Class `SessionRunArgs`

Represents arguments to be added to a `Session.run()` call.



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`fetches`</b>: Exactly like the 'fetches' argument to Session.Run().
  Can be a single tensor or op, a list of 'fetches' or a dictionary
  of fetches.  For example:
    fetches = global_step_tensor
    fetches = [train_op, summary_op, global_step_tensor]
    fetches = {'step': global_step_tensor, 'summ': summary_op}
  Note that this can recurse as expected:
    fetches = {'step': global_step_tensor,
               'ops': [train_op, check_nan_op]}
* <b>`feed_dict`</b>: Exactly like the `feed_dict` argument to `Session.Run()`
* <b>`options`</b>: Exactly like the `options` argument to `Session.run()`, i.e., a
  config_pb2.RunOptions proto.

<h2 id="__new__"><code>__new__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/training/session_run_hook.py">View source</a>

``` python
@staticmethod
__new__(
    cls,
    fetches,
    feed_dict=None,
    options=None
)
```

Create new instance of SessionRunArgs(fetches, feed_dict, options)




## Properties

<h3 id="fetches"><code>fetches</code></h3>




<h3 id="feed_dict"><code>feed_dict</code></h3>




<h3 id="options"><code>options</code></h3>








## Compat aliases

* `tf.compat.v1.estimator.SessionRunArgs`
* `tf.compat.v1.train.SessionRunArgs`
* `tf.compat.v2.estimator.SessionRunArgs`

