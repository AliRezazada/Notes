# Images 


The code below reads an image from file, imread() returns a matrix, if imread() cannot properly return the image matrix based on certain complications it will return an empty matrix.

`Mat img = imread(filename);`

By default, a jpg file will create a 3 channel image by default, therefore you must specify which channel type you wish to use.

`Mat img = imread(filename_ IMREAD_GRAYSCALE);`

To save an image to a file:

`imwrite(filename, img);`

# Basic operations with images

`Scalar intesitiy = img.at<uchar>(y,x);` 

To understand the intensity of image, you need to view the pixel, the matrix stores pixels, and looking at the pixel value will provide an indication of the intesitiy of the pixel (i.e. greyscale a pixel value of 155 means the pixel has an intensity closer to white than black).

