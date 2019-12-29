<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.estimator.TrainSpec" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="input_fn"/>
<meta itemprop="property" content="max_steps"/>
<meta itemprop="property" content="hooks"/>
<meta itemprop="property" content="__new__"/>
</div>

# tf.estimator.TrainSpec

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">

<td>
  <a target="_blank" href="https://github.com/tensorflow/estimator/tree/master/tensorflow_estimator/python/estimator/training.py">
    <img src="https://www.tensorflow.org/images/GitHub-Mark-32px.png" />
    View source on GitHub
  </a>
</td></table>



## Class `TrainSpec`

Configuration for the "train" part for the `train_and_evaluate` call.



<!-- Placeholder for "Used in" -->

`TrainSpec` determines the input data for the training, as well as the
duration. Optional hooks run at various stages of training.

<h2 id="__new__"><code>__new__</code></h2>

<a target="_blank" href="https://github.com/tensorflow/estimator/tree/master/tensorflow_estimator/python/estimator/training.py">View source</a>

``` python
@staticmethod
__new__(
    cls,
    input_fn,
    max_steps=None,
    hooks=None
)
```

Creates a validated `TrainSpec` instance.


#### Args:


* <b>`input_fn`</b>: A function that provides input data for training as minibatches.
  See [Premade Estimators](
  https://tensorflow.org/guide/premade_estimators#create_input_functions)
  for more information. The function should construct and return one of
  the following:
    * A 'tf.data.Dataset' object: Outputs of `Dataset` object must be a
      tuple (features, labels) with same constraints as below.
    * A tuple (features, labels): Where features is a `Tensor` or a
      dictionary of string feature name to `Tensor` and labels is a
      `Tensor` or a dictionary of string label name to `Tensor`.

* <b>`max_steps`</b>: Int. Positive number of total steps for which to train model.
  If `None`, train forever. The training `input_fn` is not expected to
  generate `OutOfRangeError` or `StopIteration` exceptions. See the
  `train_and_evaluate` stop condition section for details.
* <b>`hooks`</b>: Iterable of `tf.train.SessionRunHook` objects to run
  on all workers (including chief) during training.


#### Returns:

A validated `TrainSpec` object.



#### Raises:


* <b>`ValueError`</b>: If any of the input arguments is invalid.
* <b>`TypeError`</b>: If any of the arguments is not of the expected type.



## Properties

<h3 id="input_fn"><code>input_fn</code></h3>




<h3 id="max_steps"><code>max_steps</code></h3>




<h3 id="hooks"><code>hooks</code></h3>








## Compat aliases

* `tf.compat.v1.estimator.TrainSpec`
* `tf.compat.v2.estimator.TrainSpec`

