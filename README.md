# Parametric Shape Estimation of Human Body under Wide Clothing

If you are interested in using our dataset and find it useful in your research, please consider citing the following paper:

```latex
@article{lu2020parametric,
  title={Parametric Shape Estimation of Human Body under Wide Clothing},
  author={Lu, Yucheng and Cha, Jin-Hyuck and Youm, Se-Kyoung and Jung, Seung-Won},
  journal={IEEE Transactions on Multimedia},
  year={2020},
  publisher={IEEE}
}
```

------



2020-11-1: We found some bad samples in the current  SHADER dataset, and we removed them from the released pack.  Therefore not all the batches have 50 samples. We are working on re-rendering these samples, which might take some time. Please wait for the updates, thanks.



### Introduction

The SHADER dataset is a synthetic dataset that consists of 300,000 paired ground-truth naked and dressed images of 1,500 synthetic humans with different body shapes, poses, garments, skin tones, and backgrounds. It can be used to train neural networks for estimating shapes of human bodies under wide clothing.

The dataset (current version 1.0) can be downloaded from [onedrive](https://dongguk0-my.sharepoint.com/:u:/g/personal/yc_lu_dongguk_edu/ETpL1JV8ZqpDsY-BpE3eVXkBXYcBmDwZ5w12whgIq-3a_Q).



### Dataset Structure

The dataset consists of two genders, and the folder hierarchy is as follows: 

```markdown
SHADER-rx_x					# dataset root folder
├── (fe)maleBatch001				# batch folder
|	├── 0000				# sample folder
|	|	├── dressed             	# clothed image folder
|	|	|	├── Image0000.png	# clothed images
|	|	|	...
|	|	|	├── Image0198.png
|	|	|	└── Image0199.png
|	|	├── naked               	# ground-truth image folder
|	|	|	├── Image0000.png	# ground-truth images
|	|	|	...
|	|	|	├── Image0198.png
|	|	|	└── Image0199.png
|	|	└── gt0000.pkl          	# other ground-truth parameters
|	...
|	├── 0048
|	└── 0049
...
├── (fe)maleBatch014
└── (fe)maleBatch015
```



### How to Use (refer to the paper)

As is shown in the paper, the SHADER dataset is a synthetic dataset with human models under wide clothing.  Hence, two images corresponding to dressed and naked bodies are provided. The dressed image is fully rendered with garment meshes as well as skin texture, while the naked version does not include either of them. All images are provided as 4-channel PNG format where the forth channel is the transparency channel separating background or foreground pixels.

Besides images, there is a pickle file for each instance, which contains per-frame parameters as a dictionary:

|   Key    |     Size     |       Description       |
| :------: | :----------: | :---------------------: |
|  shape   |      10      |    SMPL shape vector    |
|  poses   |  #frames×72  |    SMPL pose vector     |
|  trans   |  #frames×3   | SMPL translation vector |
| joints2D | #frames×24×2 |  2D joint coordinates   |
| joints3D | #frames×24×3 |  3D joint coordinates   |



### Generate Your Own Dataset

Coming soon...



