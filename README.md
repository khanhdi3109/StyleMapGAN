
## Thesis K2018 - Computer Vision
<b> Image Editing based on Generative Adversarial Networks </b>
<p align="left"><img width="100%" src="assets/hinh_4_1_vn_celeb_toc.png" /></p>
Forked from naver-ai/StyleMapGAN - Offical Pytorch Implementation <br>
Original paper: <i>StyleMapGAN: Exploiting Spatial Dimensions of Latent in GAN for Real-time Image Editing </i><br>
Link paper: https://arxiv.org/abs/2104.14754 <br>

## Installation

![ubuntu](https://img.shields.io/badge/ubuntu-16.04.5_LTS-green.svg?style=plastic) ![gcc 7.4.0](https://img.shields.io/badge/gcc-7.4.0-green.svg?style=plastic) ![CUDA](https://img.shields.io/badge/CUDA-10.0.130-green.svg?style=plastic) ![CUDA-driver](https://img.shields.io/badge/CUDA_driver-410.72-green.svg?style=plastic) ![cudnn7](https://img.shields.io/badge/cudnn-7.6.3-green.svg?style=plastic) ![conda](https://img.shields.io/badge/conda-4.8.4-green.svg?style=plastic) ![Python 3.6.12](https://img.shields.io/badge/python-3.6.12-green.svg?style=plastic) ![pytorch 1.4.0](https://img.shields.io/badge/pytorch-1.4.0-green.svg?style=plastic)


Clone this repository:

```bash
git clone https://github.com/nguyenquyem99dt/StyleMapGAN.git
cd StyleMapGAN/
```

Install the dependencies:
```bash
conda create -y -n stylemapgan python=3.6.12
conda activate stylemapgan
./install.sh
```
Or via pip:
```bash
pip install -r requirements.txt
```

## Datasets
You can find LMDB datasets via the following link: <br>
https://drive.google.com/drive/folders/1dsaopj2l_KqO7vzlQnO-qOO0sj82VNfs?usp=sharing

## Pre-trained weights
Three pre-trained weights corresponding to VN-Celeb, CelebA-HQ and AFHQ datasets <br>
https://drive.google.com/drive/folders/1eZ2JXSVi-NpZvaBOliLWKnm4Uf_WKdIq?usp=sharing

## Demo
Upload LMDB datasets and pre-trained weights you downloaded to your google drive. <br>
Run the following notebook on Colab: <br>
https://colab.research.google.com/drive/1hFqHZZpd1tZL_Po5Z8rsR7EF4YyFYSQ4?usp=sharing

## Train network
Train network with small generator

```bash
# VN-Celeb
python train.py --dataset celeba_hq --train_data lmdb-data/vn_celeb/train --val_data lmdb-data/vn_celeb/val --small_generator

# CelebA-HQ
python train.py --dataset celeba_hq --train_data lmdb-data/celeba_hq/train --val_data lmdb-data/celeba_hq/val --small_generator

# AFHQ
python train.py --dataset afhq --train_data lmdb-data/afhq/train --val_data lmdb-data/afhq/val --small_generator
```

## Metrics
* Local editing: MSE (source & reference)
* Reconstruction: LPIPS, MSE
* Generation: FID

If you want to see more details, please follow the official file `metrics/README.md`.<br>
Or you can run the following notebooks:<br>
* VN-Celeb
https://colab.research.google.com/drive/1VSJX35k_bGhxNSlIGb3u2d1oRh3_DfIZ?usp=sharing
* CelebA-HQ
https://colab.research.google.com/drive/1coWv9sI5lh3AS6fAYDHbAYJMaWX9fAhv?usp=sharing
* AFHQ
https://colab.research.google.com/drive/1kPu7SQ00vC5dx0W4K8_feeP81gLzlUIH?usp=sharing

## License
(Official Repo) <br>
The source code, pre-trained models, and dataset are available under [Creative Commons BY-NC 4.0](LICENSE) license by NAVER Corporation. You can **use, copy, tranform and build upon** the material for **non-commercial purposes** as long as you give **appropriate credit** by citing our paper, and indicate if changes were made. 

For business inquiries, please contact clova-jobs@navercorp.com.<br/>	
For technical and other inquires, please contact hyunsu1125.kim@navercorp.com.

## Citation
If you find this work useful for your research, please cite our paper:
```
@inproceedings{kim2021stylemapgan,
  title={Exploiting Spatial Dimensions of Latent in GAN for Real-time Image Editing},
  author={Kim, Hyunsu and Choi, Yunjey and Kim, Junho and Yoo, Sungjoo and Uh, Youngjung},
  booktitle={Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition},
  year={2021}
}
```
