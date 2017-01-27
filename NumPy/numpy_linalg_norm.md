##numpy.linalg.norm(x, ord=None, axis=None, keepdims=False)[source](https://docs.scipy.org/doc/numpy/reference/generated/numpy.linalg.norm.html#numpy.linalg.norm)

###Matrix or vector norm. This function is able to return one of eight different matrix norms, or one of an infinite number of vector norms, depending on the value of the ord parameter.

###The following norms can be calculated:
		ord	norm for matrices	norm for vectors
		None	Frobenius norm	2-norm
		‘fro’	Frobenius norm	–
		‘nuc’	nuclear norm	–
		inf	max(sum(abs(x), axis=1))	max(abs(x))
		-inf	min(sum(abs(x), axis=1))	min(abs(x))
		0	–	sum(x != 0)
		1	max(sum(abs(x), axis=0))	as below
		-1	min(sum(abs(x), axis=0))	as below
		2	2-norm (largest sing. value)	as below
		-2	smallest singular value	as below
		other	–	sum(abs(x)**ord)**(1./ord)

####Parameters:	
		x : array_like
			Input array. If axis is None, x must be 1-D or 2-D.
		ord : {non-zero int, inf, -inf, ‘fro’, ‘nuc’}, optional
			Order of the norm (see table under Notes). inf means numpy’s inf object.
		axis : {int, 2-tuple of ints, None}, optional
			If axis is an integer, it specifies the axis of x along which to compute the vector norms. If axis is a 2-tuple, it specifies the axes that hold 2-D matrices, and the matrix norms of these matrices are computed. If axis is None then either a vector norm (when x is 1-D) or a matrix norm (when x is 2-D) is returned.
		keepdims : bool, optional
			If this is set to True, the axes which are normed over are left in the result as dimensions with size one. With this option the result will broadcast correctly against the original x.
		
####Returns:	
		n : float or ndarray
			Norm of the matrix or vector(s).

####Examples:

		>>> from numpy import linalg as LA
		>>> a = np.arange(9) - 4
		>>> a
		array([-4, -3, -2, -1,  0,  1,  2,  3,  4])
		>>> b = a.reshape((3, 3))
		>>> b
		array([[-4, -3, -2],
		       [-1,  0,  1],
		       [ 2,  3,  4]])
		>>>
		>>> LA.norm(a)
		7.745966692414834
		>>> LA.norm(b)
		7.745966692414834
		>>> LA.norm(b, 'fro')
		7.745966692414834
		>>> LA.norm(a, np.inf)
		4.0
		>>> LA.norm(b, np.inf)
		9.0
		>>> LA.norm(a, -np.inf)
		0.0
		>>> LA.norm(b, -np.inf)
		2.0
		>>>
		>>> LA.norm(a, 1)
		20.0
		>>> LA.norm(b, 1)
		7.0
		>>> LA.norm(a, -1)
		-4.6566128774142013e-010
		>>> LA.norm(b, -1)
		6.0