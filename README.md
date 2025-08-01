# Face Recognition System

![Python](https://img.shields.io/badge/Python-3.7%2B-blue)
![OpenCV](https://img.shields.io/badge/OpenCV-4.5%2B-orange)
![Face_Recognition](https://img.shields.io/badge/Face_Recognition-1.3%2B-green)
![License](https://img.shields.io/badge/License-MIT-yellow)

A face recognition system that detects and recognizes faces in real-time using a webcam or from static images. This system can be used for attendance tracking, security systems, or any application requiring facial identification.

## Features

- Real-time face detection and recognition
- Multiple face recognition in a single frame
- Simple training module to add new faces
- High accuracy with deep learning models
- Cross-platform (Windows, Linux, macOS)
- Easy-to-use command line interface

## Requirements

- Python 3.7+
- OpenCV
- face-recognition library
- numpy
- dlib (with CUDA support recommended for better performance)

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/face-recognition-system.git
   cd face-recognition-system
   ```

2. Install the required packages:
   ```bash
   pip install -r requirements.txt
   ```

   For better performance with dlib, consider installing CUDA-enabled version:
   ```bash
   pip install dlib --install-option="--yes" --install-option="USE_AVX_INSTRUCTIONS" --install-option="USE_NEON_INSTRUCTIONS"
   ```

## Usage

### Training the Model

1. Add images of faces to recognize in the `training_images` folder
   - Create subfolders with the person's name
   - Add multiple images (different angles/lighting) for better accuracy

2. Run the training script:
   ```bash
   python train_model.py
   ```

   This will generate an `encodings.pickle` file containing facial encodings.

### Running the Recognition System

For real-time recognition from webcam:
```bash
python recognize_faces.py
```

For recognizing faces in an image:
```bash
python recognize_faces.py --image path_to_image.jpg
```

### Command Line Arguments

- `--camera` : Specify camera index (default: 0)
- `--image` : Path to input image file
- `--tolerance` : Tolerance for face recognition (lower is stricter, default: 0.6)
- `--display-name` : Display recognized names (default: True)

## Project Structure

```
face-recognition-system/
├── training_images/          # Folder for training images
├── encodings.pickle          # Generated facial encodings
├── train_model.py            # Script to train the model
├── recognize_faces.py        # Main recognition script
├── face_utils.py             # Utility functions
├── requirements.txt          # Python dependencies
└── README.md                 # This file
```

## Performance Tips

1. Use good lighting conditions for better recognition
2. Add multiple training images with different expressions/angles
3. For large datasets, consider using GPU acceleration
4. Adjust tolerance level based on your needs

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any improvements.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Thanks to the developers of dlib and face-recognition libraries
- Inspired by various open-source face recognition projects
