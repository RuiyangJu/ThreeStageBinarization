## [Three-stage binarization of color document images based on discrete wavelet transform and generative adversarial networks](https://arxiv.org/)
### Stage-1 Flowchart
<p align="center">
  <img src="Figure/figure_stage_1.jpg" width="480" title="Stage-1">
</p>

### Stage-2 Flowchart
<p align="center">
  <img src="Figure/figure_stage_2.jpg" width="480" title="Stage-2">
</p>

### Stage-3 Flowchart
<p align="center">
  <img src="Figure/figure_stage_3.jpg" width="480" title="Stage-3">
</p>

## Abstract
The efficient segmentation of foreground text information from the background in degraded color document images is a topic of concern. Due to the imperfect preservation of ancient documents over a long period of time, various types of degradation, including staining, yellowing, and ink seepage, have seriously affected the results of image binarization. In this paper, a three-stage method is proposed for image enhancement and binarization of degraded color document images by using discrete wavelet transform (DWT) and generative adversarial network (GAN). In Stage-1, we use DWT and retain the LL subband images to achieve the image enhancement. In Stage-2, the original input image is split into four (Red, Green, Blue and Gray) single-channel images, each of which trains the independent adversarial networks. The trained adversarial network models are used to extract the color foreground information from the images. In Stage-3, in order to combine global and local features, the output image from Stage-2 and the original input image are used to train the independent adversarial networks for document binarization. The experimental results demonstrate that our proposed method outperforms many classical and state-of-the-art (SOTA) methods on the Document Image Binarization Contest (DIBCO) dataset.

## Requirements
* Linux (Ubuntu)
* Python >= 3.6
* NVIDIA GPU + CUDA CuDNN

## Installation
* Install [segmentation_models](https://github.com/qubvel/segmentation_models.pytorch)
```
    pip install segmentation-models-pytorch
```
* Install [pytesseract](https://github.com/madmaze/pytesseract)
```
    pip install pytesseract
```
* Download [tesseract data](https://github.com/tesseract-ocr/tessdata_best)
```
    conda env create -f environment.yml
```

## Dataset
* Train: 
  
  DIBCO 2009, H-DIBCO 2010, H-DIBCO 2012, PHIBD, SMADI, Bickley Diary Dataset
  [(Download Link)](https://www.dropbox.com/s/3qwv3jntmgu4rf9/Trainset.zip?dl=0)
  
* Test: 

  DIBCO 2011, DIBCO 2013, H-DIBCO 2014, H-DIBCO 2016, DIBCO 2017, H-DIBCO2018
  [(Download Link)](https://www.dropbox.com/s/54ye0mtdcvqas4o/Testset.zip?dl=0)

## Usage
* Patch per datasets
```
    python3 image_to_256.py
    python3 image_to_512.py
```
* Discrete Wavelet Transform
```
    python3 image_dwt_original.py
    python3 image_dwt_256.py
```
<p align="center">
  <img src="select_image/(original_image)2_split_3_colors/0_blue.png" width="240" title="blue">
</p>
<p align="center">
  <img src="select_image/(original_image)2_split_3_colors/0_green.png" width="240" title="green">
</p>
<p align="center">
  <img src="select_image/(original_image)2_split_3_colors/0_red.png" width="240" title="red">
</p>


optional arguments:

    --lr                default=1e-3    learning rate
    --epoch             default=200     number of epochs tp train for
    --trainBatchSize    default=100     training batch size
    --testBatchSize     default=100     test batch size


## References
[DocumentBinarization](https://github.com/opensuh/DocumentBinarization)
