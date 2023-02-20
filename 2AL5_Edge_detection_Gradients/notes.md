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
