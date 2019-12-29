<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.get_uid" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.get_uid

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/backend.py">View source</a>



Associates a string prefix with an integer counter in a TensorFlow graph.

``` python
tf.keras.backend.get_uid(prefix='')
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`prefix`</b>: String prefix to index.


#### Returns:

Unique integer ID.



#### Example:



```
>>> get_uid('dense')
1
>>> get_uid('dense')
2
```

## Compat aliases

* `tf.compat.v1.keras.backend.get_uid`
* `tf.compat.v2.keras.backend.get_uid`

