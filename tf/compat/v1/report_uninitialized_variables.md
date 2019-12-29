<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.report_uninitialized_variables" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.report_uninitialized_variables

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/variables.py">View source</a>



Adds ops to list the names of uninitialized variables.

``` python
tf.compat.v1.report_uninitialized_variables(
    var_list=None,
    name='report_uninitialized_variables'
)
```



<!-- Placeholder for "Used in" -->

When run, it returns a 1-D tensor containing the names of uninitialized
variables if there are any, or an empty array if there are none.

#### Args:


* <b>`var_list`</b>: List of `Variable` objects to check. Defaults to the value of
  `global_variables() + local_variables()`
* <b>`name`</b>: Optional name of the `Operation`.


#### Returns:

A 1-D tensor containing names of the uninitialized variables, or an empty
1-D tensor if there are no variables or no uninitialized variables.



**NOTE** The output of this function should be used.  If it is not, a warning will be logged or an error may be raised.  To mark the output as used, call its .mark_used() method.

