# Deep3P-Denoising
Deep3P Denoising: Code of the 3PM-Noise2Void and PerStruc-Denoiser Method
## Table of Contents

- [Deep3P-Denoising](#deep3p-denoising)
  - [Table of Contents](#table-of-contents)
  - [Dataset](#dataset)
  - [Installation](#installation)
  - [How-To-Run](#how-to-run)
    - [Further information](#further-information)
  - [Future Work](#future-work)
  - [References](#references)
  - [License](#license)
  - [Acknowledgements](#acknowledgements)

## Dataset

- **Description:** The data used in this research project consisted of structural signals of mGFP-labeled intravital glioblastoma cells and their THG signals in the deep layers of the mouse brain, recorded using three-photon microscopy. These data are time-series of 3D volumes showing the temporal changes of glioblastoma cells and its THG signal.
- **Preprocessing:** Before the time-series of 3D-data can be used for training or inference, it must be preprocessed. This includes registration, alignment, and cropping of translational borders. Each single 3D-time stamp is treated separately for the training and inference of the 3PM-N2V. 

## Installation

To install and use these denoising methods, follow these steps:

- Clone the repository using the following command in your terminal:
```sh
git clone https://github.com/emanuelmaus/Deep3P-Denoising.git
```
- Navigate to the cloned repository by using the following command:
```sh
cd Deep3P-Denoising
```
- Install all dependencies by creating a new environment using the [**Deep3P_Denoising.yml**](Deep3P_Denoising.yml):
```sh
conda env create --file Deep3P_Denoising.yml
```
- Activate the new environment:
```sh
conda activate Deep3P_Denoising
```
- To reduce training and inference time, access to a GPU is highly recommended. The [**NVIDIA CUDA Toolkit**](https://developer.nvidia.com/cuda-downloads) and the [**NVIDIA CUDA Deep Neural Network (cuDNN)**](https://docs.nvidia.com/deeplearning/cudnn/index.html) library are needed to accelerate the processing. Check which [**PyTorch packages**](https://pytorch.org/) is compatible with the system used by selecting the correct operating system and compute platform. Run the generated command in your terminal. The command will look similar to the following:
```sh
conda install pytorch torchvision torchaudio pytorch-cuda=11.6 -c pytorch -c nvidia
``` 
- Navigate to the notebooks containing the denoising methods by using following command:
```sh
cd notebooks
```
- Launch Jupyter-lab by typing ``jupyter-lab`` in your terminal and run the corresponding notebooks.

Typical install time is 15-30 minutes. 

## How-To-Run


There are three notebooks for **training** ([``01_Training-3PM-Noise2Void.ipynb``](notebooks/01_Training-3PM-Noise2Void.ipyn)), **inference** ([``02_Inference-3PM-Noise2Void.ipynb``](notebooks/02_Inference-3PM-Noise2Void.ipynb)), and **PerStruc-Denoiser** ([``03_PerStruc-Denoiser.ipynb``](notebooks/03_PerStruc-Denoiser.ipynb)).
The sequence of execution is as follows
1. [**Training: 3PM-Noise2Void**](notebooks/01_Training-3PM-Noise2Void.ipyn)
2. [**Inference: 3PM-Noise2Void**](notebooks/02_Inference-3PM-Noise2Void.ipynb) 
3. [**PerStruc-Denoiser**](notebooks/03_PerStruc-Denoiser.ipynb)

Each notebook provides an easy-to-use tutorial on how to use it. Code sections, which can be changed to test new parameters or adapt to new data, are marked as following:
```Python
# Select...    #

Typical run-time for the entire demoset is 30-60 minutes.

#**************#
```

### Further information

For more detailed information about the code and its functionality, please refer to the [documentation file](/docs/documentation/Documentation.txt) and the code itself, which includes comments explaining the various functions and steps. Additionally, you may contact the authors for further assistance or clarification.

This code has been tested successfully on a Windows-PC with a NVIDIA GeForce RTX 3060.

## Future Work

- [X] Document the code

## References

1. Alexander Krull et al., "Noise2Void - Learning Denoising from Single Noisy Images", In: CVPR 2019 
2. Eva Höck et al., "N2V2 - Fixing Noise2Void Checkerboard Artifacts with Modified Sampling Strategies and a Tweaked Network Architecture", In: ECCV 2022
3. Xinyang Li et al., “Reinforcing neuron extraction and spike inference in calcium imaging using deep self-supervised denoising”, In: Nat. Methods 2021
4. Kisuk Lee et al., "Superhuman Accuracy on the SNEMI3D
Connectomics Challenge", In: NIPS 201

## License

Copyright (C) 2021-2023 Emanuel Maus

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation; either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program. If not, see [https://www.gnu.org/licenses/](https://www.gnu.org/licenses/).

## Acknowledgements

This code was developed and implemented by Emanuel Maus as part of the **Deep3P** project, with guidance and consultation of [Robert Prevedel](https://www.prevedel.embl.de/), [Lina Streich](https://www.prevedel.embl.de/) and [Amr Tamimi](https://www.prevedel.embl.de/). The data used in this project was kindly provided by [Varun Venkataramani](https://www.klinikum.uni-heidelberg.de/personen/dr-med-varun-venkataramani-6982) and his research group. If you have any questions, suggestions, or have noticed any bugs, please feel free to contact me at emanuel.maus AT embl DOT de.
