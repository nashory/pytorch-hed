# hed_pytorch

Pytorch implementation of [Holistically-nested Edge Detection (HED)][1]. This repo can be used to train a HED model and perform test inference. The implementation was evaluated on the BSDS dataset.

* [Prerequisites](#prerequisites)
* [Usage](#usage)
* [Performance](#performance)
* [Files](#files)
* [Acknoledgement](#acknowledgement)
* [References](#references)

## Prerequisites

* Compute environment with GPU (optional).
* Python environment: [Anaconda](https://conda.io/docs/user-guide/install/index.html) is recommended.
* SciPy stack: [Install instructions](https://www.scipy.org/install.html).
* [Optional] CUDA and NVidia Drivers: [Install instructions](https://developer.nvidia.com/cuda-downloads).
* Pytorch: [Install instructions](http://pytorch.org/).

I use docker to avoid dependency problems. Installation instructions for my setup are available [here](Install.md).

## Usage

* Download repository:
  ```
  $ git clone https://github.com/buntyke/hed_pytorch.git
  ```
* Create `data` folder, download and extract BSDS dataset into folder:
  ```
  $ cd hed_pytorch/
  $ mkdir data; cd data
  $ wget http://vcl.ucsd.edu/hed/HED-BSDS.tar
  $ tar -xvf HED-BSDS.tar
  $ rm HED-BSDS.tar
  ```
* Create output folder to save results:
  ```
  $ mkdir output
  ```
* Train HED model by running `train.ipynb` in jupyter-notebook and following the instructions:
  ```
  $ jupyter notebook 
  ```
  The trained model along with validation results are stored in the output folder.

## Performance

* 

## Files

* [train.ipynb](train.ipynb): Notebook to train HED model.
* [trainer.py](trainer.py): Helper class to train model and perform validation.
* [model.py](model.py): HED model definition given through several class implementations.
* [dataproc.py](dataproc.py): Dataset class implementation used in Trainer class.

## Acknowledgement

The source code is derived from three different implementations available online. Thanks to [@s9xie][2] for original caffe implementation. Thanks to [@EliasVansteenkiste][3] and [@xlliu][4] for the pytorch implementations.

[1]: https://arxiv.org/abs/1504.06375 "HED"

[2]: https://github.com/s9xie/hed "Caffe"

[3]: https://github.com/EliasVansteenkiste/edge_detection_framework "Pytorch 1"

[4]: https://github.com/xlliu7/hed.pytorch "Pytorch 2"