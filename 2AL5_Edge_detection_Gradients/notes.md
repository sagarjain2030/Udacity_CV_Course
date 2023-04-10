### Notes:
- Edges are important in image since they describe what image shape represents.
- Edges originated in image when one of the following properties are hold : 
	1. Surface Normal Discontinuity
	2. Depth Discontinuity
	3. Surfae color Discontinuity
	4. Illumination Discontinuity
- If we plot intensity of image, edges looks like steep cliffs. 
- So to determine if a pixel is edge pixel i.e. if pixel lies on an edge in image, we need to look for strong change in intensity.
- But looking for these changes, arises 2 problems.
	1. How big a neighbourhood should be i.e. size of neighbourhood.
	2. How to detect changes.
- Let's consider the second problem first. Now since we are searching for changes, we can consider that derivatives.
- If we take derivatives of intensity in a row (first derivatives), edges can be determine by exteme changes in derivatives like exteme minima and exteme maxima.
- To find such exteme minima and maxima, we can apply filters/operators on image.
- A multivariant calculus is calculus of such functions which are depend upon more than 1 function.
- In case of image, output is intensity at a pixel and input is 2 variables x and y. Thus Image is multivariant function.
- Differential Operator: These are the operators when applied to image return some derivatives.
- We can model these differential operators as mask/filter/Kernel that comput image gradient function.
- By applying some threshold to this gradient, we can detect edge pixel.
- What is Gradient:
	- For multivariant function, we can have partial derivatives for each variable.
	- Gradient is a vector where first value is partial derivative with respect to first variable and second value is partial derivative with respect to second variable and so on.
	- So for image function f(x,y)
		$$▼f = {\left\lbrack \frac{\mathrm df}{\mathrm d x} , \frac{\mathrm df}{\mathrm d y} \right\rbrack} $$
	- Gradient points in the direction of most rapid increse in intensity 
	- direction	
		$$Θ = \{tan}^{-1} \left(\frac{\mathrm \delta f}{\mathrm \delta y} / \frac{\mathrm \delta f}{\mathrm \delta x}\right) $$
	- Amount 
		$$||▼f|| = \sqrt{{\left(\frac{\mathrm \delta f}{\mathrm \delta y}\right)}^{2} + {\left(\frac{\mathrm \delta f}{\mathrm \delta x}\right)}^{2}}$$
- If Gradient is zero, that means 
	1. Either image is constant over entire neighbourhood.
	2. Underlying function is either maximum or minimum
- Discrete Gradient.
	- Partial derivative is given as  
		$$\frac{\mathrm \delta f\left( x, y\right)}{\mathrm \delta x} =    \lim_{x\to0} \frac{f\left(x+\epsilon,y\right) - f\left(x,y\right)}{\epsilon}$$
	- But in case of discreet data, there cannot be ε but a finite distance only.So  
		$$\frac{\mathrm \delta f\left( x, y\right)}{\mathrm \delta x} =    \lim_{x\to0} \frac{f\left(x+1,y\right) - f\left(x,y\right)}{1}$$
	- This means, gradient is taken by moving 1 unit distance (in case of a image, 1 pixel) at a time.
- For an image, while calculating partial derivative with respect to x, correlation filter would be [-1, 1]
- For an image, while calculating partila derivative with respect to y, correlation filter would be $$[-1, 1]^T$$ if y is decreaing from top to bottom. If y is decreasing from bottom to top, it would be $$[1, -1]^T$$.
- This is because, in CS, origin is considered to be at top left hand corner in image. But in mathematics, origin is considered to be at bottom left hand corner in image.
- If we take only magnitude, then it would give edge image.
 - Now we want an operator/mask which gives discrete gradient on image, when applied.
 - it can be $$\left\lbrack \matrix{0 & 0 \cr -1 & +1 \cr 0 & 0} \right\rbrack$$
 - but problem with this operator is non symmetry. around image point.
 - One way to have proper operator is to apply this filter to 2 consecutive pixel and take average of them.Thus the operator becomes  
	 $$\left(\left\lbrack \matrix{0 & 0 + 0 & 0 \cr -1 & -1 + 1 & +1 \cr 0 & 0 + 0 & 0} \right\rbrack\right)  / 2  ...  then$$    
	 $$\left\lbrack \matrix{0 & 0 & 0 \cr -1/2 & 0 & +1/2 \cr 0 & 0 & 0} \right\rbrack$$
- Sobel Operator:
	- In sobel operator, origin is considered to be at left bottom corner of image.So y is increasing(positively) in upward direction.    
	 $$S_{X} = \frac{1}{8} * \left\lbrack \matrix{-1 & 0 & +1 \cr -2 & 0 & +2 \cr -1 & 0 & +1} \right\rbrack$$
	 $$S_{Y} = \frac{1}{8} * \left\lbrack \matrix{+1 & +2 & +1 \cr 0 & 0 & 0 \cr -1 & -2 & -1} \right\rbrack$$
	- So idea is , to check boundary change, look not only at pixel ahead and behind of interest pixel, but also the nearby pixels
	- So sobel operator considers all nearby pixel of interest pixel and performs differentials. To normalize, it divides the values by 8.
	- So sobel gradient is 
		$$▼I = {\left\lbrack g_{x} , g_{y} \right\rbrack}^{T} $$	
		- direction	
			$$Θ = \{atantwo}( g_{y},  g_{x}) $$
		- Amount 
			$$g = \sqrt{{\left(g_{x}\right)}^{2} + {\left(g_{y}\right)}^{2}}$$
- The other operators are:
	- Prewitt:
				$$S_{X} = \left\lbrack \matrix{-1 & 0 & +1 \cr -1 & 0 & +1 \cr -1 & 0 & +1} \right\rbrack$$
				$$S_{Y} = \left\lbrack \matrix{+1 & +1 & +1 \cr 0 & 0 & 0 \cr -1 & -1 & -1} \right\rbrack$$
	- Robert:
				$$S_{X} = \left\lbrack \matrix{0 & +1 \cr -1 & 0} \right\rbrack$$
				$$S_{Y} = \left\lbrack \matrix{+1 & 0 \cr 0 & -1} \right\rbrack$$
- It is better to compute gradient using correlation because it is easier to know which way the derivative are being computed.
- Now in real worlds, image is not that clean. We need to remove noise in order to get better edge detection.
	- Removal of noise can be done by smoothning image. So apply filter to smoothen the image.
	- Hence the procedure becomes, 
		$$Image I \thinspace \underset{\text{apply \thinspace smoothning \thinspace filter}} \longrightarrow \thinspace \thinspace \thinspace h * I \thinspace   \underset{\text{Apply\thinspace edge\thinspace detection\thinspace filter}} \longrightarrow \thinspace\thinspace\thinspace\frac{\mathrm \delta}{\mathrm \delta x}\left( h * I \right) $$

