
# Surface Roughness Estimation Using Image Analysis

## Overview
This project implements a computer vision algorithm to estimate the surface roughness of materials by analyzing an image of the surface. The algorithm converts the color image to grayscale and calculates statistical measures such as standard deviation and root mean square (RMS) of the gray levels to estimate the average surface roughness parameter (R_a).

The method is based on the analysis of the grayscale pixel intensity distribution to infer surface texture characteristics, inspired by techniques from machine vision and surface metrology.

## How It Works
- An input image of a surface is loaded.
- Each pixel is converted from RGB to a grayscale value using a weighted sum:  
  \( v = 0.21 B + 0.72 G + 0.07 R \)  
- A histogram of grayscale values (0-255) is constructed to obtain pixel frequency distribution.
- The standard deviation and RMS values of the grayscale distribution are computed.
- The average surface roughness parameter \( R_a \) is estimated as the ratio of standard deviation to RMS.
- The grayscale histogram is plotted, and the original image is displayed for visual inspection.

## Usage
1. Place the surface image to be analyzed in the working directory and name it `test_img.jpg` or modify the path in the script accordingly.
2. Run the Python script to obtain the surface roughness estimation.
3. The script outputs the calculated standard deviation, RMS, and \( R_a \) value in the console.
4. A plot of grayscale level frequencies and the image is displayed.

## Requirements
- Python 3.x
- OpenCV (`cv2`) for image handling
- Matplotlib for plotting

Install dependencies with:
```
pip install opencv-python matplotlib
```

## Background and Applications
This algorithm models surface roughness by analyzing scattered light intensity reflected from surfaces, as captured in images. The grayscale pixel intensity distribution corresponds to the surface topography's height variations.

Potential applications include:
- Enhancing vehicle energy efficiency by adjusting power output based on road surface roughness
- Assisting visually impaired individuals by characterizing surrounding object textures
- Analyzing extraterrestrial terrain textures in planetary exploration missions

## Results Summary
Testing on various materials (wood, carpet, concrete, etc) shows distinct surface roughness values consistent with their textures. Abrasive papers with known roughness values were used for calibration, displaying high correlation with measured values down to certain roughness limits.

Limitations include sensitivity to image shadows and fine scratches, which affect accuracy. Preprocessing steps to minimize shadow effects improve results.

## Future Work
- Integrate additional preprocessing to improve accuracy, such as cropping shadows or averaging multiple image regions.
- Explore Fourier transform analysis to quantify surface disturbance patterns.
- Cross-reference roughness values with other material attributes for classification purposes.

## Reference
The algorithm is inspired by methods described in:

"Measurement of Surface Roughness by a Machine Vision System,"  
(Reference paper on light scattering and grayscale histogram analysis for surface roughness measurement.)
