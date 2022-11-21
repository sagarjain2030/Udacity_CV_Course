### Notes:
- Linear Operator
	- An operator H is linear if two properties hold : If f1 and f2 are function and a is constant then,
		- Additivity :     
		    $$H\left(f1+f2\right) = H\left(f1\right) + H\left(f2\right) $$
		- Multiplicativity scaling (Homogeneity of degree) :       
            $$H\left(a.f1\right) = a.H\left(f1\right) $$
	- Hence filtering is linear operation
- Impulse 
	- Linearity allows to build an image a piece at a time and then helps to understand how linear operator affects that image.
	- Building block of any such function mentioned above is impulse. So, in discrete world, impulse is just value 1 at a single location.
	- In continuouse world, impulse is an idealized function that has unit area 
	- For any unknown system, response for impulse by that system is impulse response. So if system is linear, impuslse response is h(x)
- Impulse response in Image:
	- Consider image with only 1 pixel value as 1 while all others are 0.
	- So when we run a correlational filter of impulse input, we get mask values vertically and horizonatally both flipped.
- How many multiples would happen for applying mask of size N \* N over and image of size M \* M :
	- So for each mask and one pixel of image, we have N \* N multiplications happening.
	- Filter will be performing operations for M \* M times
	- So total multiples are M \* M \* N \* N
- Convolution 
	- Now since correlational operation gives us output vertically and horizontally flipped, applying a already flipped filter will give output as it is.
	- Application of this flipped filter is called convolution.
	- So convolution filters image bottom to top and right to left.
	- For symmetric filters, correlational and convolutional operation makes no difference but the output of these 2 filters matters for asymmetric filters.
	- If we convolve an image with an impulse, we get original image.
	
