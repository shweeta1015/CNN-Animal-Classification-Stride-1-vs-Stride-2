# CNN Animal Classification: Stride 1 vs Stride 2

## Project Overview

This project implements animal image classification using a Convolutional Neural Network (CNN) and compares the effect of two different convolution strides: **Stride = 1** and **Stride = 2**.

The experiment uses the **CIFAR-100 dataset** and selects four animal classes:

- Beaver
- Dolphin
- Otter
- Seal

The main objective is to study how changing the convolution stride affects image feature extraction, spatial dimensions, computational efficiency, and classification performance.

---

## Dataset

The **CIFAR-100** dataset contains 60,000 color images belonging to 100 different classes.

- Training images: 50,000
- Testing images: 10,000
- Image size: 32 × 32 pixels
- Color channels: 3 (RGB)

For this project, only four animal classes were selected:

| Class | Original CIFAR-100 Label | New Label |
|---|---:|---:|
| Beaver | 4 | 0 |
| Dolphin | 30 | 1 |
| Otter | 55 | 2 |
| Seal | 72 | 3 |

Each selected class contains approximately 500 training images and 100 testing images.

---

## Data Preprocessing

The following preprocessing steps were performed:

1. Loaded the CIFAR-100 dataset.
2. Selected the four required animal classes.
3. Removed all other classes.
4. Remapped the class labels to 0, 1, 2, and 3.
5. Normalized pixel values from the range 0–255 to the range 0–1.

The normalization was performed using:

```python
x = x.astype("float32") / 255.0
CNN Architecture

The CNN consists of the following main layers:

Input Image (32 × 32 × 3)
        ↓
Convolution Layer
        ↓
ReLU Activation
        ↓
Max Pooling
        ↓
Convolution Layer
        ↓
ReLU Activation
        ↓
Max Pooling
        ↓
Convolution Layer
        ↓
ReLU Activation
        ↓
Max Pooling
        ↓
Flatten
        ↓
Dense Layer (128 neurons)
        ↓
Dropout (0.5)
        ↓
Softmax Output
        ↓
4 Animal Classes
Convolution

The convolution layer applies filters to the input image to extract important features such as:

Edges
Shapes
Textures
Patterns
ReLU Activation

ReLU introduces non-linearity into the CNN.

The ReLU function is:

ReLU(x) = max(0, x)

Negative values are converted to zero, while positive values remain unchanged.

Max Pooling

Max pooling reduces the spatial dimensions of feature maps while retaining important features.

Softmax

The final softmax layer produces probabilities for the four animal classes.

Stride

Stride represents the number of pixels by which the convolution filter moves across the input image.

Stride = 1

With stride = 1, the filter moves one pixel at a time.

Advantages:

Preserves more spatial information
Extracts features more densely
Can provide better detail

Disadvantage:

Requires more computation
Stride = 2

With stride = 2, the filter moves two pixels at a time.

Advantages:

Reduces feature-map dimensions faster
Can reduce computation
Can improve computational efficiency

Disadvantage:

May lose some fine spatial information
Models Used

Two CNN models were trained.

Model 1 — CNN with Stride = 1

All convolution layers use:

strides=(1,1)
Model 2 — CNN with Stride = 2

All convolution layers use:

strides=(2,2)

The remaining architecture and training settings are kept the same so that the effect of stride can be compared fairly.

Training Configuration

Both models were trained using:

Parameter	Value
Optimizer	Adam
Loss Function	Sparse Categorical Crossentropy
Metric	Accuracy
Epochs	10
Batch Size	64
Validation Split	10%
Number of Classes	4
Evaluation

The two CNN models are evaluated using:

Test Accuracy
Test Loss
Confusion Matrix
Precision
Recall
F1-Score
Training Time
Test Accuracy

Test accuracy measures the percentage of test images correctly classified by the model.

Confusion Matrix

The confusion matrix shows the relationship between actual and predicted classes.

The diagonal values represent correctly classified images, while values outside the diagonal represent incorrect classifications.

Classification Report

The classification report provides:

Precision
Recall
F1-score
Support

for each animal class.

Results

The final results are obtained directly from the Google Colab notebook.

Model	Test Accuracy	Test Loss	Training Time
CNN - Stride 1	To be updated	To be updated	To be updated
CNN - Stride 2	To be updated	To be updated	To be updated

The actual values should be updated after running the complete experiment.

Comparison

The experiment compares the two models based on:

Accuracy
Loss
Training Time
Confusion Matrix
Precision
Recall
F1-Score

Stride = 1 generally examines the image more densely because the filter moves one pixel at a time.

Stride = 2 moves the filter two pixels at a time, reducing the spatial dimensions more quickly and potentially reducing computation.

The better model is determined by the actual experimental results.

Project Structure
CNN-Animal-Classification-Stride-1-vs-Stride-2/
│
├── CNN_Animal_Classification_Stride_1_vs_Stride_2.ipynb
├── README.md
└── .gitignore
Technologies Used
Python
TensorFlow
Keras
NumPy
Matplotlib
Seaborn
Scikit-learn
Google Colab
GitHub
How to Run

Open the Jupyter Notebook:

CNN_Animal_Classification_Stride_1_vs_Stride_2.ipynb

Open it using Google Colab.
Run the cells sequentially from Cell 1 to Cell 29.
The CIFAR-100 dataset will be loaded automatically.
The four animal classes will be extracted.
Both CNN models will be trained.
The final accuracy, loss, confusion matrices, classification reports, and comparison graphs will be generated.
Conclusion

This project demonstrates the use of a Convolutional Neural Network for classifying four animal categories from the CIFAR-100 dataset.

The main purpose of the experiment is to compare Stride = 1 and Stride = 2.

Stride = 1 preserves more spatial information because the filter moves one pixel at a time, while Stride = 2 reduces the feature-map size more quickly and can reduce computational requirements.

Therefore, the selection of stride involves a trade-off between spatial information, computational efficiency, and classification performance
