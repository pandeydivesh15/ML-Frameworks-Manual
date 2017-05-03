# tf.concat

```python
concat(
    values,
    axis,
    name='concat'
)
```

## Args:

values: A list of Tensor objects or a single Tensor.
axis: 0-D int32 Tensor. Dimension along which to concatenate.
name: A name for the operation (optional).

## Returns:

A Tensor resulting from concatenation of the input tensors.

## Examples

```
t1 = [[1, 2, 3], [4, 5, 6]]
t2 = [[7, 8, 9], [10, 11, 12]]
tf.concat([t1, t2], 0) ==> [[1, 2, 3], [4, 5, 6], [7, 8, 9], [10, 11, 12]]
tf.concat([t1, t2], 1) ==> [[1, 2, 3, 7, 8, 9], [4, 5, 6, 10, 11, 12]]

# tensor t3 with shape [2, 3]
# tensor t4 with shape [2, 3]
tf.shape(tf.concat([t3, t4], 0)) ==> [4, 3]
tf.shape(tf.concat([t3, t4], 1)) ==> [2, 6]
```