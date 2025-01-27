# Deep Learning Powered Video Enhancement

This project utilizes deep learning techniques to enhance video visibility under challenging atmospheric conditions, improving both underexposure and overexposure issues.

## Features
- **Exposure Enhancement**: Corrects both underexposed and overexposed areas in frames using advanced algorithms like LIME and DUAL.
- **Spatial Affinity Optimization**: Applies Gaussian-based spatial affinity weights for refined illumination.
- **Multi-Exposure Fusion**: Enhances videos by fusing multiple exposure-corrected versions.
- **Video Processing**: Accepts videos as input and produces enhanced videos as output.

## Methods
### Existing
The **existing method** relies on traditional video processing techniques, which may lack precision under extreme atmospheric conditions. The output for the existing method can be found in:
- **`output_video_existing.avi`**

### Proposed
The **proposed method** leverages advanced deep learning algorithms like LIME and DUAL for improved video enhancement. It refines illumination maps and fuses exposure-corrected versions for superior visibility. The output for the proposed method is available in:
- **`output_video_proposed.avi`**

## Project Structure
```
.
├── input_videos/           # Directory for input videos
├── input_frames/           # Extracted frames from input videos
├── output_videos/          # Directory for enhanced videos
├── output_frames/          # Frames from enhanced videos
├── utils.py                # Utility functions, including neighbor calculation
├── exposure_enhancement.py # Core image and video enhancement functions
├── main_image.ipynb        # Notebook for testing image-based enhancement
├── Main_video.ipynb        # Notebook for video-based enhancement
└── requirements.txt        # Python dependencies
```

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/your_username/deep-video-enhancement.git
   cd deep-video-enhancement
   ```
2. Create a virtual environment and activate it:
   ```bash
   python -m venv venv
   source venv/bin/activate   # On Windows: venv\Scripts\activate
   ```
3. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Usage
### Image Enhancement
1. Open the `main_image.ipynb` notebook.
2. Run the cells to test enhancement on sample images.

### Video Enhancement
1. Place your videos in the `input_videos` directory.
2. Open the `Main_video.ipynb` notebook.
3. Run the cells to process videos and save the results in `output_videos`.

### Core Functions
The `exposure_enhancement.py` file contains the core functions:
- `enhance_image_exposure`: Main function for enhancing image exposure.
- `correct_underexposure`: Corrects underexposed regions.
- `fuse_multi_exposure_images`: Fuses corrected underexposure and overexposure maps.
- `create_spacial_affinity_kernel`: Builds the spatial affinity kernel for refinement.

### Example Command
```python
from exposure_enhancement import enhance_image_exposure
import cv2

image = cv2.imread('path_to_image.jpg')
enhanced_image = enhance_image_exposure(image, gamma=2.2, lambda_=0.5)
cv2.imwrite('enhanced_image.jpg', enhanced_image)
```

## Dependencies
- Python 3.8+
- OpenCV
- NumPy
- SciPy

Install dependencies with:
```bash
pip install numpy==1.21.6
```

## Outputs
- **`output_video_existing.avi`**: Enhanced video using the existing method.
- **`output_video_proposed.avi`**: Enhanced video using the proposed method.

## References
This project is inspired by the LIME and DUAL papers for illumination map refinement and multi-exposure fusion techniques.

## License
This project is licensed under the [MIT License](LICENSE).

---

Let me know if you’d like further refinements or additions!
