<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.train.global_step" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.train.global_step

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/training/training_util.py">View source</a>



Small helper to get the global step.

``` python
tf.compat.v1.train.global_step(
    sess,
    global_step_tensor
)
```



<!-- Placeholder for "Used in" -->

```python
# Create a variable to hold the global_step.
global_step_tensor = tf.Variable(10, trainable=False, name='global_step')
# Create a session.
sess = tf.compat.v1.Session()
# Initialize the variable
sess.run(global_step_tensor.initializer)
# Get the variable value.
print('global_step: %s' % tf.compat.v1.train.global_step(sess,
global_step_tensor))

global_step: 10
```

#### Args:


* <b>`sess`</b>: A TensorFlow `Session` object.
* <b>`global_step_tensor`</b>:  `Tensor` or the `name` of the operation that contains
  the global step.


#### Returns:

The global step value.


