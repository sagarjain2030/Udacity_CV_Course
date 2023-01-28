### Notes:
- Filetrs can be considered as medium to reach intermediate representation of image.    
for example,we can convert image into an array (may be image or may not be an image) using filter. This array now has values such that, these values represents some properties of local pixel or local pixel group unlike the original image where these values represented intensity of each pixel.
- Before comparing effects of two filters, remember to make sure that the correlation done on image using filters are normalized, i.e. standard deviation is made at one.(in general case).
- Normalization is done so that effect won't be scaled up or down with respect to corresponding filter's scale.
- Normalization of correlation is done in two steps :
	1. Normalize the filter itself.
	2. Normalize the patch of image where filter is currently get applied.
- Only after normalizing correlation, we can have coparable results.
- In any correlation, we can have maximum value of filtering, 
	- when, for positive signal, we have filter value to be positive.
	- when, for negative signal, we have filter value to be negative.
- Template is pattern needs to be found in an image, so we can consider, filter as template.
- Using normalised correlation, we can figure out exact locaation where template match gives maximum score for filtering.
- But using template matching has its own disadvantages. We can only find a match, if filter is fairly right in it's scale orientation and genearal appearance.(that means, it will work only if filter and actual are closely matched.)
- One way to improve matching is to blur both image and filter, so that it would be easy to have a match.
- Template matching helps to locate area of interest.