<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.estimator.experimental.linear_logit_fn_builder" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.estimator.experimental.linear_logit_fn_builder

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">

<td>
  <a target="_blank" href="https://github.com/tensorflow/estimator/tree/master/tensorflow_estimator/python/estimator/canned/linear.py">
    <img src="https://www.tensorflow.org/images/GitHub-Mark-32px.png" />
    View source on GitHub
  </a>
</td></table>



Function builder for a linear logit_fn.

``` python
tf.compat.v1.estimator.experimental.linear_logit_fn_builder(
    units,
    feature_columns,
    sparse_combiner='sum'
)
```



<!-- Placeholder for "Used in" -->


#### Args:


* <b>`units`</b>: An int indicating the dimension of the logit layer.
* <b>`feature_columns`</b>: An iterable containing all the feature columns used by
  the model.
* <b>`sparse_combiner`</b>: A string specifying how to reduce if a categorical column
  is multivalent.  One of "mean", "sqrtn", and "sum".


#### Returns:

A logit_fn (see below).


