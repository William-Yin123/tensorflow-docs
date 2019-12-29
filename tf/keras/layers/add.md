<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.add" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.layers.add

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/merge.py">View source</a>



Functional interface to the `Add` layer.

``` python
tf.keras.layers.add(
    inputs,
    **kwargs
)
```



<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`inputs`</b>: A list of input tensors (at least 2).
* <b>`**kwargs`</b>: Standard layer keyword arguments.


#### Returns:

A tensor, the sum of the inputs.



#### Examples:



```python
    import keras

    input1 = keras.layers.Input(shape=(16,))
    x1 = keras.layers.Dense(8, activation='relu')(input1)
    input2 = keras.layers.Input(shape=(32,))
    x2 = keras.layers.Dense(8, activation='relu')(input2)
    added = keras.layers.add([x1, x2])

    out = keras.layers.Dense(4)(added)
    model = keras.models.Model(inputs=[input1, input2], outputs=out)
```

## Compat aliases

* `tf.compat.v1.keras.layers.add`
* `tf.compat.v2.keras.layers.add`

