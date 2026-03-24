🔐 FaceGuard: CNN-Based Facial Recognition for Access Control
📌 Overview

FaceGuard is an AI-powered facial recognition system developed as part of a Cybersecurity coursework. The system uses a Convolutional Neural Network (CNN) to identify individuals and control access to a secure server room.

This project demonstrates how deep learning can be applied to real-world cybersecurity scenarios, specifically identity verification and access control.

🎯 Key Features
🔍 Facial recognition using a custom CNN model
🧠 Classification of 40 unique individuals
📊 Training and evaluation using a real dataset
🔐 Access control system for authorised personnel
📉 Performance tracking with accuracy and loss metrics
🧠 Model Architecture

The CNN model is implemented using PyTorch and is designed for grayscale facial images (64×64).

Architecture Highlights:
Multiple Convolutional layers for feature extraction
ReLU activation to introduce non-linearity
MaxPooling layers to reduce spatial dimensions
Fully connected layers for classification
Output layer with 40 classes
Design Rationale:

CNNs are well-suited for image recognition tasks due to their ability to capture spatial hierarchies in data. Using grayscale images reduces computational cost while maintaining essential facial features. Pooling layers help improve generalisation, and fully connected layers enable accurate classification across multiple identities.

📊 Dataset
Dataset: Augmented Olivetti Faces Dataset
Classes: 40 individuals
Image Format: Grayscale (64×64)
Preprocessing:
Normalised pixel values to range [0,1]
Reshaped to (N, 1, 64, 64)
Stratified train-test split (80/20)
⚙️ Training Details
Framework: PyTorch
Loss Function: CrossEntropyLoss
Optimiser: Adam
Training Process:
Data loaded using PyTorch DataLoader
Model trained over multiple epochs
Validation performed during training
Performance evaluated using accuracy metrics
📈 Results
Test Accuracy: 98.75%
Analysis:

The model performs well in recognising most individuals. Some misclassifications occur between visually similar faces, which is expected in facial recognition systems. Overall, the model demonstrates strong capability for identity-based classification.

📉 Performance Visualisation

The project includes:

Training vs validation loss curves
Accuracy curves across epochs

These visualisations help in understanding model performance and detecting overfitting.

🔑 Access Control System

A function check_access() is implemented to simulate a real-world security system.

Authorised Personnel:

{0, 5, 10}

Function Behaviour:
Takes an input face image
Predicts the identity using the trained CNN
Outputs:
✅ Access Granted (authorised users)
❌ Access Denied (unauthorised users)
🧪 Testing

The system is tested on multiple images, including both authorised and unauthorised individuals, to validate correct access decisions.

💡 Future Improvements
Implement deeper architectures (e.g., ResNet)
Add real-time face recognition using a webcam
Improve accuracy with larger datasets
Integrate face detection before recognition
