##numpy.nan_to_num(x)[source](https://docs.scipy.org/doc/numpy/reference/generated/numpy.nan_to_num.html#numpy.nan_to_num)

###Replace nan with zero and inf with finite numbers. Returns an array or scalar replacing Not a Number (NaN) with zero, (positive) infinity with a very large number and negative infinity with a very small (or negative) number.

####Parameters:	
		x : array_like
			Input data.

####Returns:	
		out : ndarray
			New Array with the same shape as x and dtype of the element in x with the greatest precision. If x is inexact, then NaN is replaced by zero, and infinity (-infinity) is replaced by the largest (smallest or most negative) floating point value that fits in the output dtype. If x is not inexact, then a copy of x is returned.

####Examples

		>>> np.set_printoptions(precision=8)
		>>> x = np.array([np.inf, -np.inf, np.nan, -128, 128])
		>>> np.nan_to_num(x)
		array([  1.79769313e+308,  -1.79769313e+308,   0.00000000e+000,
		        -1.28000000e+002,   1.28000000e+002])