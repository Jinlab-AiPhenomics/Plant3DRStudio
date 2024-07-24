# Benchmarking NeRF and 3D Gaussian Splatting Methods in Plant Phenotyping  



![image-20240723165409421](./assets/overview.png)

This repo contains the official implementation for the paper "Benchmarking NeRF and 3D Gaussian Splatting Methods in Plant Phenotyping ". Our work compares the application effects of MVS-based, NeRF-based, and Gaussian-based 3D reconstruction technologies on plant phenotyping. Furthermore, we have integrated multiple algorithms into a large-scale project, enabling convenient experimentation with different algorithms simply by modifying the configuration files. In addition, we have provided datasets of soybeans and poplars (COLMAP dataset) and welcome everyone to use them.

## Installation

```bash
# download
git clone https://github.com/hbb1/2d-gaussian-splatting.git --recursive

# if you have an environment used for 3dgs, use it
# if not, create a new environment
conda env create --file environment.yml
conda activate surfel_splatting
```

## Training



```bash
python train.py -s <path to COLMAP or NeRF Synthetic dataset>
```



## Testing

```
python render.py -m <path to pre-trained model> -s <path to COLMAP dataset> 
```



## Evaluating

```bash
python scripts/mipnerf_eval.py -m60 <path to the MipNeRF360 dataset>
```



## Acknowledgements

This project is built upon [3DGS](https://github.com/graphdeco-inria/gaussian-splatting). The TSDF fusion for extracting mesh is based on [Open3D](https://github.com/isl-org/Open3D). The rendering script for MipNeRF360 is adopted from [Multinerf](https://github.com/google-research/multinerf/), while the evaluation scripts for DTU and Tanks and Temples dataset are taken from [DTUeval-python](https://github.com/jzhangbs/DTUeval-python) and [TanksAndTemples](https://github.com/isl-org/TanksAndTemples/tree/master/python_toolbox/evaluation), respectively. We thank all the authors for their great repos. 

