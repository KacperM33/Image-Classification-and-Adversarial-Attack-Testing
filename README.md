# 🖼️ Image Classification and Adversarial Attack Testing
The goal of this project was to explore image recognition using **Convolutional Neural Networks (CNNs)** and to understand how **Adversarial Attacks** affect **Neural Network Models**.

> ❕ This project was implemented using the **Google Colaboratory** environment. It is recommended to use this environment for correct installation and correct use of packages.

> Note: *README provides an **English** overview of the project content and results. All folders and file names are also in **English** to ensure clarity for international readers. 
However, the notebook itself contains comments and output descriptions in **Polish.***

## 🧰 Development Tools
- Python 3.12.2
- [TensorFlow](https://www.tensorflow.org)
- [Google Colab](https://colab.research.google.com) (Jupyter Notebook)
- [CIFAR-10 / CIFAR-100](https://www.cs.toronto.edu/~kriz/cifar.html) (Dataset with 60000 32x32 images of 10 or 100 classes.)
- [CleverHans](https://github.com/cleverhans-lab/cleverhans) (For adversarial attack)

## 📊 Results
### 🧠 Neural Network:
For testing adversarial attacks, a model was trained on the **CIFAR-10** dataset using **TensorFlow**.
The model file is named `cifar10_73.keras` and has the following architecture:
- Input Convolutional Layer (32 filters)
- 4 Convolutional Layers (64, 128, 256, 256 filters)
- 3 MaxPooling Layers (2x2 pool size)
- Global Average Pooling Layer
- Dense Layer (128 units)
- Output Dense Layer (10 units for 10 classes)

  ![image](https://github.com/user-attachments/assets/929dc5dd-e098-46b9-ae76-22d8f4913868)

### ⚔️ Adversarial Attacking:
For adversarial attack, the **Fast Gradient Sign Method (FGSM)** from the CleverHans library was used.

**FGSM** – The main goal of this attack is to introduce small but intentionally crafted perturbations to 
the input data in order to fool the model. **FGSM** achieves this by using the gradient of the loss function 
with respect to the input, generating adversarial examples that lead the model to make incorrect predictions.

### 1️⃣ First test:
In the first test, an image of a deer with size of 32x32 pixels was used. 
<br>This image size was used to match the input format expected by the model trained on the **CIFAR-10** dataset, which contains images of this resolution.

<div align="center">
  
  ![image](https://github.com/user-attachments/assets/c4d9544e-b5f6-4594-b6f8-6bda4ee5fca5)

</div>

**Left** – Original photo correctly recognized as a **deer** with 96.34% accuracy. <br>
**Right** – Photo after perturbations incorrectly recognized as a **dog** with 38.05% accuracy.

### 2️⃣ Second test:
In the second test, an image of a deer with size of 512x512 pixels was used. 
<br>This larger image was chosen to better illustrate how perturbations appear on a high-resolution image. 
<br>After that, the image was resized to 32x32 pixels to match the input format expected by the model trained on the **CIFAR-10** dataset, which contains images of this resolution.

<div align="center">
  
  ![image](https://github.com/user-attachments/assets/e74b08a1-33a4-4228-85f3-0599312855f5)

</div>

**Left** – Original photo correctly recognized as a **deer** with 95.94% accuracy. <br>
**Right** – Photo after perturbations incorrectly recognized as a **turtle** with 48.77% accuracy.

### 3️⃣ Third test:
In the third test, an image of a deer with size of 512x512 pixels was used. 
<br>The adversarial attack was applied after the image had been resized to 32x32 pixels to match the input format expected by the model trained on the **CIFAR-10** dataset, which contains images of this resolution.

<div align="center">
  
  ![image](https://github.com/user-attachments/assets/9ca29754-c9f7-424b-9274-d5a4917aa8d6)
  
</div>

**Left** – Original photo. <br>
**Center** - Original photo after resized to 32x32 pixels correctly recognized as a **deer** with 95.94% accuracy. <br>
**Right** – Photo after perturbations incorrectly recognized as a **hedgehog** with 86.12% accuracy.

## ✍️ Conclusion
- **In the first test**. a perturbation with *epsilon = 0.02*, which was sufficient to fool the model. The result **was satisfactory**, both images are very similar and difficult to distinguish by a human, yet the perturbation managed to deceive the model. ✔️
  
- **In the second test**, a perturbation with *epsilon = 0.8* was the minimal value that successfully fooled the model. The result **was unsatisfactory**, since the images were visibly different and easy for a human to distinguish, making it trivial for the model to be fooled. ❌
  
- **In the third test**, a perturbation with *epsilon = 0.02* was used again. As in the first test, the result **was satisfactory**, the images are very similar and difficult to distinguish by a human, but the model was still successfully fooled by the perturbation. ✔️

> Note: Increasing the value of **epsilon** amplified the strength of the attack, but it also made the images more distinguishable to a human observer.

## 📂 Project Structure

📦 Image-Classification-and-Adversarial-Attack-Testing <br>
├── 📄 **README.md** -- *Project documentation <br>*
├── 📊 **ImgClassification_and_AdvAttacks.ipynb** -- *Main notebook <br>*
└── 📂 **Models** -- *Folder with trained models <br>*
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── 📄 **cifar10_73.keras** -- *Model of trained model for CIFAR-10 with 73% accuracy<br>*
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└── 📄 **...** -- *Other models <br>*
└── 📂 **Images** -- *Folder with images for testing <br>*
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├── 📄 **deer.jpg** -- *Image of deer<br>*
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└── 📄 **...** -- *Other images <br>*


Images to testing was generated with AI ([Grok](https://x.com/i/grok)).
