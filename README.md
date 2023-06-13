# hit
# importing required libraries
import mahotas as mh
import numpy as np
from pylab import imshow, show
	
# creating region
# numpy.ndarray
regions = np.zeros((10, 10), bool)
	
# setting 1 value to the region
regions[1, :2] = 1
regions[5:8, 6: 8] = 1
regions[8, 0] = 1
	
# showing the image with interpolation = 'nearest'
print("Image")
imshow(regions, interpolation ='nearest')
show()

# template for hit miss
template = np.array([
			[0, 1, 1],
			[0, 1, 1],
			[0, 1, 1]])

# hit miss transform
img = mahotas.hitmiss(regions, template)

# showing image
print("Image after hit miss transform")
imshow(img)
show()
