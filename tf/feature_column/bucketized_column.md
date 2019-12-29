<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.feature_column.bucketized_column" />
<meta itemprop="path" content="Stable" />
</div>

# tf.feature_column.bucketized_column

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/feature_column/feature_column_v2.py">View source</a>



Represents discretized dense input bucketed by `boundaries`.

``` python
tf.feature_column.bucketized_column(
    source_column,
    boundaries
)
```



<!-- Placeholder for "Used in" -->

Buckets include the left boundary, and exclude the right boundary. Namely,
`boundaries=[0., 1., 2.]` generates buckets `(-inf, 0.)`, `[0., 1.)`,
`[1., 2.)`, and `[2., +inf)`.

For example, if the inputs are

```python
boundaries = [0, 10, 100]
input tensor = [[-5, 10000]
                [150,   10]
                [5,    100]]
```

then the output will be

```python
output = [[0, 3]
          [3, 2]
          [1, 3]]
```

#### Example:



```python
price = tf.feature_column.numeric_column('price')
bucketized_price = tf.feature_column.bucketized_column(
    price, boundaries=[...])
columns = [bucketized_price, ...]
features = tf.io.parse_example(
    ..., features=tf.feature_column.make_parse_example_spec(columns))
dense_tensor = tf.keras.layers.DenseFeatures(columns)(features)

`bucketized_column` can also be crossed with another categorical column using
`crossed_column`:

```python
price = tf.feature_column.numeric_column('price')
# bucketized_column converts numerical feature to a categorical one.
bucketized_price = tf.feature_column.bucketized_column(
    price, boundaries=[...])
# 'keywords' is a string feature.
price_x_keywords = tf.feature_column.crossed_column(
    [bucketized_price, 'keywords'], 50K)
columns = [price_x_keywords, ...]
features = tf.io.parse_example(
    ..., features=tf.feature_column.make_parse_example_spec(columns))
dense_tensor = tf.keras.layers.DenseFeatures(columns)(features)
linear_model = tf.keras.experimental.LinearModel(units=...)(dense_tensor)
```

#### Args:


* <b>`source_column`</b>: A one-dimensional dense column which is generated with
  `numeric_column`.
* <b>`boundaries`</b>: A sorted list or tuple of floats specifying the boundaries.


#### Returns:

A `BucketizedColumn`.



#### Raises:


* <b>`ValueError`</b>: If `source_column` is not a numeric column, or if it is not
  one-dimensional.
* <b>`ValueError`</b>: If `boundaries` is not a sorted list or tuple.

## Compat aliases

* `tf.compat.v1.feature_column.bucketized_column`
* `tf.compat.v2.feature_column.bucketized_column`

