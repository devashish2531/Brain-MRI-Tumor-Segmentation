# Brain-MRI-Tumor-Segmentation
This project presents a fully automatic method for 3D segmentation of brain tissue on MRI scans using a modern deep learning approach and proposes 3D Dense-U-Net neural network architecture using densely connected layers.
This project aims to distinguish gliomas which are the most difficult brain tumors to be detected with deep learning algorithms. For a skilled radiologist, analysis of multimodal MRI scans can take up to 20 minutes.

# Dataset
### LLG Segmentation dataset
Kaggle dataset: https://www.kaggle.com/mateuszbuda/lgg-mri-segmentation

  -This dataset contains brain magnetic resonance images together with manual FLAIR abnormality segmentation masks.
  -The images were obtained from The Cancer Imaging Archive (TCIA). The dataset includes 3829 images from 110 patients.
  -They correspond to 110 patients included in The Cancer Genome Atlas (TCGA) lower-grade glioma collection with at least fluid-attenuated inversion recovery (FLAIR) sequence and genomic cluster data available.

# Preprocessing

  -We are keeping brain images in RGB because we think with 3 channel R-G-B, information about tumors is different from the rest in a typical MRI Scan Image Output. The mask images are gray.
  -We bring the image's pixel to between 0 and 1 and mask's pixel are 0 or 1 (0 when pixel / 255 < 0.5, 1 when pixel / 255 >= 0.5).
  -We split data into 3 parts: Train, Validation, and Test:
    -Train: 2828 images, masks (71.98%)
    -Validation: 708 images, masks (18.02%)
    -Test: 393 images, masks (10%)
    
# Model Architecture
