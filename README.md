# Brain-MRI-Tumor-Segmentation
This project presents a fully automatic method for 3D segmentation of brain tissue on MRI scans using a modern deep learning approach and proposes 3D Dense-U-Net neural network architecture using densely connected layers.
This project aims to distinguish gliomas which are the most difficult brain tumors to be detected with deep learning algorithms. For a skilled radiologist, analysis of multimodal MRI scans can take up to 20 minutes.

# Dataset
### LLG Segmentation dataset
Kaggle dataset: https://www.kaggle.com/mateuszbuda/lgg-mri-segmentation

  - This dataset contains brain magnetic resonance images together with manual FLAIR abnormality segmentation masks.
  - The images were obtained from The Cancer Imaging Archive (TCIA). The dataset includes 3829 images from 110 patients.
  - They correspond to 110 patients included in The Cancer Genome Atlas (TCGA) lower-grade glioma collection with at least fluid-attenuated inversion recovery (FLAIR) sequence and genomic cluster data available.

# Preprocessing

  - We are keeping brain images in RGB because we think with 3 channel R-G-B, information about tumors is different from the rest in a typical MRI Scan Image Output. The mask    images are gray.
  - We bring the image's pixel to between 0 and 1 and mask's pixel are 0 or 1 (0 when pixel / 255 < 0.5, 1 when pixel / 255 >= 0.5).
  - We split data into 3 parts: Train, Validation, and Test:
    - Train: 2828 images, masks (71.98%)
    - Validation: 708 images, masks (18.02%)
    - Test: 393 images, masks (10%)
    
# Model Architecture
![Model](https://imgur.com/G0SIfkR.png)

# Training
- Training of our CNN model: Done on a 4GB VRAM NVIDIA GTX 1050Ti 
- For 150 epochs 
- Using the Keras API and adam optimizer function 
- With a learning rate of 1e-4
### Loss and Accuracy after each Iteration
![Model](https://imgur.com/CofCrjs.png)
![Model](https://imgur.com/Equ6r7l.png)

# Some Predictions

MRI Scan with Brain Tumor :

![Model](https://imgur.com/OKZX18x.png)
MRI Scan without Brain Tumor :

![Model](https://imgur.com/wisKMyM.png)


# References
### Papers referred to
1. Low Grade Glioma Segmentation Based on CNN with Fully Connected CRF
(Hindawi Journal of Healthcare Engineering Volume 2017)
2. Enhanced Performance of Brain Tumor Classification via Tumor Region Augmentation and Partition
(Journal PLOS One 2015)
3. 3D Dense-U-Net for MRI Brain Tissue Segmentation
(IEEE Xplore (Martin Kolaˇr ́ık, Radim Burget, Vaclav Uher, BRNO UNIVERSITY OF TECHNOLOGY Brno, Czech Republic ) 2018)
4. Segmentation of MRI Images for Brain Cancer Detection
(2018 International Conference on Information and Communications Technology (ICOIACT))
5. Automatic Segmentation of MRI Images for Brain Tumor using unet
(2019 1st International Conference on Advances in Information Technology)
6. Brain tumor segmentation based on a new threshold approach
(International Conference on Theory and application of Soft Computing, Computing with Words and   Perception. 2017)
7. Automatic classification of Brain Tumor and Alzheimer's Disease in MRI
(Elsevier 2019)
8. Novel approach for segmentation of brain magnetic resonance imaging using intensity-based thresholding
(IEEE Xplore(D.Selvaraj,R.Dhanasekaran) 2010)
9. Multi-Res-Attention UNet: A CNN Model for the Segmentation of Focal Cortical Dysplasia Lesions from Magnetic Resonance Images
(IEEE Journal of Biomedical and Health Informatics 2020)
10. Attention-Guided Version of 2D UNet for Automatic Brain Tumor Segmentation
(9th International Conference on Computer and Knowledge Engineering (ICCKE 2019))
