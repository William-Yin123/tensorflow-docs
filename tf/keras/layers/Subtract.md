<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.Subtract" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.keras.layers.Subtract

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/merge.py">View source</a>



## Class `Subtract`

Layer that subtracts two inputs.



<!-- Placeholder for "Used in" -->

It takes as input a list of tensors of size 2,
both of the same shape, and returns a single tensor, (inputs[0] - inputs[1]),
also of the same shape.

#### Examples:



```python
    import keras

    input1 = keras.layers.Input(shape=(16,))
    x1 = keras.layers.Dense(8, activation='relu')(input1)
    input2 = keras.layers.Input(shape=(32,))
    x2 = keras.layers.Dense(8, activation='relu')(input2)
    # Equivalent to subtracted = keras.layers.subtract([x1, x2])
    subtracted = keras.layers.Subtract()([x1, x2])

    out = keras.layers.Dense(4)(subtracted)
    model = keras.models.Model(inputs=[input1, input2], outputs=out)
```

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/merge.py">View source</a>

``` python
__init__(**kwargs)
```








## Compat aliases

* `tf.compat.v1.keras.layers.Subtract`
* `tf.compat.v2.keras.layers.Subtract`

