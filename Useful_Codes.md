### Started code to read image and convert to grayscale
```
import numpy as np
import cv2
from google.colab.patches import cv2_imshow

img_path = "/content/panda.jpg"
col_img = cv2.imread(img_path)
cv2_imshow(col_img) 
bnw_img = cv2.cvtColor(col_img,cv2.COLOR_BGR2GRAY)
cv2_imshow(bnw_img) 
print(bnw_img.shape)
```

### Code to convert given 2D image in surface plot

```
# Convert the image to grayscale
gray = cv2.cvtColor(col_img, cv2.COLOR_BGR2GRAY)

# Create x and y arrays with the same shape as the image
y, x  = np.mgrid[0:gray.shape[0], 0:gray.shape[1]]
# Create a figure and a 3D axes object
fig = plt.figure()
ax = fig.add_subplot(111, projection='3d')

# Plot the intensity of the image as a height map
ax.plot_surface(x, y, gray, cmap='gray')
ax.set_xlabel('X-axis')
ax.set_ylabel('Y-axis')
ax.set_zlabel('Intensity')
plt.show()
```