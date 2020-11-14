# MATANet
This repository is the code of paper "Multi-scale Adaptive Task Attention Network for Few-shot Learning".

Our code will be released until the paper received.

# Citation
If you find our work useful, please consider citing our work using the bibtex:
```
@article{chen2020mata,
  title={MATA: Multi-scale Adaptive Task Attention Network for Few-shot Learning},  
  author={Chen,Haoxing and Li, Huaxiong and Li, Yaohui and Chen, Chunlin},  
  journal={arXiv preprint arXiv:xxx},  
  year={2020}
}
```

# Prerequisites
* Linux
* Python 3.6
* Pytorch 1.0+
* GPU + CUDA CuDNN
* pillow, torchvision, scipy, numpy

# Datasets
* [miniImageNet](https://drive.google.com/file/d/1fUBrpv8iutYwdL4xE1rX_R9ef6tyncX9/view)
* [CUB-200-2011](http://www.vision.caltech.edu/visipedia/CUB-200-2011.html)
* [Stanford Dog](http://vision.stanford.edu/aditya86/ImageNetDogs/)
* [Stanford Car](https://ai.stanford.edu/~jkrause/cars/car_dataset.html)

# miniImageNet Few-shot Classification
* Train a 5-way 1-shot model based on Conv-64F:
```
python MATA_Train_5way1shot.py --dataset_dir ./datasets/miniImageNet --data_name miniImageNet
```
Test model on the test set:
```
python MATA_Test_5way1shot.py --dataset_dir ./datasets/miniImageNet --data_name miniImageNet --resume ./results/MATA_miniImageNet_MATA64_5Way_1Shot/model_best_test.pth.tar 
```
# Fine-grained Few-shot Classification
* Data prepocessing (e.g., CUB-200-2011).
* Run the preprocessing script.
```
python ./dataset/CUB200_preprocessing.py
```
* Train a 5-way 1-shot model based on Conv-64F:
```
python MATA_Train_5way1shot.py --dataset_dir ./datasets/CUB_200_2011 --data_name CUBBirds
```
Test model on the test set:
```
python MATA_Test_5way1shot.py --dataset_dir ./datasets/CUB_200_2011 --data_name CUBBirds --resume ./results/MATA_CUBBirds_MATA64_5Way_1Shot/model_best_test.pth.tar 
```
# Contacts
Please feel free to contact us if you have any problem.

Email: haoxingchen@smail.nju.edu.cn


Our code is based on [CovaMNet](https://github.com/WenbinLee/CovaMNet).

