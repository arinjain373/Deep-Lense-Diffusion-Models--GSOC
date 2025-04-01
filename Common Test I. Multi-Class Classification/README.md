# **Deep-Lense**
# Common Test I: Multi-Class Classification

## Task
Develop a deep learning model to classify images into different lens types using **PyTorch** or **Keras**. The most appropriate approach is selected, and the strategy is discussed.

---

## Dataset Description
The dataset consists of three classes:
- **No Substructure**
- **Subhalo Substructure**
- **Vortex Substructure**

**Dataset Split:**
- **Training Data:** 10,000 images per class (**Total: 30,000** images)
- **Validation Data:** 2,500 images per class (**Total: 7,500** images)
- **Train-Test Split:** 90:10
- **Preprocessing:** Min-max normalization (Additional normalization and augmentation techniques can be applied for better performance)

---

## Evaluation Metrics
The model performance is evaluated using:
- **ROC Curve (Receiver Operating Characteristic Curve)**
- **AUC Score (Area Under the ROC Curve)**

---

## Models and AUC Scores
The following models were fine-tuned and evaluated:

### **VGG16**
![VGG16 Performance](deep%20lense%20vgg16.png)
- **No Substructure:** AUC = **0.89**
- **Subhalo Substructure:** AUC = **0.77**
- **Vortex Substructure:** AUC = **0.79**

### **ResNet50**
![ResNet50 Performance](deep%20lense%20resnet50.png)
- **No Substructure:** AUC = **0.87**
- **Subhalo Substructure:** AUC = **0.75**
- **Vortex Substructure:** AUC = **0.78**

### **EfficientNetB0**
![EfficientNetB0 Performance](deep%20lense%20efficientnetB0.png)
- **No Substructure:** AUC = **0.49**
- **Subhalo Substructure:** AUC = **0.50**
- **Vortex Substructure:** AUC = **0.50**

### **MobileNetV2**
![MobileNetV2 Performance](deep%20lense%20mobilenetV2.png)
- **No Substructure:** AUC = **0.56**
- **Subhalo Substructure:** AUC = **0.54**
- **Vortex Substructure:** AUC = **0.52**

---

## Training Configuration
The training process consists of two phases:

### **First Training Phase**
- **Epochs:** 20
- **Batch Size:** 32 (Reduced to prevent memory issues)

### **Second Phase: Fine-Tuning**
- **Fine-Tune At:** Layer **100** (For VGG16 , **15**)
- **Optimizer:** Adam (learning rate = **1e-5**)
- **Loss Function:** Categorical Crossentropy
- **Metrics:** Accuracy
- **Epochs for Fine-Tuning:** 10

---

## Conclusion
- **VGG16** performed the best among the tested models with an AUC of **0.89** for the 'No Substructure' class.
- **EfficientNetB0** performed poorly with an AUC close to **0.50**, indicating random classification.
- Fine-tuning significantly improved performance for VGG16 and ResNet50.


