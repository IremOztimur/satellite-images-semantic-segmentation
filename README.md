# Semantic Segmentation of Satellite Images

## Dataset
---
For this project I'll be using a dataset which is already annotated. The dataset is from kaggle you can download it from here [Semantic Segmentation of Aerial Imagery Dataset](https://www.kaggle.com/datasets/humansintheloop/semantic-segmentation-of-aerial-imagery/data)

### About Dataset
The dataset consists of aerial imagery of Dubai obtained by MBRSC satellites and annotated with pixel-wise semantic segmentation in 6 classes. The total volume of the dataset is 72 images grouped into 6 larger tiles. The classes are:

Building: #3C1098\
Land (unpaved area): #8429F6\
Road: #6EC1E4\
Vegetation: #FEDD3A\
Water: #E2A929\
Unlabeled: #9B9B9B


| | | |
|:-------------------------:|:-------------------------:|:-------------------------:|
|<img width="500" src="https://github.com/user-attachments/assets/8246d7d2-49e3-4365-a110-ce883e013f65"> image | |<img width="500" src="https://github.com/user-attachments/assets/2ebda246-4dff-454a-ac4b-bd04a8617118"> mask|


> [!NOTE]
>The number of images available for training is insufficient for a wide range of applications. This project aims to explore semantic segmentation using different models as efficiently as possible.


### Preprocessing the Data

- The images come in various sizes: 797x644, 509x544, 682x658, 1099x846, 1126x1058, 859x838, 1817x2061, 2149x1479\
  -> Crop to a size divisible by 256 and extract patches.
- Masks are RGB and information provided as HEX color code.\
  -> Need to convert HEX to RGB values and then convert RGB labels to integer values and then to one hot encoded.
- Predicted (segmented) images need to converted back into original
RGB colors.
