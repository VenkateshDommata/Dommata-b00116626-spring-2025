# **Dommata-b00116626-Spring-2025**

### **Dataset Information:**
As the dataset size is more than 2GB, you can access and download it from the following link:  
🔗 [Driver Drowsiness Dataset (DDD)](https://www.kaggle.com/datasets/ismailnasri20/driver-drowsiness-dataset-ddd?resource=download)

#### **Dataset Properties:**
- **RGB Images**
- **2 Classes:** Drowsy & Non-Drowsy
- **Image Size:** 227 x 227
- **Total Images:** More than 41,790
- **File Size:** 2.32 GB  

---

## **Project: Drowsiness Detection Model using Deep Learning**

I worked on building a **drowsiness detection model** using deep learning. The key steps I completed are:

### **1. Dataset Processing:**
- Loaded images of **open and closed eyes** from the dataset.
- Created a structured **DataFrame** to store **image paths and labels**.

### **2. Data Augmentation & Preprocessing:**
- Used `ImageDataGenerator` to apply augmentations (**rotation, brightness, flipping**) to improve generalization.
- Split the dataset into **training, validation, and test sets**.

### **3. Model Development:**
- Used **MobileNet** as the base model (**without top layers**) for feature extraction.
- Added **custom layers** and trained a **binary classification model** using:
  - **Adam optimizer**
  - **Binary cross-entropy loss**
  - **Early stopping & model checkpointing** to prevent overfitting.

### **4. Training & Evaluation:**
- Achieved **98.7% accuracy** on the **training set** and **98.6% validation accuracy**.
- Evaluated the model on the **test set**, achieving **84.8% test accuracy**.
- Generated a **confusion matrix** and **classification report** to analyze model performance.

### **5. Predictions:**
- Tested the model on a **new image**, and successfully classified it as **open eyes** with high confidence.

## **6. Eye Detection with Haar Cascade (OpenCV)**
This week, I integrated **eye detection** using **Haar cascades in OpenCV**.  

📌 **How it works:**
- Used the **haarcascade_eye.xml** classifier to detect eyes from the webcam in real-time.
- Captured frames, applied the classifier, and **highlighted detected eyes with green rectangles**.
- The system continues detection **until the 'q' key is pressed** to stop the webcam feed.

### **Code Breakdown:**
✔ **Initialization:**  
- The code accesses the **webcam** using `cv2.VideoCapture()`.  
- Haar cascade classifiers are loaded using `cv2.CascadeClassifier()`.  

✔ **Detection:**  
- Each **captured frame** is converted to **grayscale** for better accuracy.  
- The `detectMultiScale()` method detects **eyes**.

✔ **Output:**  
- The detected **eyes are highlighted** with rectangles.  
- The **resulting frame** is shown in a window.

## **7. Model Integration with OpenCV for Real-Time Eye State Detection**
📌 Integration Approach:

Successfully bridged the machine learning model with OpenCV's real-time video capture
Implemented a seamless workflow for eye detection and state classification

Technical Integration Process:
✔ Model Preparation:

Utilized a pre-trained neural network for binary eye state classification
Configured the model to work with live video stream inputs
Ensured compatibility between model input requirements and OpenCV frame capture

✔ Real-Time Processing Workflow:

Capture video frames using OpenCV's VideoCapture
Detect eye regions using Haar Cascade Classifier
Extract and preprocess detected eye regions for model prediction
Perform real-time classification of eye state

Preprocessing Steps:

Convert detected eye region to grayscale
Resize eye image to model's expected input dimension (224x224 pixels)
Normalize pixel values (scale to 0-1 range)
Add batch dimension for model input np.expand_dims()

Prediction Mechanism:
final_image = cv2.resize(eyes_roi, (224, 224))
final_image = np.expand_dims(final_image, axis=0)  # Add batch dimension
final_image = final_image / 255.0  # Normalize image

# Predict eye state
predictions = new_model.predict(final_image)
predicted_index = (predictions > 0.5).astype(int)[0, 0]
Visualization and Feedback:

Display eye state in real-time on video frame
Use color-coded text for different eye states:

Green for "Open Eyes"
Red for "Closed Eyes"
---

## **Next Steps:**

✅ **Frame Recognition Optimization:**  
- Fine-tuning the **frame rate** for better performance without excessive delays.  

✅ **Drowsiness Alert System:**  
- In the next phase, if the driver’s **eyes remain closed for too long**, the system will:  
  - **Trigger an alert sound (beep)** to warn the driver.  

