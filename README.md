# rock_paper_scissor

The proposed architecture has the following steps:

1. Feature Detection: Utilizing an image classification algorithm, like Fast-RCNN. Here I suggest the EfficientNet model. Fine-tuning is performed on this model using our dataset, then the Global Average Pooling layer of the model is removed as our aim is feature extraction.

2. Region of Interest (RoI) suggestion: On the resulting feature map, we employ the Region Proposal Network (an improvement over original fast-RCNN which uses selective search) to identify Regions of Interest. This process yields the coordinates (xmin, ymin, xmax, ymax) of the bounding boxes. Further we apply a RoI pooling layer to make input for further layers.

3. Object Classification: The identified Regions of Interest are passed through two CNN layers, as proposed in OverFeat. This step provides us with the classification of objects within the bounding boxes, categorizing them as Rock, Paper, or Scissor.

Currently only the first step is partially completed.

References:
1. Fast R-CNN : https://arxiv.org/abs/1504.08083
2. Faster R-CNN : https://arxiv.org/abs/1506.01497
3. OverFeat : https://arxiv.org/abs/1312.6229
4. EfficientNet : https://arxiv.org/abs/1905.11946
