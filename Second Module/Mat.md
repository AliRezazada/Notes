# Mat

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

#  Creating a Mat Object Explicitly

`Mat M(2,2, CV_8UC3, Scalar(0,0,255));
`cout << "M = " << endl << " " << M << endl << endl;`

The first line of code means you create a 2x2 matrix (2,2, ) the CV_8UC3 indicates 8 bit unsigned integer C3 = 3 channel colour scheme like RGB and scalar (0,0,255) means Blue = 0, Green = 0, Red = 255.

*CV_[The number of bits per item] [Signed or Unsigned] [Type Prefix] C [The channel number]*

Produces:

![[Pasted image 20250527163202.png]]

Each row has two pixels -> so basically the matrix would look like:

[
 [B,G,R], [B,G,R] 
 [B,G,R], [B,G,R]       
]


each array within the matrix constitutes for 1 pixel, in grey scale each array would account for just an integer value of between 0-255 indicating the intensity of the black to white ratio (black = 0, white = 255).













	

