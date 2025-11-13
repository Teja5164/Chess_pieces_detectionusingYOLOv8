# Chessboard Position Recognition with YOLOv8

This repository contains a project to automatically detect chess pieces on a chessboard image using a trained YOLOv8 model, transform detections into a standardized board position, and generate Forsyth-Edwards Notation (FEN) strings representing the chessboard state.

***

## Features

- Upload and use a custom-trained YOLOv8 model for chess piece detection
- Detect and warp chessboard images to a fixed top-down view for uniform processing
- Map detected pieces to the corresponding squares on the chessboard grid
- Generate valid FEN strings encoding the entire board position from detections
- Save FEN strings to files for further use or analysis
- Fully implemented in Google Colab for easy use and reproducibility

***

## Setup and Usage

1. **Install dependencies**:

   Run the command below in Colab or your Python environment to install required packages:

   ```bash
   pip install ultralytics python-chess opencv-python-headless matplotlib
   ```

2. **Upload your YOLOv8 model and images**:

   Upload your `.pt` model file and chessboard images (`.jpg`) directly into the notebook via file upload prompts.

3. **Run the detection and FEN generation pipeline**:

   - Detect and warp the chessboard in each image
   - Run YOLOv8 piece detection on the warped image
   - Map detections to board squares and generate the FEN string
   - Print and save the FEN string for each image

4. **Download the generated FEN files** for use in chess applications, analysis, or review.

***

## Project Structure

- **Model loading and inference**: Loads your YOLOv8 `.pt` model and runs detection on input images.
- **Board detection and warping**: Identifies and warps chessboard region to a fixed-size image.
- **Piece mapping**: Maps YOLOv8 detected pieces to the chessboard's 8x8 grid.
- **FEN generation**: Converts mapped pieces into FEN notation.
- **File I/O**: Saves FEN strings to individual `.fen` files per image.

***

## Notes

- Images should ideally be clear, top-down views of the chessboard for best accuracy.
- Warping step assumes the largest contour corresponds to the chessboard for perspective correction.
- The piece class to FEN character mapping depends on your YOLOv8 model training classes; adjust accordingly.
- The FEN output assumes white to move and no castling or en passant rights; extend as needed.

***

## Credits

- YOLOv8 by Ultralytics ([GitHub](https://github.com/ultralytics/ultralytics))
- OpenCV for image processing
- Python-Chess for FEN validation and chess utilities

***
