### Notes:
- Why we multiply first smoothing operator with derivative filter and then apply it to Image, it is becasue
	- Since derivative operator is smaller so we take fewer calculations and so it is faster.
	- Also smoothing filter is applied again and again and then derivative is applied again and again..These multiple calculations can be avoided.
- Now to smooth image, Gaussian filter is used. But the sigma value affects again.
	- If lower sigma value is used, finer features are detected.
	- If higher sigma value is used, larger scale details are detected.
- Depending upon the region of interest and how finer and how larger ddetails are required, sigma values for Gaussian filter is decided.
- So Primary steps to detect edges:
	1. Smoothing derivatives to suppress noise and compute gradient.
	2. Threshold to find regions of significant gradient.
	3. Thin to get localised edge pixels.
	4. Link/connect edge pixels to form edge.
- So most useful edge operator is Canny Edge Operator.
- Canny edge operator works as :
	1. Filter image with derivative of Gaussian.
	2. Find magnitude and orientation of gradient.
	3. Non maximum suppression:
		- Thin multi pixel wide ridges to single pixel width.
	4. Linking and Thresholding (Hysteresis)
		- Define Two Threshold : Low and High
		- Use the high threshold to start edge curves and the low threshold to continue them.
- Canny Threshold Hysteresis:
	1. Apply a high threshold to detect strong edge pixels.
	2. Link those strong edge pixels to form strong edges.
	3. Apply a low threshold to find a weak but plausible edge pixels.
	4. Extend the strong edges to follow weak edge pixels.
- The disadvantage of canny edge operator is since it depends upon how smooth image is, Gaussian sigma may lead it to be suseptible to noise in image
- In case of 1D, we can get edge by applying 2nd derivative . But in case of 2D, it is possible to have 2nd derivative either 
in
	- completely X direction
	- completely Y direction
	- 1st derivative in both X and Y direction.
- To avoid such complications, we can apply Laplacian operator.
$${▼}^{2}h = \frac{\mathrm {d}^{2}f}{\mathrm d{x}^{2}} + \frac{\mathrm {d}^{2}f}{\mathrm d{y}^{2}} $$
Here $${▼}^{2}$$ is Laplacian operator and Zero crossings give the edges.
- So in 2D, we can apply either,
	- Difference between Right shifted image by 1 pixel and left shifted image by 1 pixel
	- Canny Edge Detection
	- Difference of Gaussian i.e. applying 2nd derivative in either the 3 possibilities
	- Laplacian of Gaussian    
and Search for zero crossings to get the edges.