# Innovation Point | Fault Diagnosis Model Based on Fast Fourier Transform Convolution (FFC)

This issue introduces a network model based on Fast Fourier Transform Convolution (FFC-ResNet), which enhances the performance of Convolutional Neural Networks (CNN) by replacing conventional convolutions in ResNet with Fast Fourier Transform Convolutions. This model has been applied to bearing fault diagnosis tasks and has achieved promising results.
\t  
By cleverly integrating the outstanding performance of Fast Fourier Transform (FFT), Fast Fourier Convolution (FFC) has become an efficient tool for convolution operations, particularly in scenarios where global context understanding and seamless integration of cross-scale features are sought. This innovative frequency domain processing not only significantly enhances the precision and efficiency of feature extraction but also greatly accelerates the computational process, laying a solid foundation for leaps in model performance in practical applications while maintaining low computational resource consumption.
● Dataset: CWRU West Reserve University Bearing Dataset
● Environment Framework: Python 3.9, PyTorch 1.8 and above can be run.
● Accuracy: 96% on the test set.
● Usage Object: Paper requirements, graduation design requirements.
● Code Guarantee: The code comments are detailed and ready to run.
Preface
This paper is based on the bearing data from Case Western Reserve University (CWRU), and firstly, it carries out data preprocessing. Then, a classification model based on the FFC-ResNet network is implemented using Python to classify fault data.
1. Data preprocessing for bearing faults
1.1 Import data
Refer to the previous article for preprocessing of fault classification 10, and the Case Western Reserve University bearing data set: Classification 10 dataset.
\ttrain_set, val_set, test_set are all divided into training set, validation set and test set according to the ratio of 7:2:1, and finally save the data.
1.2 Preprocessing of fault data and dataset preparation
2. Introduction to Fast Fourier Transform Convolution (FFC)
2.1 Model Introduction
The core of the FFC module is to convert traditional spatial convolution into frequency domain, which is realized by using Fast Fourier Transform (FFT). This transformation brings significant improvements in computational efficiency and model accuracy. Additionally, the module introduces Local Fourier Unit (LFU), a learnable filter operating in the frequency domain, capable of further optimizing feature representation, thereby enhancing the model's performance.
2.2 Innovation Points
A new convolutional module, Fast Fourier Convolution (FFC), is proposed. It not only has a non-local receptive field but also performs the fusion of information across scales within the convolution itself.
(1) FFC Framework:
\tFFC consists of two interconnected paths: a spatial (local) path that performs ordinary convolution over partial input feature channels, and a spectral (global) path that operates in the frequency domain. Each path can capture complementary information with different receptive fields.
\t  
\t (2)Fourier Unit(FU)  
1. Properties: When applying a two-dimensional FFT to real signals, an entirely symmetrical Hermitian matrix is produced. Applying the inverse FFT to this Hermitian matrix results in only real elements. When performing an FFT on a real tensor, its result is conjugate symmetric. Therefore, without losing useful information, we can retain only half of the results and simply restore the other half by using conjugate symmetry.
2. Properties: The Spectral Convolution Theorem in Fourier Theory: Updating a single value in the spectral domain can affect global features in the spatial domain.
For spectrum transformers, a large kernel size is unnecessary, as any operation in the spectral domain has a global receptive field.
\t (3)Local Fourier Unit(LFU)  
\t  
The goal is to capture semi-global information, which involves dividing the input feature map into four patches and using FU for each one. Compared to FU, LFU requires higher computational complexity, primarily due to the additional channels. The effectiveness of LFU varies depending on the specific task!
2.3 Complexity Analysis
\t  
Compared to conventional convolutions, FFC has comparable computational costs. However, when using large kernel convolutions in conventional convolutions, FFC demonstrates its superiority. In spectral transformers, 1×1 kernels are still used for learning global receptive fields.
3. Fault Diagnosis Model Based on FFC-ResNet
\t3.1 Define the FFC-ResNet model
3.2 Set parameters and train the model
\t  
3.3 Model Evaluation
Accuracy, Precision, Recall, F1 Score
\tFault classification confusion matrix:
\tOther visualizations:
(1) Classification Label Visualization
(2) Original Data t-SNE Feature Visualization
(3) t-SNE feature visualization after model training:
The model classification effect is significant, with 50 epochs achieving an accuracy of 96%. The FFC-ResNet can effectively mine multi-scale features from signals, has a fast convergence speed, superior performance, high precision, and can extract important features from the frequency domain and time domain characteristics of fault signals, resulting in noticeable effects.
\tFast Fourier Transform Convolution (FFC) is a substitute for conventional convolutions, enhancing the performance of Convolutional Neural Networks (CNN), and holds great application value in fault diagnosis tasks!
Click to download: Complete original data, Python code
Previously Featured Content:
Python-Case Western Reserve University (CWRU) Bearing Data Interpretation and Classification Process
Python Bearing Fault Diagnosis (I) Short-Time Fourier Transform STFT
Python Bearing Fault Diagnosis (II) Continuous Wavelet Transform CWT
Python Bearing Fault Diagnosis (IV) EMD-CNN for One-Dimensional Signal Classification  
Pytorch-LSTM Bearing Fault One-Dimensional Signal Classification (I)  
Pytorch-CNN Bearing Fault One-Dimensional Signal Classification (II)  
Pytorch-Transformer Bearing Fault One-Dimensional Signal Classification (III)  
Python Bearing Fault Diagnosis (IV) Based on EMD-CNN for Fault Classification  
Python Bearing Fault Diagnosis (V) Based on EMD-LSTM for Fault Classification  
Python Bearing Fault Diagnosis (VI) Based on EMD-Transformer for Fault Classification  
Python Bearing Fault Diagnosis (VII) Based on EMD-CNN-LSTM for Fault Classification  
Python Bearing Fault Diagnosis (VIII) Based on EMD-CNN-GRU Parallel Model for Fault Classification  
Bearing Fault Identification Model Based on FFT + CNN - BiGRU-Attention for Time and Frequency Feature Attention Fusion  
Bearing Fault Identification Model Based on FFT + CNN - Transformer for Time and Frequency Feature Fusion  
Python Bearing Fault Diagnosis (IX) Based on VMD+CNN-BiLSTM for Fault Classification  
Python Bearing Fault Diagnosis (X) Based on VMD+CNN-Transformer for Fault Classification  
Python Bearing Fault Diagnosis (XI) Based on VMD+CNN-BiGRU-Attenion for Fault Classification  
Cross Attention Fusion for Time and Frequency Features: Bearing Fault Identification Model Based on FFT + CNN-BiLSTM-CrossAttention  
Cross Attention Fusion for Time and Frequency Features: Bearing Fault Identification Model Based on FFT + CNN-Transformer-CrossAttention
Python Bearing Fault Diagnosis (13) Super-strong Machine Learning Identification Model Based on Fault Signal Feature Extraction
Python Bearing Fault Diagnosis (14) Highly Innovative Fault Identification Model
Python Bearing Fault Diagnosis (15) One-Dimensional Fault Signal Identification Model Based on CNN-Transformer
Python Bearing Fault Diagnosis (16) Highly Innovative Fault Identification Model (II)
 | Science Citation Index 1 Region, Highly Innovative Bearing Fault Diagnosis Model!
Python Bearing Fault Diagnosis (18) Innovation Diagnosis Model Based on CNN-TCN-Attention
Based on GADF+Swin-CNN-GAM, Highly Innovative Bearing Fault Diagnosis Model
Attention Magic Modification | Super-strong Bearing Fault Diagnosis Model!
Bearing Fault—Cross Attention Innovation Model Full Set
Python Bearing Fault Diagnosis (19) Innovation Diagnosis Model Based on Transformer-BiLSTM
END

## Images

<!-- PAYMENT_BLOCK -->

## Get this dataset

- Payment link (Stripe): [Buy now](https://buy.stripe.com/3cs8yP7sY87d0vu9AB)
- Payment QR code: ![Payment QR code](pay.png)

<!-- /PAYMENT_BLOCK -->
