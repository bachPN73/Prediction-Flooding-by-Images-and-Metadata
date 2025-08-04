# Prediction Flooding by Images and Metadata
### Task Description
##### Task Description The goal of this task is to retrieve all images which show direct evidence of a flooding event from social media streams, independently of a particular event. The objective is to design a system/algorithm that given any collection of multimedia images and their metadata (e.g., YFCC100M, Twitter, Wikipedia, news articles) is able to identify those images that are related to a flooding event. Please note, that only those images which convey an evidence of a flooding event will be considered as True Positives. Specifically, we define images showing unexpected high water levels in industrial, residential, commercial and agricultural areas“ as images providing evidence of a flooding event. The main challenges of this task are the proper discrimination of the water level in different areas (e.g., images showing a lake vs. showing high water at a street) as well as the consideration of different types of flooding events (e.g., coastal flooding, river flooding, pluvial flooding).

![Image](https://multimediaeval.github.io/2017-Multimedia-Satellite-Task/Preview_DIRSM.png)

### Evaluation
#### The evaluation metric for this competition is MAP@K. K=250
#### This leaderboard is calculated with approximately 60% of the test data. The final results will be based on the other 40%, so the final standings may be different

### Data set
##### We thank: MediaEval 2017 and Pham Quang Nhat Minh
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
### Method
```
ViT (frozen) + LoRA  →  Linear + GELU → Dropout → img_feat
BERT (frozen) + LoRA →  Linear + GELU → Dropout → text_feat
           Concatenate [img_feat, text_feat]
                         ↓
               Classifier → Output (Sigmoid)

```
### Result
