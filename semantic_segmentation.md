## Resources
[Great blog post on semantic segmentation](https://www.jeremyjordan.me/semantic-segmentation/)


# Semantic segmentation
![Semantic Segmentation](https://www.jeremyjordan.me/content/images/2018/05/Screen-Shot-2018-05-17-at-7.42.16-PM.png)

## Task representation
- Convert RGB image of (w, h, 3) into (w, h, c) where c is number of classes. 
![Task illustration](https://www.jeremyjordan.me/content/images/2018/05/Screen-Shot-2018-05-17-at-9.02.15-PM.png)
- Key differences with image classification
  - Location matters
  - Final output is an image with same resolution
  
## Architectures
- ### Full Conv
  ![Full Conv architecture](https://www.jeremyjordan.me/content/images/2018/05/Screen-Shot-2018-05-19-at-12.32.20-PM.png)
- To allow for lower computations, downsample and upsample. 
  ![Down and up](https://www.jeremyjordan.me/content/images/2018/05/Screen-Shot-2018-05-16-at-10.33.29-PM.png) 
  - ![Repurposed alexent](https://www.jeremyjordan.me/content/images/2018/05/Screen-Shot-2018-05-20-at-9.53.20-AM.png)
  - Repurposed alexnet struggles to produce fine grained stuff. Tension between global and local semantics. 
- ### UNet
  - Add skip connections to combine global and local semantics. 
  - ![UNet](https://www.jeremyjordan.me/content/images/2018/05/Screen-Shot-2018-05-20-at-1.46.43-PM.png)
  - We can also replace conv blocks with dense blocks, res blocks. 
  - ![DenseNet](https://www.jeremyjordan.me/content/images/2018/05/Screen-Shot-2018-05-20-at-3.42.24-PM.png)

## Loss function
  - Pixel wise cross entropy loss is very common
    - ![PCE loss](https://www.jeremyjordan.me/content/images/2018/05/Screen-Shot-2018-05-24-at-10.46.16-PM.png)
  - Dice coefficient, find ratio of intersection over union. 
    - $Dice = \frac{2|A \cap B|}{|A| + |B|}$
    - 1 for perfect intersections
    - How to compute this practically ?
      - Intersection is sum of element wise multiplication between gt and predicted. 
      - Union is sum of activations
    - Soft dice loss
      - ![Soft dice loss](https://www.jeremyjordan.me/content/images/2018/05/Screen-Shot-2018-05-24-at-10.50.59-PM.png)
      - Compute soft dice loss for each class separately and average over. 

## Datasets


## Tags
- Computer vision, semantic segmentation