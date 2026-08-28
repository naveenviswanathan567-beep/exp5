### Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

### Software Required:
Anaconda - Python 3.7

### Algorithm:
==> Step1 Load the input image and convert it from BGR to RGB format.

==> Step2 Select the required filter (Averaging, Weighted Averaging, Gaussian, Median, Laplacian Kernel, or Laplacian Operator).

==> Step3 Apply the selected filter to the image using the appropriate OpenCV function.

==> Step4 Store the processed (filtered or sharpened) image.

==> Step5 Display both the original image and the processed image for comparison.

### Program:
Developed By : NAVEEN V Register Number: 212225240098

Smoothing Filters i) Using Averaging Filter
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("8.jpeg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/169
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()
ii) Using Weighted Averaging Filter

kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
image3=cv2.filter2D(image2,-1,kernel1)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
iii) Using Gaussian Filter

gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
iv)Using Median Filter

median=cv2.medianBlur(image2,13)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")
plt.show()
Sharpening Filters i) Using Laplacian Linear Kernal
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
ii) Using Laplacian Operator

laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
OUTPUT:

Smoothing Filters
i) Using Averaging Filter

<img width="717" height="603" alt="download" src="https://github.com/user-attachments/assets/2e26c201-8e02-44cb-b051-29b20d193335" />


ii)Using Weighted Averaging Filter

<img width="522" height="409" alt="download (1)" src="https://github.com/user-attachments/assets/e8e3b29c-2c63-4b25-8bbc-6bb995806987" />


iii)Using Gaussian Filter

![Uploading download (2).png…]()


iv) Using Median Filter

<img width="717" height="603" alt="download (3)" src="https://github.com/user-attachments/assets/e3678ca5-170a-4799-91aa-d3f2ed055ea0" />



Sharpening Filters
i) Using Laplacian Kernal

<img width="498" height="409" alt="download (4)" src="https://github.com/user-attachments/assets/c0608408-53b8-4854-a097-cf5b50d04101" />


ii) Using Laplacian Operator

<img width="498" height="409" alt="download (5)" src="https://github.com/user-attachments/assets/25a558bf-d320-46de-82ae-6ad0454b69bd" />


Result: Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
