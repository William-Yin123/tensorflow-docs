<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.flags.tf_decorator.tf_stack" />
<meta itemprop="path" content="Stable" />
</div>

# Module: tf.compat.v1.flags.tf_decorator.tf_stack


<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/util/tf_stack.py">View source</a>



Functions used to extract and analyze stacks.  Faster than Python libs.



## Classes

[`class CurrentModuleFilter`](../../../../../tf/compat/v1/flags/tf_decorator/tf_stack/CurrentModuleFilter.md): Filters stack frames from the module where this is used (best effort).

[`class FrameSummary`](../../../../../tf/compat/v1/flags/tf_decorator/tf_stack/FrameSummary.md)

[`class StackSummary`](../../../../../tf/compat/v1/flags/tf_decorator/tf_stack/StackSummary.md)

[`class StackTraceFilter`](../../../../../tf/compat/v1/flags/tf_decorator/tf_stack/StackTraceFilter.md): Allows filtering traceback information by removing superfluous frames.

[`class StackTraceMapper`](../../../../../tf/compat/v1/flags/tf_decorator/tf_stack/StackTraceMapper.md): Allows remapping traceback information to different source code.

[`class StackTraceTransform`](../../../../../tf/compat/v1/flags/tf_decorator/tf_stack/StackTraceTransform.md): Base class for stack trace transformation functions.

## Functions

[`extract_stack(...)`](../../../../../tf/compat/v1/flags/tf_decorator/tf_stack/extract_stack.md): A lightweight, extensible re-implementation of traceback.extract_stack.



## Compat aliases

* `tf.compat.v1.app.flags.tf_decorator.tf_stack`

