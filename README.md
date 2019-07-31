# OAG

OAG: Toward Linking Large-scale Heterogeneous Entity Graphs.<br>
Fanjin Zhang, Xiao Liu, Jie Tang, Yuxiao Dong, Peiran Yao, Jie Zhang, Xiaotao Gu, Yan Wang, Bin Shao, Rui Li, and Kuansan Wang.<br>
In KDD 2019 (Applied Data Science Track)

## Prerequisites

- Linux or macOS
- Python 3
- TensorFlow GPU >= 1.14
- NVIDIA GPU + CUDA cuDNN

## Getting Started

### Installation

Clone this repo.

```bash
git clone https://github.com/THUKG/OAG
cd OAG
```

Please install dependencies by

```bash
pip install -r requirements.txt
```
### Dataset

The dataset can be downloaded from [OneDrive](https://mailstsinghuaeducn-my.sharepoint.com/:u:/g/personal/zfj17_mails_tsinghua_edu_cn/ES2s-PhyDeREs1zk0qdnA08BhzBZRSzrzKCqGAjEvdGBVQ?e=6U3bOd) or [BaiduPan](https://pan.baidu.com/s/1ZkIs89yy9TrDMssZ3ceeVw) (with password gzpp). Unzip the file and put the _data_ directory into project directory.

## How to run
```bash
cd $project_path
export PYTHONPATH="$project_path:$PYTHONPATH"
export CUDA_VISIBLE_DEVICES='?'  # specify which GPU(s) to be used
cd core

# venue linking
python rnn/train.py

# paper linking
### LSH method
python hash/title2vec.py  # train doc2vec model
python hash/hash.py
### CNN method
python cnn/train.py

# author linking
python gat/preprocessing.py
python gat/train.py
