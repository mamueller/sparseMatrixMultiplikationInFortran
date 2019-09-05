The blas subdirectory 

is only there to test the installation of the mkl library 
It uses a routine that computes the dot product


The spblas subdirectory 

contains examples (partly even in f77) using the "sparse blas" subroutines
"sparse blas" is the interesting extension to blas for sparse matrixes and vectors.
Not all spblase implementations contain routines for the multiplication of a
sparse matrix wiht a sparse matrix. Some only implement a sparse matrix dense vector product
Which is enough to implement a matrix product though if one starts from the last matrix vector product 
and multiplies the other parts of the matrix product repeatedly from the left.

The mkl even has a special routine for sparse matrix matrix multiplications 

Interresting are especially 
"spblas/source/dcsr_multiplication" 
which implements the multiplication of two sparse matrices
and 
"spblas/source/sparse_c_csrmv.f90" 
which implements a multiplication of a sparse matrix with a dense vector
It also is quite convinient because it uses the fortran module for the binding.

The most interesting since it already is in Fortran90 and using a new (afaIk mkl specific interface) 
is:
"spblas/source/sparse_d_export_csr.f90"
which we will use to build a bigger test case which we can compare to normal matrix multiplication
in 
