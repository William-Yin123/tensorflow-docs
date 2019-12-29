<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image.generate_bounding_box_proposals" />
<meta itemprop="path" content="Stable" />
</div>

# tf.image.generate_bounding_box_proposals

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="/code/stable/tensorflow/python/ops/image_ops_impl.py">View source</a>



Generate bounding box proposals from encoded bounding boxes.

``` python
tf.image.generate_bounding_box_proposals(
    scores,
    bbox_deltas,
    image_info,
    anchors,
    nms_threshold=0.7,
    pre_nms_topn=6000,
    min_size=16,
    post_nms_topn=300,
    name=None
)
```



<!-- Placeholder for "Used in" -->


#### Returns:


* <b>`rois`</b>: Region of interest boxes sorted by their scores.
* <b>`roi_probabilities`</b>: scores of the ROI boxes in the ROIs' tensor.

## Compat aliases

* `tf.compat.v1.image.generate_bounding_box_proposals`
* `tf.compat.v2.image.generate_bounding_box_proposals`

