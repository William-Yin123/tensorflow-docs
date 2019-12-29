<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.strings.regex_full_match" />
<meta itemprop="path" content="Stable" />
</div>

# tf.strings.regex_full_match

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/string_ops.py">View source</a>



Check if the input matches the regex pattern.

``` python
tf.strings.regex_full_match(
    input,
    pattern,
    name=None
)
```



<!-- Placeholder for "Used in" -->

The input is a string tensor of any shape. The pattern is a scalar
string tensor which is applied to every element of the input tensor.
The boolean values (True or False) of the output tensor indicate
if the input matches the regex pattern provided.

The pattern follows the re2 syntax (https://github.com/google/re2/wiki/Syntax)

#### Examples:


>>> tf.strings.regex_full_match(["TensorFlow library", "Hello world"], ".*library$")
<tf.Tensor: id=322, shape=(2,), dtype=bool, numpy=array([ True, False])>
>>> tf.strings.regex_full_match(["TensorFlow library", "The library is called TensorFlow"], ".*library$")
<tf.Tensor: id=324, shape=(2,), dtype=bool, numpy=array([ True, False])>

#### Args:


* <b>`input`</b>: A `Tensor` of type `string`.
  A string tensor of the text to be processed.
* <b>`pattern`</b>: A `Tensor` of type `string`.
  A scalar string tensor containing the regular expression to match the input.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `bool`.


## Compat aliases

* `tf.compat.v1.strings.regex_full_match`
* `tf.compat.v2.strings.regex_full_match`

