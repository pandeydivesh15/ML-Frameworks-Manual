##numpy.argmax(a, axis=None, out=None)[source]

###Returns the indices of the maximum values along an axis.

####Parameters:	
		a : array_like
				Input array.
		axis : int, optional
				By default, the index is into the flattened array, otherwise along the specified axis.
		out : array, optional
				If provided, the result will be inserted into this array. It should be of the appropriate shape and dtype.

####Returns:	
		index_array : ndarray of ints
				Array of indices into the array. It has the same shape as a.shape with the dimension along axis removed.

####Examples

>>> a = np.arange(6).reshape(2,3)
>>> a
array([[0, 1, 2],
       [3, 4, 5]])
>>> np.argmax(a)
5
>>> np.argmax(a, axis=0)
array([1, 1, 1])
>>> np.argmax(a, axis=1)
array([2, 2])
>>> b = np.arange(6)
>>> b[1] = 5
>>> b
array([0, 5, 2, 3, 4, 5])
>>> np.argmax(b) # Only the first occurrence is returned.
1