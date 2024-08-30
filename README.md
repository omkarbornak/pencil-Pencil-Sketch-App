# pencil-Pencil-Sketch-App
Creating an AI project for beginners may seem straightforward nowadays, thanks to the existence of libraries that can handle image conversion on our behalf. However, the true challenge lies in constructing a functional app that allows users to interact with the AI, as it demands proficiency in languages beyond Python.
import cv2
import numpy as np

def pencil_sketch(img):
    # Convert image to grayscale
    gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)

    # Apply Gaussian blur to reduce noise
    blur = cv2.GaussianBlur(gray, (5, 5), 0)

    # Detect edges using Canny edge detection
    edges = cv2.Canny(blur, 50, 150)

    # Create a pencil sketch effect
    sketch = cv2.bitwise_not(edges)

    return sketch

# Load the image
img = cv2.imread('image.jpg')

# Convert the image to a pencil sketch
sketch = pencil_sketch(img)

# Display the output
cv2.imshow('Pencil Sketch', sketch)
cv2.waitKey(0)
cv2.destroyAllWindows()
