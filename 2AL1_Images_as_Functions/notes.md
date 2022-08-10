### Notes:
- Image is a function. So for gray scal Image    
 $I(x,y) = GrayscaleValue$
- So Image processing for computer vision is mostly image like values i.e. we take one image as input and output another image.
- An Image can be 2 Dimensional arrayof numbers with some minimum and maximum fixed value as range.
- A function $I = R^2 --> R$ where $(x , y)$ pixel image and $I(x , y)$ is intensity or value at position $(x, y )$
- In practice, we define ranges for $x$ and $y$ , so it would be   
       $f : [a : b] X [c : d] --> [min , max]   
	and intensity ranges from some min value to some max value.
- In case of color images, instead of one function we would have 3 functions, one for each color channel. So for color image, function would become:  
  $I = R^2 --> R^3$
- For a Digital Image, we need,  
	- Sample : Divide the 2 Dimensional space into regular grid i.e. divide 2 Dimensional area into a single point each.
	- Quantize : Quantify each sample i.e. convert the frequency at each point to closest integer.
- Quantization is required since we cannot use continuous real values.
- In image, pixel value is represented as $(x , y)$. It means x goes horizontally while y goes vertically      
- Since image is considered as matrix in computer, $i$ represents row and $j$ represents column 
![image_details](picture1.jpg)


### Project/Code/Tutorials that can be done:
- For any given grayscale image, print a surface with x and y as coordinates and gray scale value as value.
- Write a function to convert given matrix to quantized matrix with given min and max values.([notebook](2A_L1_Image_As_Function.ipynb))
- Load and Display Dolphin.png. Print its size and datatype.
