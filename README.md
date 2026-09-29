# 🧠 MNIST Handwritten Digit Classification using CNN

A Deep Learning project that uses a Convolutional Neural Network (CNN) to classify handwritten digits from **0 to 9** using the MNIST dataset.

The model achieved **99.06% accuracy on the unseen MNIST test dataset** and was also tested with a custom handwritten digit image.

## 📌 Project Overview

The goal of this project is to build a CNN that can automatically recognize handwritten digits.

The complete workflow includes:

**Dataset → Preprocessing → CNN → Training → Validation → Testing → Prediction**

## 📊 Dataset

The MNIST dataset contains:

* 60,000 training images
* 10,000 testing images
* Image size: 28 × 28 pixels
* Grayscale images
* 10 classes: digits 0–9

Each pixel initially has a value between **0 and 255**.

The images were normalized to:

```text
0–255 → 0–1
```

## 🧠 CNN Architecture

The model consists of:

```text
Input: 28 × 28 × 1
        ↓
Conv2D (32 filters, 3×3)
        ↓
MaxPooling2D (2×2)
        ↓
Conv2D (64 filters, 3×3)
        ↓
MaxPooling2D (2×2)
        ↓
Flatten
        ↓
Dense (128, ReLU)
        ↓
Dense (10, Softmax)
```

### Model Parameters

* Total parameters: **225,034**
* Trainable parameters: **225,034**
* Non-trainable parameters: **0**

## ⚙️ Training Configuration

**Optimizer:** Adam

**Loss Function:** Sparse Categorical Crossentropy

**Metric:** Accuracy

**Epochs:** 5

A validation split of 10% was used during training.

## 📈 Results

| Metric              |     Result |
| ------------------- | ---------: |
| Training Accuracy   |     99.46% |
| Validation Accuracy |     99.07% |
| Test Accuracy       | **99.06%** |
| Test Loss           |     0.0298 |

The model achieved **99.06% accuracy on 10,000 unseen test images**.

## ✍️ Custom Image Prediction

After training, the model was also tested with a custom handwritten digit image.

The custom image was:

1. Converted from RGB to grayscale
2. Resized to 28 × 28 pixels
3. Normalized from 0–255 to 0–1
4. Reshaped to match the CNN input format
5. Passed through the trained model
6. Classified using the highest predicted probability

## 💾 Model Saving

The trained model was saved using the Keras format:

```text
mnist_cnn.keras
```

The saved model can be loaded later without retraining:

```python
model = tf.keras.models.load_model("mnist_cnn.keras")
```

## 🛠️ Technologies Used

* Python
* TensorFlow
* Keras
* NumPy
* Matplotlib
* Pillow
* Jupyter Notebook

## 📁 Project Structure

```text
mnist-digit-classification/
│
├── mnist_cnn.ipynb
├── mnist_cnn.keras
├── my_digit.png
└── README.md
```

## 🎯 Key Learning Outcomes

Through this project, I practiced:

* CNN architecture
* Image preprocessing
* Pixel normalization
* Convolution and pooling
* ReLU and Softmax activation functions
* Model training and validation
* Loss and accuracy evaluation
* Making predictions with a trained model
* Saving and loading Keras models
* Custom image preprocessing

## 🚀 Future Improvements

Possible improvements include:

* Confusion matrix analysis
* Data augmentation
* Hyperparameter tuning
* Testing additional CNN architectures
* Building an API for digit prediction
* Creating a web interface for handwritten digit recognition

## 👨‍💻 Project

This project was built as part of my Deep Learning learning journey, progressing from fundamental neural networks toward practical AI applications.
