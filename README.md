# **COMET**
## Project Overview
![image](https://github.com/wulibingbinglin/COMET/blob/main/images/process.jpg)
COMET address spacecraft pose estimation from a monocular RGB sequence with known intrinsics. The framework consists of two key modules. First, Trajectory-Guided Temporal Modeling integrates patch-level image features with point trajectories and continuous-time encodings, enabling long-range temporal reasoning and reducing reliance on explicit priors. Second, Geometry-Aware Pose Regression (GAPR) jointly estimates rotation quaternions, image-plane translations, and relative depth from the fused spatio-temporal representation.
## Installation

This project requires Python 3.10+ and CUDA >=12.1 for GPU support.  
We provide a minimal `requirements_min.txt` for pip-installable packages, and some dependencies (like PyTorch3D) need conda.
### 1. Create a new conda environment
```bash
conda create -n vggsfm python=3.10 -y
conda activate vggsfm
```
### 2. Install PyTorch & torchvision
```bash
# Install PyTorch 2.1 and torchvision with CUDA 12.1 support
conda install pytorch=2.1 torchvision pytorch-cuda=12.1 -c pytorch -c nvidia -y
```
### 3. Install dependency packages
```bash
# Upgrade pip first
python -m pip install --upgrade pip

# Install all required packages
python -m pip install -r requirements_min.txt
```
## Dataset
```bash
dataset_root/
└── seq1/
    ├── 000000/
    │   ├── frame/               # Images / video frames
    │   ├── GroundTruth/         # Ground-truth annotations
    │   ├── Mask/                # Masks for segmentation or other tasks
    │   ├── scene_camera.json    # Camera parameters and metadata
    │   └── scene_gt.json        # Scene ground-truth (pose, position, etc.)
└── seq2/
    ├── 000000/
    │   ├── frame/
    │   ├── GroundTruth/
    │   ├── Mask/
    │   ├── scene_camera.json
    │   └── scene_gt.json
```
## Training & Testing
> python train.py 
> python test.py 
