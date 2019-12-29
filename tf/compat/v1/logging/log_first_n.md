<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.logging.log_first_n" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.logging.log_first_n

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/platform/tf_logging.py">View source</a>



Log 'msg % args' at level 'level' only first 'n' times.

``` python
tf.compat.v1.logging.log_first_n(
    level,
    msg,
    n,
    *args
)
```



<!-- Placeholder for "Used in" -->

Not threadsafe.

#### Args:


* <b>`level`</b>: The level at which to log.
* <b>`msg`</b>: The message to be logged.
* <b>`n`</b>: The number of times this should be called before it is logged.
* <b>`*args`</b>: The args to be substituted into the msg.

