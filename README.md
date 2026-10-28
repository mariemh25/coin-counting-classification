# coin-counting-classification
A computer vision project that detects coins in an image, estimates their count, classifies them by size, and calculates an estimated total value using classical image processing techniques.

## Overview

This project implements an automated coin counting system using Python and OpenCV. It processes input images through a series of image processing operations to identify coin-shaped regions and produce a visualized result.

The system also includes an interactive GUI built with `ipywidgets` in Google Colab, allowing users to upload an image and view the detected coins and estimated total value.

## Features

- Coin detection using contour analysis.
- Image preprocessing and contrast enhancement.
- Noise reduction using Gaussian and median filtering.
- Global, Otsu, and adaptive thresholding techniques.
- Morphological operations for noise removal and region refinement.
- Contour filtering using area, circularity, radius, and aspect ratio.
- Size-based coin classification: Small, Medium, and Large.
- Estimated total value calculation.
- Evaluation against ground-truth coin counts.
- Interactive image upload and processing GUI in Google Colab.
- Visualization of results and challenging failure cases.

## Technologies Used

- Python
- OpenCV
- NumPy
- Pandas
- Matplotlib
- KaggleHub
- ipywidgets

## Methodology

The system follows a classical computer vision pipeline:

1. Dataset loading and evaluation image selection.
2. Grayscale conversion.
3. Contrast enhancement using histogram equalization and CLAHE.
4. Noise reduction using Gaussian and median blur.
5. Thresholding using multiple approaches.
6. Morphological opening and closing.
7. Contour detection and filtering.
8. Coin classification based on contour area.
9. Coin counting and estimated value calculation.
10. Evaluation and visualization of results.

Multiple thresholding candidates are evaluated, and the candidate producing the highest scoring number of valid contours is selected.

## Results

The system was evaluated on 15 selected images representing different levels of difficulty.

| Metric | Result |
|---|---:|
| Evaluation images | 15 |
| Average counting accuracy | 74.06% |

The evaluation compares predicted coin counts with actual counts from the dataset. Accuracy is calculated using the absolute counting error relative to the actual count.

The system performs better on images with clear backgrounds, good lighting, and separated coins. Performance decreases when coins overlap, are partially cropped, or appear against complex backgrounds.

## Limitations

- Overlapping coins may merge into a single detected region.
- Shadows and complex backgrounds can affect segmentation.
- Cropped coins may not be detected accurately.
- Size-based classification depends on the detected contour areas.
- Total value is an estimate based on size categories and predefined values, rather than recognition of actual coin denominations.


## How to Run

The notebook is designed for Google Colab.

1. Open the notebook in Google Colab.
2. Install the required dependencies.
3. Download or configure access to the coin image dataset.
4. Run the notebook cells in order.
5. Review the processing pipeline, evaluation results, and visualizations.
6. Use the interactive GUI to upload and process an image.

The notebook requires access to the dataset used in the project.

## Demo

[Watch the project demonstration](https://drive.google.com/file/d/19XA9B5jUQgZKzPvs1q0qb2VEbdtkx3jz/view?usp=sharing)

## Project Report

The complete project report is available in `report/Coin_Counting_Classification_Report.pdf`.

## Acknowledgements

Dataset: [Count Coins Image Dataset on Kaggle](https://www.kaggle.com/datasets/balabaskar/count-coins-image-dataset)
