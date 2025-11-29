**Skin Cancer Detection for Telehealth**
Skin cancer is a rapidly growing global health concern, with cases increasing at an alarming rate each year. According to the World Health Organization (WHO), over 1.5 million new cases were reported in 2022, making skin cancer one of the most frequently diagnosed cancers worldwide. Although melanoma accounts for only 1% of all cases, it is responsible for more than 80% of skin-cancer-related deaths due to its aggressive nature and ability to metastasize quickly if not treated promptly. Other forms such as basal cell carcinoma and squamous cell carcinoma are less aggressive but still pose serious health risks when left undetected.
Traditional skin cancer diagnosis heavily relies on in-person dermatological evaluations and specialized imaging tools like dermatoscopes. Unfortunately, access to these resources is limited in many underserved and remote regions, resulting in delayed or missed diagnoses. The lack of accessible screening options underscores the urgent need for remote, low-cost, and reliable diagnostic solutions—especially for populations that depend on telehealth services.
This project, Skin Cancer Detection for Telehealth, aims to bridge this gap by leveraging machine learning to classify skin lesions from low-resolution, patient-submitted images. Using the ISIC 2024 dataset, the system employs a hybrid deep feature extraction approach, combining features from a custom autoencoder and ResNet-50’s conv5_block2 layer to capture both compressed and high-level lesion characteristics. To further enhance classification performance, Linear Discriminant Analysis (LDA) is used to refine these features by maximizing class separability. The optimized feature set is evaluated using Support Vector Machines (SVM), Neural Networks (NN), and Random Forests (RF), with SVM achieving the highest accuracy.
By integrating deep learning with robust classical machine learning techniques, this project demonstrates a practical and effective solution for accessible, scalable, and reliable skin cancer detection in telehealth environments.

**Dataset: ISIC 2024 [kaggle competitions download -c isic-2024-challenge]**
**Proposed System:**
The proposed system for skin cancer detection operates through a structured pipeline designed to facilitate accurate diagnosis from low-resolution telehealth images
<img width="663" height="373" alt="image" src="https://github.com/user-attachments/assets/4af4f33e-8def-43ba-8b45-cc8e70e1028b" />

The proposed system enhances skin cancer diagnosis by combining deep feature extraction 
from an autoencoder and ResNet-50’s conv5_block2 layer. To further optimize classification, 
Linear Discriminant Analysis (LDA) is applied to maximize class separability. The refined 
features are then analyzed using Support Vector Machines (SVM), Neural Networks (NN), and 
Random Forest (RF), with SVM achieving the highest accuracy of 91.8%. This approach 
improves diagnostic reliability, particularly for low-resolution skin lesion images commonly 
encountered in telehealth settings.
To enhance the classification of skin lesions, we first evaluated deep feature extraction from 
VGG16 and ResNet-50 architectures. These models are known for their ability to capture 
intricate patterns in medical images. We focused on specific layers, extracting features from 
VGG16's block5_conv2, block5_conv1, and block5_conv3, as well as ResNet-50's 
conv5_block1 and conv5_block2. Each of these layers provided distinct feature 
representations, which were then fed into various classifiers, including Support Vector 
Machines (SVM), Neural Networks (NN), and Random Forests (RF). After thorough 
evaluation, we found that the highest classification accuracy 80.50% was achieved using 
features extracted from ResNet-50’s conv5_block2 layer.
<img width="801" height="421" alt="image" src="https://github.com/user-attachments/assets/221c3322-ef4a-440f-a1e4-900054b76bcf" />


Recognizing the potential of feature learning, we then incorporated an autoencoder-based 
approach to improve the extracted feature representations. The autoencoder was designed to be 
more memory-efficient by reducing image size and batch size while improving training 
stability through Batch Normalization after each convolutional layer. Instead of relying solely 
on MaxPooling, we introduced a 256-channel bottleneck layer to retain more informative 
features. Additionally, we optimized training by using fewer steps per epoch and clearing GPU 
memory before each session to prevent crashes. The bottleneck layer’s compressed yet 
meaningful representation provided another set of valuable features for classification.
<img width="569" height="262" alt="image" src="https://github.com/user-attachments/assets/89f9c352-e5b9-434b-8347-b97698442e02" />


To further refine the feature set, we combined the extracted features from ResNet-50’s 
conv5_block2 layer and the autoencoder’s bottleneck layer. To ensure that the most 
discriminative features were retained, we applied Linear Discriminant Analysis (LDA), which 
maximized class separability by projecting the features onto a lower-dimensional space. These 
optimized features were then classified using SVM, NN, and RF. The highest accuracy 91.8% 
was achieved using SVM, demonstrating the effectiveness of our approach in distinguishing 
between benign and malignant skin lesions.

<img width="772" height="405" alt="image" src="https://github.com/user-attachments/assets/c5cde063-babb-4425-be0d-71db785ce2bf" />

