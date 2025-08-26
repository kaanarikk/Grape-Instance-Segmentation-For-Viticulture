# Grape-Instance-Segmentation-For-Viticulture
In this dataset, using a unique dataset (FGVL Dataset) collected from Sultana seedless grape vineyards in the Aegean Region of Turkey, an example segmentation model has been developed to classify frost-damaged leaves and grape clusters at the pixel level.
The dataset includes 418 frost-damaged grapes, 510 frost-damaged leaves, 395 healthy grapes, and 698 healthy leaves, collected after a severe frost event in April 2025 at a vineyard in Manisa. The im-ages were captured in high resolution under natural lighting conditions and manually labeled by experts.

# Instructions

Participants must use the FGVL Dataset to develop deep learning models for instance segmentation of frost-damaged and healthy grape leaves and clusters.

You are free to use any image processing or deep learning framework (e.g., YOLOv11, PyTorch, TensorFlow) and apply data augmentation, model tuning, and evaluation techniques.

Submissions will be evaluated based on mAP@50 and mAP@50-95 metrics on the test set.

Access the dataset: 

1. https://ieee-dataport.org//documents/frost-damaged-leaf-and-grape
2. https://universe.roboflow.com/computer-vision-yqyos/grape-segmentation-yedek-kendi-verim/browse?queryText=&pageSize=50&startingIndex=0&browseQuery=true
3. https://www.kaggle.com/datasets/kaanarikkk/grape-instance-segmentation-for-viticulture

README - FGVL Dataset: Frost Grape and Vine Leaf Dataset
1. Dataset Overview
Dataset Name: FGVL (Frost Grape and Vine Leaf Dataset)
Domain: Precision Agriculture, Computer Vision, Deep Learning
Purpose: To support instance-based segmentation of frost-damaged and healthy grape leaves and clusters using YOLO-based models, particularly YOLOv11s+ASPP.
Licensing: Academic use only (please cite the associated IEEE Access paper).

2. Data Structure
Total Images (after preprocessing): ~1100
Image Format: JPEG (.jpg), 24-bit color
Resolution: 640x640 (after resizing from 1512x2016)
Annotations: YOLOv11-compatible segmentation masks
Annotation Format: .txt or .json (depending on release; COCO format optionally available)

Folder Structure Example:
/FGVL_Dataset/
│
├── /images/
│   ├── train/
│   ├── val/
│   └── test/
│
├── /labels/
│   ├── train/
│   ├── val/
│   └── test/
│
├── classes.txt
└── README.txt

| Class ID | Class Name    |
| -------- | ------------- |
| 0        | Frozen Grape  |
| 1        | Frozen Leaf   |
| 2        | Healthy Grape |
| 3        | Healthy Leaf  |

4. Preprocessing Details
Auto-Orientation: Images reoriented using EXIF data to prevent bias from incorrect rotation.

Resize: All images resized to 640x640 to fit YOLOv11 input requirements.

Compression: Lossless JPEG compression (0.80 quality) reduced size from 3.2 GB to 236 MB.

Color Depth: 24-bit RGB

5. Augmentation Techniques
The following augmentations were applied:

Horizontal & Vertical Flip

90° Rotation

Random Brightness Adjustments (±18%)

Gaussian Blur (σ = 0.5 to 2)

CLAHE (Contrast-Limited Adaptive Histogram Equalization)

Shear, Scale, Crop, and Exposure Modifications

6. Usage Instructions
To use this dataset:

Load image and mask paths as per YOLO training format.

Convert to COCO format if needed using tools like Roboflow or FiftyOne.

Apply model training using YOLOv11 or YOLOv11+ASPP with the provided classes.

Evaluate using mAP@50 and mAP@50-95 metrics.

Suggested Training Ratios:

Train: 70%

Validation: 20%

Test: 10%

7. Contact
For dataset questions or collaboration:
Email: kaanarik@subu.edu.tr
Affiliation: Sakarya University of Applied Sciences
