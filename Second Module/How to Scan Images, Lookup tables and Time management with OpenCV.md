
# How is the image matrix stored in Memory?

Matrix size is dependent on the color system used, the more complex a color system, the more it will take up in memory. From previous notes it makes sense if we comparatively look at greyscale vs BGR system.
### Grey Scale vs BGR scale 

![[Pasted image 20250528093922.png]]

![[Pasted image 20250528093937.png]]

All in All, you do not use the lookup algo, images become very costly and can provide confusion for some areas of application -> robotics for example, may get confused on the image, reducing the intensity of the image will aid in keeping things simplified for the robot and provides the same functionality. 

an example -> converting images to greyscale, costs less memory and provides the application (robotics etc), enough information.


