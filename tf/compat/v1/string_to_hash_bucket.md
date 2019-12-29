<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.string_to_hash_bucket" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.string_to_hash_bucket

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/string_ops.py">View source</a>



Converts each string in the input Tensor to its hash mod by a number of buckets.

``` python
tf.compat.v1.string_to_hash_bucket(
    string_tensor=None,
    num_buckets=None,
    name=None,
    input=None
)
```



<!-- Placeholder for "Used in" -->

The hash function is deterministic on the content of the string within the
process.

Note that the hash function may change from time to time.
This functionality will be deprecated and it's recommended to use
`tf.string_to_hash_bucket_fast()` or `tf.string_to_hash_bucket_strong()`.

#### Args:


* <b>`string_tensor`</b>: A `Tensor` of type `string`.
* <b>`num_buckets`</b>: An `int` that is `>= 1`. The number of buckets.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `int64`.


## Compat aliases

* `tf.compat.v1.strings.to_hash_bucket`

