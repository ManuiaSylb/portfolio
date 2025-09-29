---
title: Ensuring Fairness in Pose Estimation Models for Diverse Populations
publishDate: 2025-09-12 16:00:00
img: /assets/stock-1.jpg
img_alt: Iridescent ripples of a bright blue and pink liquid
description: |
  We designed an end-to-end pipeline to assess the balance of Human Pose Estimation (HPE) datasets.
tags:
  - Artificial Intelligence 
  - Medical
  - PyTorch
---

## Fairness in HPE 

> Despite remarkable progress, human pose estimation remains a challenging task.

Despite remarkable progress driven by deep learning, human pose estimation remains a challenging task. The diversity of human appearances, clothing, and body shapes introduces significant variability. In addition, the human body exhibits complex articulations, making it difficult to accurately capture fine-grained joint dependencies. These challenges are amplified when datasets are imbalanced or lack representative coverage of poses, leading to biased models. 

Our work addresses these issues by designing an end-to-end pipeline that not only evaluates dataset balance but also performs data augmentation through image generation, thereby improving the diversity and representativeness of human pose estimation datasets.

### COCO Dataset

The **COCO (Common Objects in Context)** dataset is one of the most widely used benchmarks in computer vision, covering tasks such as object detection, segmentation, captioning, and crucially **keypoint detection** for human pose estimation. [COCO official website](https://cocodataset.org/?utm_source=chatgpt.com)  

In the COCO keypoints format, each annotated person is described by **17 body keypoints** (e.g., nose, eyes, shoulders, elbows, wrists, hips, knees, ankles), each specified by an (x, y) coordinate and a visibility flag. [COCO keypoints guide](https://www.v7labs.com/blog/coco-dataset-guide?utm_source=chatgpt.com)  

This format allows models to learn to localize human joints in varied scenes. To evaluate pose estimators, COCO uses a metric called **Object Keypoint Similarity (OKS)**, which compares predicted vs. ground-truth keypoints while accounting for object scale and visibility. [OKS explanation](https://learnopencv.com/object-keypoint-similarity/?utm_source=chatgpt.com)  

Because of its scale, annotation quality, and standard evaluation protocols, COCO has become a de facto reference for human pose estimation research.

#### Dataset Evaluation

Evaluating the quality and representativeness of human pose estimation datasets is a crucial step toward building reliable models. In our work, we focus on several human-centered and visual attributes that can significantly impact performance: age, gender, body shape, and clothing-to-background contrast. These factors introduce strong variability in appearance and, if imbalanced, can bias the learning process. To systematically assess them, we leverage machine learning models trained to classify these attributes directly from the dataset images. By analyzing the resulting class distributions, we are able to detect overrepresented and underrepresented categories, highlight potential dataset biases, and provide a quantitative basis for further balancing strategies.

#### Dataset balancing

Once imbalances are identified, the next step is to mitigate them through dataset balancing. In our approach, we employ data augmentation via image generation, ensuring a more diverse and representative sample space. For this purpose, we adopt the COCO (Common Objects in Context) annotation format, a widely used standard in computer vision that provides detailed keypoint annotations for human pose estimation. By generating new images with corresponding COCO-style annotations, we are able to enrich minority classes and reduce distributional gaps highlighted during the evaluation phase. This strategy not only improves dataset diversity but also enhances the robustness of pose estimation models trained on the augmented data.

#### Results

- We noted this
- And also this other point
