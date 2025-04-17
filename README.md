# Computer Vision Fundamentals: Implementations and Comparisons

This repository explores fundamental computer vision techniques by implementing and comparing algorithms for noise handling, edge detection, corner detection, image stitching, and optical flow estimation using Python, OpenCV, and NumPy/SciPy.

## Notebooks Overview

This repository contains several Jupyter notebooks, each focusing on a specific aspect of the project. Below is a summary of each notebook and its key features:

**Notebook 1: `NoiseAddition_EdgeDetection.ipynb` - Image Noise Addition and Edge Detection Comparison**

*   Implements a function to add Gaussian noise (sigma=25) and applies it to create a noisy image set [1].
*   Defines standard image processing kernels (Sobel for X/Y directions, Gaussian blur) [1].
*   Performs edge detection by applying Gaussian smoothing followed by Sobel filtering using `scipy.signal.convolve2d` [1].
*   Visually compares edge detection results on original versus noisy images using Matplotlib grids [1].
*   Quantitatively evaluates the impact of noise on edge detection performance by calculating the Mean Squared Error (MSE) between the resulting edge maps [1].

**Notebook 2: `CornerDetection.ipynb` - Harris Corner Detection Implementation**

*   Implements the Harris corner detection algorithm from scratch [1].
*   Key steps include: Grayscale conversion, Gaussian smoothing (sigma=1), Sobel gradient calculation (Ix, Iy), structure tensor computation (Ixx, Iyy, Ixy), Harris response calculation (R = det(M) - k*trace(M)^2), non-maximum suppression, and thresholding [1].
*   Applies the implemented corner detector to the loaded images [1].
*   Visualizes the results by displaying original images alongside detected corners marked in red using Matplotlib [1].

**Notebook 3: `Panorama.ipynb` - Image Stitching for Panorama Creation**

*   Implements panorama stitching using SIFT (`cv2.SIFT_create`) for feature detection and description [user code].
*   Matches features using BFMatcher (`cv2.BFMatcher`) with KNN and Lowe's ratio test [user code].
*   Includes a custom implementation of RANSAC (`computeHomography_RANSAC`) to robustly estimate the homography matrix between image pairs [user code].
*   Contains a custom implementation of image warping (`warpPerspective`) using the calculated homography [user code].
*   Stitches images sequentially (right-to-left) and displays intermediate feature matches [1, user code].
  

**Notebook 4: `OpticalFlow.ipynb` - Lucas-Kanade Optical Flow Implementation and Visualization**

*   Implements the Lucas-Kanade optical flow algorithm (`lucas_kanade_optical_flow`) from scratch, using convolution for spatial gradients and least squares to solve for flow vectors (u, v) in local windows [1].
*   Computes dense optical flow between consecutive frames for multiple video sequences [1].
*   Provides functions to visualize optical flow:
    *   Using HSV color space (Hue=direction, Value=magnitude) [1].
    *   Using arrow overlays on grayscale frames (`visualize_optical_flow`) [1].
*   Generates and displays GIFs for original videos and both types of optical flow visualizations using `imageio` [1].
*   Implements image warping (`optical_flow_warping`) based on calculated flow vectors to align one frame to another, demonstrating warping between non-consecutive frames [1].

