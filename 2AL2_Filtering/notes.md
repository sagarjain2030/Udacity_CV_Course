### Notes:
- Now let's consider removing noise from image.
- So one way to do is take average of nearby pixels and replace currrent value of pixel by average.
- Assumptions madewith average approach:
	- The "true" value of pixels are similar to the true value of pixels nearby.
	- The noise added to each pixel is done independently.
- Another way can be subtracting noise function from image as noise is simply a function added to image. But since noise function itself is unknown, it is not possible to subtract it from image.

### Project/Code/Tutorials that can be done:
