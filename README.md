# 🧑‍💻Computer Vision

Computer vision assignments as Jupyter notebooks. The datasets are not included.

## PA1 - Traffic Sign Detection

Detects circular traffic signs in a GTSDB subset. I implemented the Hough circle transform and RANSAC from scratch on top of Canny edges, then compared them with IoU-based precision, recall and F1. The notebook also covers multi-scale detection with cross-scale NMS and a failure analysis.

Hough clearly did better (F1 0.30 vs 0.01). RANSAC was about 35 times faster but fit circles to background clutter.

## PA2 - Single-Object Tracking

A ResNet18 regressor predicts the target box inside a search region around the previous box. Each prediction becomes the search center for the next frame. It reaches about 0.70 IoU on single crops. Over full sequences the errors add up, giving a mean IoU of 0.19, though it tracks steady sequences such as Man well (0.81).

The full submission, including the trained weights and prediction files, is on [Google Drive](https://drive.google.com/file/d/1O7QZFf4Adny6GeKEYU6TGrLZfrBrQ1cb/view?usp=sharing).
