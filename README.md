# Docker for Stable Diffusion WebUI Forge

The Dockerfile pull the latest HEAD from lllyasviel SD Webui (https://github.com/lllyasviel/stable-diffusion-webui-forge).

# docker-shared filestructure
Create a folder $HOME/docker-shared to hold models instead of having them copied on every container run:
```
docker-shared/
├── checkpoints/
├── embeddings/
├── loras/
├── upscaler/
└── vae/
```

To build the image:
$ cd docker-forge
$ docker build -t forge .
$ docker run --gpus all -p 7860:7860 -v $HOME/docker-shared:/app/repo/docker-shared forge
