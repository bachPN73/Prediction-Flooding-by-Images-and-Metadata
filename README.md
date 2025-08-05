# Prediction Flooding by Images and Metadata
### Task Description
##### Task Description The goal of this task is to retrieve all images which show direct evidence of a flooding event from social media streams, independently of a particular event. The objective is to design a system/algorithm that given any collection of multimedia images and their metadata (e.g., YFCC100M, Twitter, Wikipedia, news articles) is able to identify those images that are related to a flooding event. Please note, that only those images which convey an evidence of a flooding event will be considered as True Positives. Specifically, we define images showing unexpected high water levels in industrial, residential, commercial and agricultural areas“ as images providing evidence of a flooding event. The main challenges of this task are the proper discrimination of the water level in different areas (e.g., images showing a lake vs. showing high water at a street) as well as the consideration of different types of flooding events (e.g., coastal flooding, river flooding, pluvial flooding).

![Image](https://multimediaeval.github.io/2017-Multimedia-Satellite-Task/Preview_DIRSM.png)

### Evaluation
#### The evaluation metric for this competition is MAP@K. K=250
#### This leaderboard is calculated with approximately 60% of the test data. The final results will be based on the other 40%, so the final standings may be different
##### We thank: MediaEval 2017 and Pham Quang Nhat Minh
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
### Introduction
#### Fine-tuned ViT + DeBERTa on flood image dataset using multi-modal deep learning to combine visual and textual features, achieving higher accuracy than single-modality baselines.

### Data set
```
/kaggle/input/2025-sum-dpl-302-m/
│
├── devset_images/                       
│   └── devset_images/
├── devset_images_metadata.json       
├── devset_images_gt.csv            
├── testset_images/                   
│   └── testset_images/
├── test.csv                            

```
#### Image: devset_images, testset_images
#### Metadata: devset_images_metadata.json, test.csv (image_id, title, description, user_tags, label)
#### Label: devset_images_gt.csv, test.csv

### Method
#### Combines the power of:
- Vision Transformer (ViT) for extracting features from images.
- DeBERTa-v3-small for understanding the context of image descriptions.
#### Applies multi-modal deep learning to fuse visual and textual features, leading to better accuracy than single-modality models.
### Result
- Achieved 0.91 private and public scores on the ¬ood image classi«cation task
using mAP@250
