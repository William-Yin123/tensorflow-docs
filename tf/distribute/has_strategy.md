<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.distribute.has_strategy" />
<meta itemprop="path" content="Stable" />
</div>

# tf.distribute.has_strategy

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/distribute/distribution_strategy_context.py">View source</a>



Return if there is a current non-default <a href="../../tf/distribute/Strategy.md"><code>tf.distribute.Strategy</code></a>.

``` python
tf.distribute.has_strategy()
```



<!-- Placeholder for "Used in" -->

```
assert not tf.distribute.has_strategy()
with strategy.scope():
  assert tf.distribute.has_strategy()
```

#### Returns:

True if inside a `with strategy.scope():`.


## Compat aliases

* `tf.compat.v1.distribute.has_strategy`
* `tf.compat.v2.distribute.has_strategy`

