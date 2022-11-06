### Notes:
- Now let's consider removing noise from image.
- So one way to do is take average of nearby pixels and replace currrent value of pixel by average.
- Assumptions madewith average approach:
	- The "true" value of pixels are similar to the true value of pixels nearby.
	- The noise added to each pixel is done independently.
- Another way can be subtracting noise function from image as noise is simply a function added to image. But since noise function itself is unknown, it is not possible to subtract it from image.
- Weighted Average:
	- The pixels closer to interested pixel contributes more in defining interested pixel's value as compared to pixel further away from interested pixel. So in such cases, weighted average works quite well.
	- In weighted average, weights are assigned to each pixel value, taken their multiplications and then averaged out to get final pixel value.
	- These weights are divided by total sum of weights.It gives smoother value of pixel.
	- For weighted average, number of pixels should be odd with interessted pixel having highest weight and it should be in center.
- Correlational Filtering
	- Uniform weights of kernel (filter)
		- if we have window size of $\(2k+1\) * (2k+1)$,      
		$$G[i,j]=\left(1/\left(2k+1\right)^2\right)  \sum_{u=-k}^k \sum_{v=-k}^k F\left[i+u,j+v\right] $$      	
		- Uniform weights means all weights are equal  (mostly 1)
	- Non Uniform weights:
		- if we have window size of $\(2k+1\) * (2k+1)$,    
		$$G[i,j]=\sum_{u=-k}^k \sum_{v=-k}^k H\left[u,v\right] F\left[i+u,j+v\right] $$      
		where $H\left[u,v\right]$ are non uniform weights.
	- This is called cross correlation denoted by G = H $\bigodot$ F
	- The H is called kernel or mask. $H\left[u,v\right]$ is matrix of weights in linear combination.
	- To create a blurry spot at a pixel, use filter with higher value in middle, falling of the edges.
	- So if we build H such that nearest neightbours have most influence.
	- This type of mash is also known as Gaussian filter
- so Gaussian filer is filter with circular symmetric fuzzy blob at center. i.e. middle values are highest while values away from middle are decreasing.
	- isotropic ==> circularly symmetric 
	- variance of Gaussian filters determine extent of smooting .
	- The bigger the variance $\sigma^2$ , the more blur    