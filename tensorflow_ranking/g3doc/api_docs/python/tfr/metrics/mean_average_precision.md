<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tfr.metrics.mean_average_precision" />
<meta itemprop="path" content="Stable" />
</div>

# tfr.metrics.mean_average_precision

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">

<td>
  <a target="_blank" href="https://github.com/tensorflow/ranking/tree/master/tensorflow_ranking/python/metrics.py">
    <img src="https://www.tensorflow.org/images/GitHub-Mark-32px.png" />
    View source on GitHub
  </a>
</td></table>

Computes mean average precision (MAP).

```python
tfr.metrics.mean_average_precision(
    labels, predictions, weights=None, topn=None, name=None
)
```

<!-- Placeholder for "Used in" -->

The implementation of MAP is based on Equation (1.7) in the following: Liu, T-Y
"Learning to Rank for Information Retrieval" found at
https://www.nowpublishers.com/article/DownloadSummary/INR-016

#### Args:

*   <b>`labels`</b>: A `Tensor` of the same shape as `predictions`. A value >= 1
    means a relevant example.
*   <b>`predictions`</b>: A `Tensor` with shape [batch_size, list_size]. Each
    value is the ranking score of the corresponding example.
*   <b>`weights`</b>: A `Tensor` of the same shape of predictions or
    [batch_size, 1]. The former case is per-example and the latter case is
    per-list.
*   <b>`topn`</b>: A cutoff for how many examples to consider for this metric.
*   <b>`name`</b>: A string used as the name for this metric.

#### Returns:

A metric for the mean average precision.