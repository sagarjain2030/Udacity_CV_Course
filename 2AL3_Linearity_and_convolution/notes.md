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
