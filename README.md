# Dommata-b00116626-spring-2025

As the dataset size is more than 2GB, you can access and download the dataset from the following link:
https://www.kaggle.com/datasets/ismailnasri20/driver-drowsiness-dataset-ddd?resource=download

The dataset has the following properties :
• RGB images
• 2 classes (Drowsy & Non Drowsy)
• Size of image : 227 x 227
• More than 41,790 images in total
• File size : 2.32 Go

I worked on building a **drowsiness detection model** using deep learning. The key steps I completed are:  

1. **Dataset Processing:**  
   - Loaded images of open and closed eyes from the dataset.  
   - Created a structured DataFrame to store image paths and labels.  

2. **Data Augmentation & Preprocessing:**  
   - Used `ImageDataGenerator` to apply augmentations (rotation, brightness, flipping) to improve generalization.  
   - Split the dataset into **training, validation, and test sets**.  

3. **Model Development:**  
   - Used **MobileNet** as the base model (without top layers) for feature extraction.  
   - Added custom layers and trained a binary classification model using **Adam optimizer** with **binary cross-entropy loss**.  
   - Used **early stopping and model checkpointing** to prevent overfitting.  

4. **Training & Evaluation:**  
   - Achieved **98.7% accuracy** on the training set and **98.6% validation accuracy**.  
   - Evaluated the model on the test set, achieving **84.8% test accuracy**.  
   - Generated a **confusion matrix** and **classification report** to analyze model performance.  

5. **Predictions:**  
   - Tested the model on a new image and successfully classified it as **open eyes** with high confidence.
     
6. **Eye Detection with Haar Cascade:**

This week, I integrated the functionality for eye detection using Haar cascades in OpenCV.
I used the haarcascade_eye.xml classifier to detect eyes from the webcam in real-time. The system captures frames, applies the classifier, and highlights the detected eyes with green rectangles on the live webcam feed.
The code continuously detects eyes until the 'q' key is pressed to stop the webcam feed.

**Code Breakdown:**

Initialization: The code accesses the webcam using cv2.VideoCapture(), and Haar cascade classifiers are loaded using cv2.CascadeClassifier().
Detection: Each captured frame is converted to grayscale for better detection accuracy, and the detectMultiScale() method is used to detect eyes.
Output: The detected eyes are highlighted with rectangles, and the resulting frame is shown in a window.

**Next Steps:**

Real-Time Eye Status Detection: We aim to enhance this system by implementing real-time eye status detection to classify whether the eyes are open or closed.
Frame Recognition Time: The frame rate for detection will be fine-tuned to ensure optimal performance without excessive delays.
Alert System: In the next phase, if the driver’s eyes are continuously closed (indicating drowsiness), the system will sound an alert (beep) to warn the driver.

