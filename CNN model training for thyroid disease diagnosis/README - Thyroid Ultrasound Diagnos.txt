README - Thyroid Ultrasound Diagnosis with CNN

This guide will help you run a Convolutional Neural Network (CNN) that classifies thyroid ultrasound images as benign or malignant.  
Step 1: Prerequisites

We will use Google Colab, which does not require installation. Just ensure you have a Google account.

Required Python packages (Colab will install them automatically):
- tensorflow
- seaborn
- scikit-learn
- opencv-python
- matplotlib

Step 2: Connect to Google Drive

We store and load data directly from Google Drive. Run the following code cell in Colab:

from google.colab import drive
drive.mount('/content/drive')
Step 3: Folder Structure

Place your images in the following folder structure inside your Google Drive:

/MyDrive/ulstrasound images/
  ├── train/
  │   ├── benign/
  │   └── malignant/
  ├── val/
  │   ├── benign/
  │   └── malignant/
  └── test/
      ├── benign/
      └── malignant/

Step 4: Run the Full Code

Now run the full code provided in order. It will:
- Load and preprocess the data
- Build and train the CNN using EfficientNetB3
- Show training results (accuracy, loss)
- Evaluate performance (confusion matrix, ROC curve, classification report)
- Generate Grad-CAM visual explanations

Step 5: Interpreting Results

After training, the notebook will automatically show:
- Accuracy and loss plots for training and validation
- Confusion matrix: compares predicted vs actual labels
- ROC curve and AUC value: measures overall performance
- Grad-CAM overlays: highlights regions the model used to make decisions

Step 6: Save the Model

The trained model will be saved as a .h5 file:
    model.save('efficientnetb3.h5')

You can later load this file to make predictions from a web application.

Final Note

This project uses deep learning for educational and research purposes.
Ensure you use medically validated datasets for real-world applications.
