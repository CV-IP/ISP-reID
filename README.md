# ISP-reID

We propose the Identity-Guided Human Semantic Parsing approach (ISP) to locate both the human body parts and personal belongings at pixel-level for person re-ID only with person identity labels.
ISP-reID is based on the open project, [reid strong baseline](https://github.com/michuanhaohao/reid-strong-baseline).


## Installation

1. 'cd' to folder where you want to download this repo

2. Run 'git clone https://github.com/CASIA-IVA-Lab/ISP-reID.git'

3. Install dependencies:
    - [pytorch>=1.2.0](https://pytorch.org/)
    - torchvision
    - [ignite](https://github.com/pytorch/ignite)
    - [yacs](https://github.com/rbgirshick/yacs)

4. Install faiss from [faiss](https://github.com/facebookresearch/faiss/blob/master/INSTALL.md)

## Re-ID Dataset Preparation

Create a directory to store reid datasets under this repo or outside this repo. Remember to set your path to the root of the dataset in `config/defaults.py` for all training and testing or set in every single config file in `configs/` or set in every single command.

Take 'DukeMTMC-reID' for exmaple:

Extract dataset to 'DukeMTMC-reID'. The data structure would like:

    ```bash
    data
        DukeMTMC-reID
            	bounding_box_test/
            	bounding_box_train/
                bounding_box_train_parsing_pgt/
            	......
    ```
'bounding_box_train_parsing_pgt' is the predicted ground-truth generated by [SCHP](https://github.com/PeikeLi/Self-Correction-Human-Parsing). We have generated the predicted ground-truth for person re-ID datasets on [PGT](https://pan.baidu.com/s/1uqlZHxTtWeTL5kenpD5iaA), code: m6n5.

## Pre-trained Model Preparation

Download the pre-trained [HRNet32](https://arxiv.org/abs/1902.09212) on ImageNet from [Model](https://pan.baidu.com/s/1L-CLWFX-8BJl9m6XAjB1GA), code: r1o2.

## Train

For your convenience, we provide the bash scripts with our recommended settings. Please 'cd' to the root path of this repo and run:

`bash ./ISP-*.sh`

## Reference

We hope that this technique will benefit more computer vision related applications and inspire more works.
If you find this technique and repository useful, please cite the paper. Thanks!

```
@article{zhu2020identity,
  title={Identity-Guided Human Semantic Parsing for Person Re-Identification},
  author={Zhu, Kuan and Guo, Haiyun and Liu, Zhiwei and Tang, Ming and Wang, Jinqiao},
  journal={ECCV},
  year={2020}
}
```

