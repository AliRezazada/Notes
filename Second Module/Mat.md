
a C++ class with two data parts: The matrix header and a pointer containing the pixel values.

**Matrix Header**

Stores metadata about the image -> size of matrix, method for storing, the address the matrix is stored at etc.

**Pointer**

Points to the matrix containing the pixel values.

The same image can have multiple matrix objects attached to it, this is done by each matrix object has its own matrix header that points to the allocated slot in memory where the actual image matrix is located. This allows for each matrix object to have access to the matrix image. Main benefits: 

- Saves Memory
- Very fast (copying a pointer vs. copying millions of pixels)
- Allows for flexible manipulation (like ROI views)

Problem, if multiple matrix objects point to the same memory slot, altercations will be made to across the board (changes to Mat A will affect both Mat B and Mat C). 

`Mat F = A.clone();
This will clone a copy of matrix A to Mat F, and changes Mat F does to the matrix will not affect Mat A

# Storing methods






	

