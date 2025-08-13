# CIFAR-10 CNN: With and Without Data Augmentation

This project shows the effect of **data augmentation** on improving the performance and generalisation of a Convolutional Neural Network (CNN) trained on the **CIFAR-10 dataset**.

We trained two CNN models:
1. **`model`** → Without data augmentation  
2. **`model_dataaugmentation`** → With data augmentation (rotation, shift, flip, zoom)

---

## 📌 Dataset
- **Dataset:** CIFAR-10
- **Classes:** 10 categories → airplane, automobile, bird, cat, deer, dog, frog, horse, ship, truck
- **Image size:** 32x32 pixels (RGB)

---

## 🛠️ Model Details
- **Architecture:** CNN with multiple convolutional and pooling layers
- **Activation:** ReLU
- **Regularisation:** **L1 regularisation**
- **Optimizer:** Adam
- **Loss Function:** Categorical Crossentropy
- **Callbacks:**
  - **EarlyStopping** → to stop training when no improvement is seen
  - **ReduceLROnPlateau** → to reduce learning rate when validation accuracy stops improving

---

## 🎯 Data Augmentation Settings (for `model_dataaugmentation`)
- rotation_range = 15
- width_shift_range = 0.1
- height_shift_range = 0.1
- horizontal_flip = True
- zoom_range = 0.1

---

## 📊 Results

| Model                 | Train Accuracy | Validation Accuracy | Test Accuracy |
|-----------------------|---------------:|--------------------:|--------------:|
| Without Augmentation  | 93.96%         | 85.90%              | 86.53%        |
| With Augmentation     | 96.82%         | 89.50%              | 88.36%        |

---

## 🔍 Observations
- Data augmentation improved **validation** and **test** accuracy, showing better generalisation.  
- Training accuracy is slightly higher in the augmented model because of better feature learning.  
- Overfitting reduced in the augmented model as the gap between training and validation accuracy is smaller.  

---

## 💾 Model Saving
Both models are saved for further use:

- `model.keras`
- `model_dataaugmentation.keras`

---

## 🚀 How to Run

**1. Clone the repository:**
git clone https://github.com/Nakshu35/CIFAR10-CNN-AUGMENTATION.git
cd CIFAR10-CNN-AUGMENTATION

**2. Install dependencies:**
pip install tensorflow numpy matplotlib

**3. Run the notebook:**
jupyter notebook CIFAR10_Classification.ipynb

---

## 📌 Conclusion
Data augmentation helps CNN models **generalise better** by training them with different versions of the same image.  

In this experiment:
- **Validation accuracy** improved by **+3.6%**
- **Test accuracy** improved by **+1.83%**

This shows that even simple augmentation techniques can make a big difference in model performance.

---