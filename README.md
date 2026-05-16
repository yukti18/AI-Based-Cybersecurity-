# 🔐 FaceGuard – AI Facial Recognition Security System

### CNN-Based Access Control with Adversarial Attack & Defence Analysis

## 📌 Overview

FaceGuard is an AI-powered facial recognition and access control system developed as part of MSc Applied Cyber Security coursework at Queen’s University Belfast.

The project demonstrates how deep learning can be applied to real-world cybersecurity scenarios, specifically identity verification and secure access control. The system was later extended with a full AI security assessment involving adversarial attacks, model stealing, transferability analysis, and adversarial defence mechanisms.

This repository combines:

* Facial Recognition System Development (CW1)
* AI Security Assessment & Defence (CW2)

# 🎯 Key Features

## 🧠 Facial Recognition System

* CNN-based facial recognition using PyTorch
* Classification of 40 unique individuals
* Access control for authorised personnel
* Training and evaluation using the Augmented Olivetti Faces Dataset
* Performance visualisation with accuracy and loss curves

## 🛡️ AI Security Assessment

* Black-box model stealing attack
* FGSM adversarial attacks
* PGD adversarial attacks
* Targeted impersonation attack
* Transferability analysis
* Adversarial training defence
* Robustness evaluation against attacks

# 🧠 Model Architecture

The FaceGuard model is implemented using a Convolutional Neural Network (CNN) designed for grayscale facial recognition tasks.

## Architecture Highlights

* Multiple convolutional layers for feature extraction
* ReLU activation functions
* MaxPooling layers for dimensionality reduction
* Fully connected layers for classification
* Output layer with 40 classes

## Design Rationale

CNNs are highly effective for image recognition tasks because they capture spatial hierarchies within images. Using grayscale images reduces computational cost while preserving essential facial features.

Pooling layers improve generalisation, and fully connected layers enable accurate identity classification.

# 📊 Dataset

## Dataset Used

* Augmented Olivetti Faces Dataset

## Dataset Details

* 40 individuals/classes
* Grayscale facial images
* Image size: 64×64

## Preprocessing

* Normalised pixel values to range [0,1]
* Reshaped images to (N, 1, 64, 64)
* Stratified train-test split (80/20)

# ⚙️ Technologies Used

* Python
* PyTorch
* NumPy
* Matplotlib
* Scikit-learn
* Jupyter Notebook
  
# 🔐 Access Control System

A custom `check_access()` function simulates a real-world server room access system.

## Authorised Personnel

```python
{0, 5, 10}
```

## Function Behaviour

* Takes an input face image
* Predicts identity using the trained CNN
* Grants or denies access based on predicted ID

### Outputs

* ✅ Access Granted
* ❌ Access Denied

# 📈 Model Performance

## CW1 Results

* Test Accuracy: 98.75%

## Analysis

The CNN performs strongly in recognising authorised and unauthorised individuals. Minor misclassifications occur between visually similar faces, which is expected in facial recognition systems.

# 🛡️ AI Security Assessment (CW2)

The project was extended with a complete Red Team / Blue Team security assessment to evaluate the robustness of the FaceGuard system against adversarial machine learning attacks.

# 🔴 Red Team – Model Stealing Attack

A black-box model stealing attack was implemented where the attacker had query-only access to the deployed model.

## Objectives

* Query the victim model
* Build a surrogate dataset
* Train a proxy model to mimic the victim system

## Results

* Successfully trained a proxy model capable of approximating victim behaviour
* Demonstrated risks associated with exposed AI prediction APIs

# 🔴 Adversarial Attacks

Implemented adversarial attacks against the proxy model using:

## FGSM (Fast Gradient Sign Method)

* Single-step gradient-based attack
* Fast but less powerful

## PGD (Projected Gradient Descent)

* Iterative gradient-based attack
* Stronger and more effective than FGSM

## Evaluations

* Robust accuracy vs epsilon analysis
* Accuracy degradation plots
* Attack effectiveness comparison

# 🎭 Targeted Impersonation Attack

A targeted adversarial attack was performed where an unauthorised individual was manipulated to be classified as the CEO (ID = 0).

## Security Implication

This demonstrates how adversarial perturbations can potentially bypass AI-based access control systems.

# 🔁 Transferability Analysis

Adversarial examples generated on the proxy model were tested against the original victim model.

## Findings

* Adversarial examples successfully transferred between models
* Transferability effectiveness increased with epsilon
* PGD attacks generally achieved higher transfer success

# 🔵 Blue Team – Adversarial Training Defence

A robust version of FaceGuard was developed using adversarial training.

## Defence Strategy

* Generate adversarial examples during training
* Train the model on both clean and adversarial samples

## Results

* Improved robustness against FGSM and PGD attacks
* Reduced vulnerability to transferability attacks
* Demonstrated the tradeoff between clean accuracy and robustness

# 📉 Performance Visualisations

The project includes:

* Training and validation loss curves
* Accuracy curves across epochs
* Robustness vs epsilon plots
* Adversarial image visualisations
* Perturbation analysis

These visualisations help analyse attack effectiveness and defence performance.

# 🧪 Testing

The system was tested using:

* Clean facial images
* Adversarial examples
* Transferability evaluations
* Robustness assessments

Both authorised and unauthorised users were evaluated to validate access control behaviour.


# 💡 Future Improvements

* Implement deeper architectures (ResNet, EfficientNet)
* Add real-time webcam-based recognition
* Integrate face detection before recognition
* Explore certified adversarial robustness techniques
* Deploy as a secure web application
* Implement explainable AI techniques


# 📚 Learning Outcomes

This project provided practical experience in:

* Deep Learning
* Computer Vision
* AI Security
* Adversarial Machine Learning
* Red Team / Blue Team Methodologies
* Secure AI System Design
* Cybersecurity Risk Analysis

---

# 👤 Author

Yukti Ogare
MSc Applied Cyber Security
Queen’s University Belfast

---

# 📜 Academic Context

This project was developed as part of the CyberAI module coursework at Queen’s University Belfast.

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

👤 Author

Yukti Ogare
AI & Cybersecurity Student
