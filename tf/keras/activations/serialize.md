<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.activations.serialize" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.activations.serialize

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/activations.py">View source</a>



Returns name attribute (`__name__`) of function.

``` python
tf.keras.activations.serialize(activation)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`activation`</b>: Function


#### Returns:

String denoting the name attribute of the input function



#### For example:



```
>>> tf.keras.activations.serialize(tf.keras.activations.tanh)
'tanh'
>>> tf.keras.activations.serialize(tf.keras.activations.sigmoid)
'sigmoid'
>>> tf.keras.activations.serialize('abcd')
Traceback (most recent call last):
...
ValueError: ('Cannot serialize', 'abcd')
```

#### Raises:


* <b>`ValueError`</b>: The input function is not a valid one.

## Compat aliases

* `tf.compat.v1.keras.activations.serialize`
* `tf.compat.v2.keras.activations.serialize`

