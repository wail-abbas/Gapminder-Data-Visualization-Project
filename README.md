# Gapminder: Data Visualization Project:

### Objectives:
#### This project aims to:
* analyze the Gapminder datasets.
* Visualize the correlation between each country's population and fertiliy rate.
* Generate a gif image using python and matplotlib.

 
#### Life Expectancy vs. Fertility:
![wail](lifeexp.gif)



![Build Status](https://github.com/agrivero-ai/experiments/workflows/Python%20Testing/badge.svg)

# experiments
Code for the research phase of R&amp;D. Results will be input for production code.


### Setting up docker:

    ##### 1.Install the latest NVIDIA drivers:
        $ sudo ubuntu-drivers devices
        $ sudo ubuntu-drivers autoinstall
        $ sudo reboot

    ##### 2. Install Docker:
        2.1 Follow [instructions here](https://docs.docker.com/engine/install/ubuntu/).
        2.2 Check Docker version:
            $ docker -v
        2.3 Make sure you have installed Docker correctly:
            $ docker run hello-world

    ##### 3. Install the NVIDIA Container toolkit:
        3.1 Follow [instructions here](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html#docker).
        3.2 Make sure you have installed NVIDIA Container toolkit correctly:
            $ docker run --gpus all --rm nvidia/cuda nvidia-smi

    ##### 4. Download TensorFlow Docker images with GPU support:
        4.1 Pull tensorflow:
            $ docker pull tensorflow/tensorflow:2.5.0-gpu-jupyter
        4.2 Run tensorflow:
            $ docker run --gpus all -it -p 8888:8888 -v <path to experiments folder>:/tf/agrivero/ tensorflow/tensorflow:2.5.0-gpu-jupyter
        4.3 Instal OpenCV:
            4.3.1 inside jupyter notebook:
                $ pip install opencv-python
            4.3.2 In the terminal, list the running containers:
                $ docker ps
            Copy the CONTAINER ID of tensorflow image and palace it in the following command.
                $ docker commit <CONTAINER ID> tensorflow/tensorflow:2.5.0-gpu-jupyter-opencv
            You can also check [This Link](https://docs.docker.com/engine/reference/commandline/commit/)
        4.4 Run tensorflow with OpenCV:
            $ docker run --gpus all -it -p 8888:8888 -v <path to experiments folder>:/tf/agrivero/ tensorflow/tensorflow:2.5.0-gpu-jupyter-opencv
