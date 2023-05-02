# Noisy Labels repairing in dataset CASIA v2.0 groundtruth
 ![GitHub repo size](https://img.shields.io/github/repo-size/SunnyHaze/CASIA2.0-Corrected-Groundtruth?logo=hack%20the%20box)  [![Ask Me Anything !](https://img.shields.io/badge/Official%20-No-1abc9c.svg)](https://GitHub.com/Sunnyhaze) ![visitors](https://visitor-badge.glitch.me/badge?page_id=Sunnyhaze.CASIA2.0-Corrected-Groundtruth)

This repository includes resources below:
- **CASIA2.0** Image Tampering Detection Evaluation Dataset
- Ground-truth of CASIA2.0, which **repaired some of Noisy label-masks.**

> Owner of this repository is a colledge student now, if my tiny contribution helps you, please give me a star⭐ and explain the problem to other scientific researchers, which can help me a lot. Thanks! 
## Intro
CASIA 2.0 is a dataset for Image Tampering Detection Evaluation, which was published by Jing Dong et al in 2013. However, this dataset is **lack of the groundtruth images** comparing to other Image Tampering Detection Datasets.

To soleving the problem, Nam Thanh Pham et al. generated the corresponding Groundtruth in a 2019 paper contributed it to Github. This publicly available groundtruth has gained wide distribution in data science platforms such as kaggle([Link](https://www.kaggle.com/datasets/divg07/casia-20-image-tampering-detection-dataset)).
> Nam Thanh Pham et al. also corrected some mistakes in naming the files of the origianl CAISA 2.0 Dataset.
## Noisy Labels in wide spread groundtruth
However, when we doing experiments base on CASIA 2.0 datasets, we found that there are some<font color ="red"><b> serious noises</b></font> in groundtruth such as :
- Rotation mismatch
- Resolution mismatch
- Mask boundary mismatch

Here are some Examples:
- Rotation mismatch example on [Kaggle platform](https://www.kaggle.com/datasets/divg07/casia-20-image-tampering-detection-dataset):
  - ![](images/kaggle_example.jpg)
- Another Rotation mismatch example:
  - ![](images/rotation_mismatch.png)
- Resolution mismatch example:
  - ![](images/resolution_mismatch.png)

Because `resize()` is generally used in pre-processing, these dozens of problematic images are difficult to be detected from more than 5000 tampered images.

What's more, this dataset is widly use in the field of Image Tampering Detection to eavaluate model performance, and it's hard to find a second groundtruth dataset on the Internet, we have reason to believe that many papers have adopted this groundtruth as the validation of the CASIA 2.0 dataset.

## Fixed groundtruth downloading
Although these images can hardly have a significant impact on the training results of a dataset containing more than 5,000 images, we thought it would be useful to point out this issue for researchers to know. 

And here we place the Google Drive link of [corrected CASIA 2.0 dataset and it's ground truth ZIP file](https://drive.google.com/file/d/1JN93ts7VxJ4bbJL9TlE9uxM3ZeYuCN9M/view?usp=sharing), you can **DOWNLOAD** it through the link above.

Files in the ZIP are organized as follows:
```bash
├───Au          # Authentic images
├───Tp          # Tampered images
└───Gt          # Groundtruth images
```
## Index of all the wrong images
```
[["Tp_D_CNN_M_N_sec00011_cha00085_11227.jpg", [256, 384, 3], [384, 256, 3]], 
["Tp_D_CRN_S_N_ani10191_ani10190_12437.jpg", [638, 336, 3], [336, 638, 3]],  
["Tp_D_CRN_S_N_nat10130_pla00049_11524.jpg", [256, 384, 3], [384, 256, 3]], 
["Tp_D_NND_M_B_nat20098_nat20073_01602.tif", [387, 581, 3], [382, 581, 3]], 
["Tp_D_NRN_M_N_nat10134_nat00095_11912.jpg", [600, 600, 3], [475, 600, 3]], 
["Tp_D_NRN_M_N_nat10134_nat10124_11913.jpg", [600, 600, 3], [475, 600, 3]], 
["Tp_S_CRN_S_N_art00059_art00059_10508.tif", [256, 384, 3], [384, 256, 3]], 
["Tp_S_NND_S_N_sec20064_sec20064_01654.tif", [647, 416, 3], [636, 416, 3]], 
["Tp_S_NNN_S_N_art20077_art20077_01883.tif", [867, 578, 3], [864, 573, 3]], 
["Tp_S_NNN_S_N_ind20037_ind20037_01778.tif", [578, 863, 3], [569, 862, 3]], 
["Tp_S_NNN_S_N_sec00012_sec00012_11230.jpg", [256, 384, 3], [384, 256, 3]], 
["Tp_S_NNN_S_N_sec00074_sec00074_00751.tif", [384, 256, 3], [384, 255, 3]], 
["Tp_S_NRD_S_N_arc20079_arc20079_01719.tif", [392, 591, 3], [383, 582, 3]], 
["Tp_S_NRD_S_N_pla20071_pla20071_01971.tif", [501, 760, 3], [499, 760, 3]], 
["Tp_S_NRN_S_B_ind10002_ind10002_20010.jpg", [600, 450, 3], [800, 600, 3]], 
["Tp_S_NRN_S_N_art20077_art20077_02316.tif", [863, 574, 3], [863, 572, 3]], 
["Tp_S_NRN_S_N_pla20080_pla20080_01980.tif", [781, 514, 3], [781, 512, 3]]]
```
## Cite

You can visit [Nam Thanh Pham's CASIA 2.0 Groundtruth Github repo](https://github.com/namtpham/casia2groundtruth) to check their original Groundtruth. 

______

If you use the groundtruth dataset for **a scientific publication,** please cite the following papers:

* Official CASIA dataset

        @inproceedings{Dong2013,
        doi = {10.1109/chinasip.2013.6625374},
        url = {https://doi.org/10.1109/chinasip.2013.6625374},
        year = {2013},
        month = jul,
        publisher = {{IEEE}},
        author = {Jing Dong and Wei Wang and Tieniu Tan},
        title = {{CASIA} Image Tampering Detection Evaluation Database},
        booktitle = {2013 {IEEE} China Summit and International Conference on Signal and Information Processing}
        }


 * Official CASIA groundtruth dataset 
 
        @article{pham2019hybrid,
        title={Hybrid Image-Retrieval Method for Image-Splicing Validation},
        author={Pham, Nam Thanh and Lee, Jong-Weon and Kwon, Goo-Rak and Park, Chun-Su},
        journal={Symmetry},
        volume={11},
        number={1},
        pages={83},
        year={2019},
        publisher={Multidisciplinary Digital Publishing Institute}
        }
