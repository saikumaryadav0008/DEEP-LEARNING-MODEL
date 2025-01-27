# Deep Learning Powered Video Enhancement

## Project Overview

This project focuses on enhancing video quality using advanced deep learning and image processing techniques. It is specifically designed to improve visibility and atmospheric conditions in videos, making them clearer and more vibrant under challenging environments such as low light or haze.

## Features

- **Exposure Correction**: Adjusts both underexposed and overexposed areas in video frames.
- **Multi-Exposure Fusion**: Uses Mertens' fusion technique for seamless blending of exposure corrections.
- **Illumination Map Optimization**: Refines brightness adjustments for natural-looking enhancements.
- **Customizable Parameters**: Allows control over contrast, saturation, and other visual properties.
- **Comparative Results**: Provides visual comparisons between existing and proposed enhancement methods.

## Project Structure

```plaintext
.
├── utils.py                      # Utility functions for matrix operations
├── exposure_enhancement.py       # Core algorithms for video enhancement
├── Main_video.ipynb              # Jupyter notebook for video processing and visualization
├── output_video_existing.avi     # Output video from existing enhancement methods
├── output_video_proposed.avi     # Output video from the proposed enhancement method
```

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your_username/video-enhancement.git
   ```
2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

### 1. Enhance Videos
Run the `Main_video.ipynb` notebook to process and enhance videos step by step. This notebook demonstrates the use of the enhancement functions and visualizes the results.

### 2. Enhance Images
Use the `exposure_enhancement.py` script for image processing:
- Key function: `enhance_image_exposure`
  ```python
  enhance_image_exposure(im, gamma, lambda_, dual=True, sigma=3, bc=1, bs=1, be=1)
  ```
  - `im`: Input image
  - `gamma`, `lambda_`: Parameters for brightness and contrast
  - `dual`: Whether to use DUAL (True) or LIME (False) methods
  - `sigma`: Gaussian weight for spatial affinity
  - `bc`, `bs`, `be`: Weights for contrast, saturation, and well-exposedness

### 3. Compare Results
- View `output_video_existing.avi` and `output_video_proposed.avi` for a side-by-side comparison of video enhancement methods.

## Examples

Here is a comparison of results:

| **Existing Method**       | **Proposed Method**       |
|---------------------------|---------------------------|
| ![Existing](example1_existing.jpg) | ![Proposed](example1_proposed.jpg) |

## Key Functions

- **`create_spacial_affinity_kernel`**: Generates Gaussian kernels for spatial weights.
- **`fuse_multi_exposure_images`**: Combines images with different exposures for optimal visual quality.
- **`refine_illumination_map_linear`**: Refines the brightness adjustment using optimization techniques.
- **`correct_underexposure`**: Corrects dim areas in images using retinex-based algorithms.
- **`enhance_image_exposure`**: Main function for exposure and illumination enhancement.

## Results

The proposed method significantly improves visibility and clarity in challenging conditions, such as:
- Low-light scenes
- Foggy or hazy environments
- Backlit subjects

## Future Work

- Incorporate real-time processing using deep learning models.
- Extend support to extreme environmental conditions like rain or snow.
- Optimize performance for high-resolution videos.

## References

1. **DUAL Method**: A multi-exposure fusion-based approach for video enhancement.
2. **LIME Method**: Illumination map optimization for enhancing visual quality in natural videos.

---

Feel free to contribute to this project by submitting issues or pull requests. Together, let's make videos clearer and more visually stunning!

