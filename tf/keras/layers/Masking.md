<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.Masking" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
</div>

# tf.keras.layers.Masking

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/core.py">View source</a>



## Class `Masking`

Masks a sequence by using a mask value to skip timesteps.

Inherits From: [`Layer`](../../../tf/keras/layers/Layer.md)

<!-- Placeholder for "Used in" -->

For each timestep in the input tensor (dimension #1 in the tensor),
if all values in the input tensor at that timestep
are equal to `mask_value`, then the timestep will be masked (skipped)
in all downstream layers (as long as they support masking).

If any downstream layer does not support masking yet receives such
an input mask, an exception will be raised.

#### Example:



Consider a Numpy data array `x` of shape `(samples, timesteps, features)`,
to be fed to an LSTM layer. You want to mask timestep #3 and #5 because you
lack data for these timesteps. You can:

- Set `x[:, 3, :] = 0.` and `x[:, 5, :] = 0.`
- Insert a `Masking` layer with `mask_value=0.` before the LSTM layer:

```python
samples, timesteps, features = 32, 10, 8
inputs = np.random.random([samples, timesteps, features]).astype(np.float32)
inputs[:, 3, :] = 0.
inputs[:, 5, :] = 0.

model = tf.keras.models.Sequential()
model.add(tf.keras.layers.Masking(mask_value=0.,
                                  input_shape=(timesteps, features)))
model.add(tf.keras.layers.LSTM(32))

output = model(inputs)
# The time step 3 and 5 will be skipped from LSTM calculation.
```

See [the masking and padding
guide](https://www.tensorflow.org/guide/keras/masking_and_padding)
for more details.

<h2 id="__init__"><code>__init__</code></h2>

<a target="_blank" href="/code/stable/tensorflow/python/keras/layers/core.py">View source</a>

``` python
__init__(
    mask_value=0.0,
    **kwargs
)
```








## Compat aliases

* `tf.compat.v1.keras.layers.Masking`
* `tf.compat.v2.keras.layers.Masking`

