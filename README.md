# 🖼️ Image Classification and Adversarial Attack Testing

❕ This project was implemented using the **Google Colaboratory** environment. It is recommended to use this environment for correct installation and correct use of packages.

## 📚 About This Project
Note: *README provides an **English** overview of the project content and results. All folders and file names are also in **English** to ensure clarity for international readers. 
However, the notebook itself contains comments and output descriptions in **Polish.***

## 🧰 Development Tools
- Python 3.12.2
- [TensorFlow](https://www.tensorflow.org)
- [Google Colab](https://colab.research.google.com) (Jupyter Notebook)
- [CIFAR-10 / CIFAR-100](https://www.cs.toronto.edu/~kriz/cifar.html) (Dataset with 60000 32x32 images of 10 or 100 classes.)
- [Cleverhans](https://github.com/cleverhans-lab/cleverhans) (For adversarial attack test)

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


### 1️⃣ First test:

![image](https://github.com/user-attachments/assets/c4d9544e-b5f6-4594-b6f8-6bda4ee5fca5)

### 2️⃣ Second test:
  
![image](https://github.com/user-attachments/assets/e74b08a1-33a4-4228-85f3-0599312855f5)

### 3️⃣ Third test:
  
![image](https://github.com/user-attachments/assets/9ca29754-c9f7-424b-9274-d5a4917aa8d6)

## ✍️ Conclusion

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
