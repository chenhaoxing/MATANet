# Multi-scale Adaptive Task Attention Network for Few-Shot Learning
This code implements the Multi-scale Adaptive Task Attention Network (MATANet).

Our code will be released soon.

## Citation
If you find our work useful, please consider citing our work using the bibtex:
```
@Article{chen2020multi,
	author  = {Chen, Haoxing and Li, Huaxiong and Li, Yaohui and Chen, Chunlin},
	title   = {Multi-scale Adaptive Task Attention Network for Few-Shot Learning},
	journal = {arXiv preprint arXiv:2011.14479},
	year    = {2020},
}
```

## Prerequisites
* Linux
* Python 3.6
* Pytorch 1.0+
* GPU + CUDA CuDNN
* pillow, torchvision, scipy, numpy

## Datasets
**Dataset download link:**
* [miniImageNet](https://drive.google.com/file/d/1fUBrpv8iutYwdL4xE1rX_R9ef6tyncX9/view)
* [CUB-200-2011](http://www.vision.caltech.edu/visipedia/CUB-200-2011.html)
* [Stanford Dog](http://vision.stanford.edu/aditya86/ImageNetDogs/)
* [Stanford Car](https://ai.stanford.edu/~jkrause/cars/car_dataset.html)

**Note: You need to manually change the dataset directory.**

## miniImageNet Few-shot Classification
* Train a 5-way 1-shot model based on Conv-64F:
```
python MATA_Train_5way1shot.py --dataset_dir ./datasets/miniImageNet --data_name miniImageNet
```
Test model on the test set:
```
python MATA_Test_5way1shot.py --dataset_dir ./datasets/miniImageNet --data_name miniImageNet --resume ./results/MATA_miniImageNet_MATA64_5Way_1Shot/model_best_test.pth.tar 
```
## Fine-grained Few-shot Classification
* Data preprocessing (e.g., CUB-200-2011).
* Run the preprocessing script.
```
python ./dataset/CUB_200_2011_preprocessing.py
```
* Train a 5-way 1-shot model based on Conv-64F:
```
python MATA_Train_5way1shot.py --dataset_dir ./datasets/CUB_200_2011 --data_name CUBBirds
```
Test model on the test set:
```
python MATA_Test_5way1shot.py --dataset_dir ./datasets/CUB_200_2011 --data_name CUBBirds --resume ./results/MATA_CUBBirds_MATA64_5Way_1Shot/model_best_test.pth.tar 
```
## Pretrained models
We also provide some of the pre-trained models.
You can run the following command to evaluate the model
```
python MATA_Test_5way1shot_fg.py --dataset_dir ./datasets/CUB_200_2011 --data_name CUBBirds --resume ./results/MATA_CUBBirds_MATA64_5Way_1Shot/model_best_test.pth.tar 
```


## Contacts
Please feel free to contact us if you have any problems.

Email: haoxingchen@smail.nju.edu.cn


