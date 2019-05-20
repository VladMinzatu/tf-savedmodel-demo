# tf-savedmodel-demo

This repository demos the functionality of saving and loading models in TensorFlow 2.0.

### Repository structure

The `./notebooks` directory contains the Jupyter notebooks that produce the models and save them.

The `./models` directory is where the models are saved, in subdirectories having names that match the notebooks producing them.

The `./applications` directory contains examples of loading and using the saved models.

### Running the notebooks

The notebooks can be run using the TensorFlow 2.0 Docker image and then accessing the `notebooks` directory:

```
docker run -it --rm -v $(pwd):/tf -p 8888:8888 tensorflow/tensorflow:2.0.0a0-gpu-py3-jupyter
```


