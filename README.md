# ashwini
1. Develop a program o perform linear transformation of an image
2. import cv2
# Reading the image
image = cv2.imread('red.jpg')
# dividing height and width by 2 to get the center of the image
height, width = image.shape[:2]
# get the center coordinates of the image to create the 2D rotation matrix
center = (width/2, height/2)
# using cv2.getRotationMatrix2D() to get the rotation matrix
rotate_matrix = cv2.getRotationMatrix2D(center=center, angle=45, scale=1)
# rotate the image using cv2.warpAffine
rotated_image = cv2.warpAffine(src=image, M=rotate_matrix, dsize=(width, height))
cv2.imshow('Original image', image)
cv2.imshow('Rotated image', rotated_image)
# wait indefinitely, press any key on keyboard to exit
cv2.waitKey(0)
# save the rotated image to disk
cv2.imwrite('rotated_image.jpg', rotated_image)

original image
![image](https://user-images.githubusercontent.com/95745972/148203058-e5a43c63-ef19-45a6-9c85-bf3d826e63b6.png)
rotate image
![image](https://user-images.githubusercontent.com/95745972/148203159-67d6c2a1-699a-4045-98f2-f62c6e6add58.png)
