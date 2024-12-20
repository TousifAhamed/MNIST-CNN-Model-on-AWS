# Training Experiments on MNIST Dataset

## Objective
The objective of this project is to achieve **99.4% test accuracy in 15 epochs** using a **CNN network with less than 8000 parameters**. 

This repository contains a series of experiments on the MNIST dataset aimed at achieving high accuracy with a compact CNN model. The experiments involve iterative improvements to a **Squeeze and Excite (SE) model structure** across five versions.

---

## Experiments conducted

### **Version 1: Basic Skeleton**
#### Target
- Develop the initial architecture of the Squeeze and Excite (SE) model.

#### Results
- **Parameters**: 6,633  
- **Best Train Accuracy**: 99.22%  
- **Best Test Accuracy**: 98.78%  

#### Analysis

- Model is having less parameters less than 8000 parameters.
- Model is overfitting.

---

### **Version 2**
#### Target
- Improve model by updating last convolution layer with a **Global Average Pooling (GAP)** layer.

#### Results
- **Parameters**: 5,733  
- **Best Train Accuracy**: 98.46%  
- **Best Test Accuracy**: 98.45%  

#### Analysis
- Model is having parameters less than 8000 parameters.
- GAP helped to reduce the number of parameters.
- Overfitting is reduced now.
- Network capacity is reduced and it is expected that reduction in model accuracies.

---

### **Version 3: Batch Normalization**
#### Target
- Update each layer with **Batch Normalization** in each convolution block (except the last layer) to normalize kernel outputs and improve convergence.

#### Results
- **Parameters**: 5,893  
- **Best Train Accuracy**: 99.30%  
- **Best Test Accuracy**: 99.12%  

#### Analysis
- Model is having parameters less than 8000 parameters.
- Batch Normalization improved convergence and increased accuracies.  
- Slight overfitting was observed.  
- Further updates with Step LR Schedulers in the next version.

---

### Version 4: Step LR 
#### Target : StepLR to decrase the learning rate
- Added step LR with step size 7 and gamma 0.1

#### Results
- **Parameters**: 5,893  
- **Best Train Accuracy**: 99.48%  
- **Best Test Accuracy**: 99.07%  

#### Analysis
- Model is having less parameters less than 8000 parameters.
- Accuracy is improved with Step LR
- It is observed that the model is overfitting and there is room for improvement in next version.
- Update model with image augmentation and also updaring step LR params

---

### **Version 5: Image Augmentation and StepLR Scheduler**
#### Target
####  Apply Image Augmentation and LR Fine tunning
- Image augmentation - Random rotation of in the range of -10 to 10 degrees and fill with 1
- Step LR with Learning Rate = 0.1, Step Size = 9 and Gamma = 0.18

#### Results
- **Parameters**: 5,893  
- **Best Train Accuracy**: 99.26%  
- **Best Test Accuracy**: 99.44%  

#### Analysis
- Image Augmentation with random rotation of -10 to 10 degrees helped to overcome overfitting issues.
- Step LR with Learning Rate of 0.1 and Step Size of 9 and Gamma of 0.18 helped to achieve consistency with model results.  
- Finally objective achieved with test accuracy of 99.44% with parameter less than 8K.

#### Logs
![](Images/Final_Results.png)
---

## Repository Structure
- **Version 1**: Basic skeleton implementation.
- **Version 2**: GAP layer.
- **Version 3**: Batch Normalization.
- **Version 4**: Learning Rate Scheduler implementation.
- **Version 5**: Image Augmentation and StepLR Scheduler.

---

## Dataset
The experiments were conducted on the MNIST dataset, which consists of grayscale images of handwritten digits (0-9).

---

## Conclusion
This project showcases the effectiveness of iterative enhancements such as parameter optimization, Batch Normalization, Learning Rate Scheduling, and Image Augmentation in achieving high accuracy within set constraints. The final CNN model attained the target of **99.44% test accuracy** in 15 epochs with fewer than **8000 parameters**.

---

## Future Work
- Further optimize the model architecture and training procedures to reduce overall training time.
- Extend the scope of experiments to additional datasets such as FashionMNIST and CIFAR-10 to demonstrate the model's versatility.
- Explore the deployment of the trained model on edge devices, evaluating its performance and resource efficiency in real-world environments.
- Implement advanced regularization techniques to enhance model generalizability and prevent overfitting.
- Investigate automated hyperparameter tuning methods to systematically refine model performance.
- Conduct a detailed analysis of various performance metrics to identify potential areas for further improvement.
- Integrate model compression techniques to further reduce the number of parameters while maintaining high accuracy.

---
