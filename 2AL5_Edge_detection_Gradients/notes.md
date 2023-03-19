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
		$$ \frac{\mathrm \delta f\left( x, y\right)}{\mathrm \delta x} =    \lim_{x\to\infty} \frac{f\left(x+\epsilon,y\right) - f\left(x,y\right)}{\epsilon}  $$
	- But in case of discreet data, there cannot be ε but a finite distance only.So  
		$$ \frac{\mathrm \delta f\left( x, y\right)}{\mathrm \delta x} =    \lim_{x\to\infty} \frac{f\left(x+1,y\right) - f\left(x,y\right)}{1}  $$
	- This means, gradient is taken by moving 1 unit distance (in case of a image, 1 pixel) at a time.