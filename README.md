# AUB

Source code for the paper:

  > [Why be adversarial? Let's cooperate!: Cooperative Dataset Alignment via JSD Upper Bound](https://openreview.net/forum?id=kcadk-DShNO) 
  > ICLR 2022 Conference Blind Submission

## Prerequisites
- Linux
- Python 3.8
- CPU or NVIDIA GPU + CUDA CuDNN

## Getting Started

### Installation
Download files from https://anonymous.4open.science/r/AUB
(Note that the individual file should be downloaded respectively.)

### Dataset
The dataset is exactly same with the original MNIST data (http://yann.lecun.com/exdb/mnist/)
`unzip data.zip`

#### Environment setup
1. `conda env create -f environment.yml`
2. `source activate aub`
   
### Usage 
```bash 

python run.py --multi_gpu False --setting demo --batch_size 128 --gpu_id 0 --lr 2e-4 --lambda_TC 0.0

```
- The option `--multi_gpu` is used for GPU parallelization. The code only support for running on a single GPU now. 
  The option `--setting` is the name of current experiment.
  The option `--batch_size` determines how large each batch should be feed to the GPU at once. The value of this option varies among different GPUs.
  The option `--gpu_id` select which GPU the experiment will be run on. Default is 0.
  Learning rate is determined by option `--lr`.
  Regularization for AUB is controlled by option `lambda_TC`, `0` means no regularization.