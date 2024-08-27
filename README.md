# Image Processing with FFT and iFFT

This project demonstrates image processing using Fast Fourier Transform (FFT) and Inverse Fast Fourier Transform (iFFT) in Python. The code computes FFT and iFFT of an image, visualizes the magnitude and phase spectrum, and performs specific operations on an image using custom FFT and iFFT functions.

## Table of Contents
1. [Introduction](#introduction)
2. [Installation](#installation)
3. [Usage](#usage)
4. [Functions Overview](#functions-overview)
5. [Experiment Steps](#experiment-steps)
6. [Explanation of Output](#explanation-of-output)
7. [References](#references)

## Introduction

The purpose of this project is to:
- Compute the FFT and iFFT of an image.
- Visualize the magnitude and phase spectrum.
- Apply a series of image processing operations to an image using FFT and iFFT.

The project is inspired by exercises from "Digital Image Processing" by Gonzalez and Woods and NPTEL lectures by Prof. P.K. Biswas.

## Installation

To run the code, you need Python 3 and the following libraries:
- numpy
- matplotlib
- pillow

Install the required libraries using pip:

```
pip install numpy matplotlib pillow
```
## Usage
Prepare the Image: Ensure you have an image file named dip.tif or any other valid image file in the working directory or provide a path to an image file.

Run the Python Script:
```
python fft_image_processing.py
```
This script will:

- Read the image.
- Perform the transformations.
- Display the resultant image and visualize the FFT results.

## Functions Overview
- compute_fft:
Computes the Fast Fourier Transform (FFT) of a given grayscale image.<br/>

- compute_ifft:
Computes the Inverse Fast Fourier Transform (iFFT) of given FFT data.<br/>

- visualize_spectrum:
Visualizes the magnitude and phase spectrum of an image.<br/>

- load_image:
Loads an image from the specified path and converts it to grayscale.<br/>

- multiply_image_by_negative_power(image):
Multiplies the image by $(-1)^{x+y}$ at each pixel located at (x,y).<br/>

- process_image:
Processes the image by applying the transformations involving FFT and iFFT.


## Transformation Steps
- Load and Multiply Image: The image is loaded and multiplied by (-1)^(x+y) to shift the zero-frequency component to the center of the spectrum.
- Compute FFT: The FFT of the modified image is computed to transform the image into the frequency domain.
- Compute Complex Conjugate of FFT: The complex conjugate of the FFT result is calculated.
- Compute iFFT of Complex Conjugate: The iFFT is performed on the complex conjugate to return to the spatial domain.
- Multiply the Real Part by (-1)^(x+y): The real part of the iFFT result is multiplied again by (-1)^(x+y) to re-center the zero-frequency component.

## Explanation of Output
The output image will show a mirrored or flipped version of the original image due to the complex conjugation in the frequency domain and subsequent transformations. The operations illustrate the effects of manipulating the Fourier components on the spatial representation of the image.

## References
- Gonzalez, Woods “Digital Image Processing” 3/e, Chapter 3, Prentice Hall.
- NPTEL Lectures on Digital Image Processing by Prof. P.K. Biswas.
