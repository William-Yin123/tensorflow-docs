<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.optimizers.schedules.LearningRateSchedule" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="from_config"/>
<meta itemprop="property" content="get_config"/>
</div>

# tf.keras.optimizers.schedules.LearningRateSchedule

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/optimizer_v2/learning_rate_schedule.py">View source</a>



## Class `LearningRateSchedule`

A serializable learning rate decay schedule.



**Aliases**: `tf.optimizers.schedules.LearningRateSchedule`

<!-- Placeholder for "Used in" -->

`LearningRateSchedule`s can be passed in as the learning rate of optimizers in
<a href="../../../../tf/keras/optimizers.md"><code>tf.keras.optimizers</code></a>. They can be serialized and deserialized using
<a href="../../../../tf/keras/optimizers/schedules/serialize.md"><code>tf.keras.optimizers.schedules.serialize</code></a> and
<a href="../../../../tf/keras/optimizers/schedules/deserialize.md"><code>tf.keras.optimizers.schedules.deserialize</code></a>.

## Methods

<h3 id="__call__"><code>__call__</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/optimizer_v2/learning_rate_schedule.py">View source</a>

``` python
__call__(step)
```

Call self as a function.


<h3 id="from_config"><code>from_config</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/optimizer_v2/learning_rate_schedule.py">View source</a>

``` python
@classmethod
from_config(
    cls,
    config
)
```

Instantiates a `LearningRateSchedule` from its config.


#### Args:


* <b>`config`</b>: Output of `get_config()`.


#### Returns:

A `LearningRateSchedule` instance.


<h3 id="get_config"><code>get_config</code></h3>

<a target="_blank" href="/code/stable/tensorflow/python/keras/optimizer_v2/learning_rate_schedule.py">View source</a>

``` python
get_config()
```








## Compat aliases

* `tf.compat.v1.keras.optimizers.schedules.LearningRateSchedule`
* `tf.compat.v2.keras.optimizers.schedules.LearningRateSchedule`
* `tf.compat.v2.optimizers.schedules.LearningRateSchedule`

