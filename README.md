# 🧑‍💻Computer Vision

My computer vision assignments. Both notebooks were run on Colab. The datasets are not included.

## PA1 - Traffic Sign Detection

Detects circular traffic signs in a small GTSDB subset (50 images, 68 circular signs). I wrote both the Hough circle transform and RANSAC from scratch, ran them on Canny edges, and compared them using IoU-matched precision, recall and F1. The notebook also has a 3-level image pyramid with cross-scale NMS and a look at the failure cases.

Hough did much better (F1 0.30 vs 0.01). RANSAC was about 35x faster but fit circles to trees and other background clutter.

## PA2 - Single-Object Tracking

A ResNet18 regressor predicts the target box inside a search crop around the previous box. Each prediction becomes the search center for the next frame. Trained for 10 epochs with Smooth L1 loss and Adam.

On single crops it reaches about 0.70 validation IoU. Over full sequences the error builds up: mean IoU across the 11 validation sequences is 0.19. It does well on steady sequences like Man (0.81) and loses the target on fast or crowded ones like Basketball and Crowds.

The full submission, with weights and prediction CSVs, is on [Google Drive](https://drive.google.com/file/d/1O7QZFf4Adny6GeKEYU6TGrLZfrBrQ1cb/view?usp=sharing).
