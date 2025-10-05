# Sign_Language
Hand Gesture Recognition (ASL) using MediaPipe
![demo1](https://github.com/Muskanpandey0304/Hand_Sign_Language/blob/main/images/demo_1.png)
![demo2](https://github.com/Muskanpandey0304/Hand_Sign_Language/blob/main/images/demo_1.png)

This project recognizes American Sign Language (ASL) hand signs and finger gestures in real time using MediaPipe (Python) and a simple MLP classifier.

Contents
- Sample demo program (app.py)
- Pre-trained models (TFLite) for hand sign and finger gesture recognition
- Training data and Jupyter notebooks for re-training models
- Utility for FPS calculation

Requirements
- mediapipe >= 0.8.1
- opencv >= 3.4.2
- tensorflow >= 2.3.0 (tf-nightly >= 2.5.0.dev for LSTM TFLite models)
- scikit-learn >= 0.23.2 (for confusion matrix)
- matplotlib >= 3.3.2 (for confusion matrix)

Run Demo
  - Run the sample using your webcam:
      - python app.py


Optional arguments:
- --device → camera ID (default: 0)
- --width / --height → capture size (default: 960x540)
- --use_static_image_mode → static image mode for inference
- --min_detection_confidence → detection threshold (default: 0.5)
- --min_tracking_confidence → tracking threshold (default: 0.5)

Training
Hand Sign Recognition
1. Collect training data (k to enable keypoint logging, 0-9 to save class ID).
→ Saved in model/keypoint_classifier/keypoint.csv
2. Train model by running keypoint_classification.ipynb.
3. Adjust NUM_CLASSES and keypoint_classifier_label.csv as needed.

Finger Gesture Recognition
1. Collect data (h to enable fingertip history logging, 0-9 for class ID).
→ Saved in model/point_history_classifier/point_history.csv
2. Train model by running point_history_classification.ipynb.
3. Adjust NUM_CLASSES and point_history_classifier_label.csv as needed.
4. LSTM-based model also supported (set use_lstm=True).

Reference
- MediaPipe
