<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.strings.reduce_join" />
<meta itemprop="path" content="Stable" />
</div>

# tf.strings.reduce_join

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/string_ops.py">View source</a>



Joins all strings into a single string, or joins along an axis.

``` python
tf.strings.reduce_join(
    inputs,
    axis=None,
    keepdims=False,
    separator='',
    name=None
)
```



<!-- Placeholder for "Used in" -->

```
>>> tf.strings.reduce_join([['abc','123'],
...                         ['def','456']]).numpy()
b'abc123def456'
>>> tf.strings.reduce_join([['abc','123'],
...                         ['def','456']], axis=-1).numpy()
array([b'abc123', b'def456'], dtype=object)
>>> tf.strings.reduce_join([['abc','123'],
...                         ['def','456']],
...                        axis=-1,
...                        separator=" ").numpy()
array([b'abc 123', b'def 456'], dtype=object)
```

#### Args:


* <b>`inputs`</b>: A <a href="../../tf.md#string"><code>tf.string</code></a> tensor.
* <b>`axis`</b>: Which axis to join along. The default behavior is to join all
  elements, producing a scalar.
* <b>`keepdims`</b>: If true, retains reduced dimensions with length 1.
* <b>`separator`</b>: a string added between each string being joined.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A <a href="../../tf.md#string"><code>tf.string</code></a> tensor.


## Compat aliases

* `tf.compat.v2.strings.reduce_join`

