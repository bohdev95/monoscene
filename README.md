entioned in https://github.com/astra-vision/MonoScene/issues/18 

# Preparing MonoScene

## Installation

1. Create conda environment:

```
$ conda create -y -n monoscene python=3.7
$ conda activate monoscene
```
2. This code was implemented with python 3.7, pytorch 1.7.1 and CUDA 10.2. Please install [PyTorch](https://pytorch.org/): 

```
$ conda install pytorch==1.7.1 torchvision==0.8.2 torchaudio==0.7.2 cudatoolkit=10.2 -c pytorch
```

3. Install the additional dependencies:

```
$ cd MonoScene/
$ pip install -r requirements.txt
```

4. Install tbb:

```
$ conda install -c bioconda tbb=2020.2
```

5. Downgrade torchmetrics to 0.6.0
```
$ pip install torchmetrics==0.6.0
```

6. Finally, install MonoScene:

```
$ pip install -e ./
```
7. Configurations
Setup your dataset and output data paths in 
```
MonoScene/monoscene/config/monoscene.yaml
```

# Docker Setup
Here is Docker setup for MonoScene. You can use the following commands to build the docker image and run the container.

Clone the git repository
```
git clone https://github.com/astra-vision/MonoScene.git
cd MonoScene
```
Pull docker image
```
docker pull sohaibanwaar/monoscene
```
Run docker Image
```
docker run -it -p 8888:8888 --gpus all -v /path/to/MonoScene:/MonoScene sohaibanwaar/monoscene /bin/bash
```
Activate Environment
```
conda activate monoscene
```
Run Jupyter Notebook inside docker container
```
```
jupyter notebook --ip 0.0.0.0 --no-browser --allow-root 
```
Get the token from the terminal and paste it in the jupyter notebook page. You are good to go.

Go to the link provided in the terminal and copy the token and paste it in the jupyter notebook page. You are good to go.

```
https://localhost:8888/?token=xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

You also need to install some packages used by the visualization scripts using the commands:
```
pip install tqdm
pip install omegaconf
pip install hydra-core
```

## Inference Notebooks

We provide two notebooks to run inference on the NYUv2 and KITTI datasets. The notebooks are located in the `notebooks` folder.

### For Prediction go to notebook
[Prediction Notebook](jupyter_notebooks/predict_room_3d_model.ipynb)

in this notebook we also place code to store pkl file. 

### For Visualization go to notebook
For mayaavi visualization go to notebook

[Visualisation Notebook](jupyter_notebooks/Plot_3d_model.ipynb)