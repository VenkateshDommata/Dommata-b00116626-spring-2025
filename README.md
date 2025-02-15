# Dommata-b00116626-spring-2025

As the dataset size is more than 2GB, you can access and download the dataset from the following link:
https://www.kaggle.com/datasets/ismailnasri20/driver-drowsiness-dataset-ddd?resource=download

The dataset has the following properties :
• RGB images
• 2 classes (Drowsy & Non Drowsy)
• Size of image : 227 x 227
• More than 41,790 images in total
• File size : 2.32 Go

This week, I worked on building a **drowsiness detection model** using deep learning. The key steps I completed are:  

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

Next Steps: Further fine-tune the model to improve test accuracy and optimize for real-time inference.  

