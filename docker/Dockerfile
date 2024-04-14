FROM nvcr.io/nvidia/cuda:11.8.0-cudnn8-devel-ubuntu22.04

RUN apt-get update \
    && apt-get install -y --no-install-recommends git git-lfs python3 python3-pip \
    && apt-get install -y --no-install-recommends libgl1-mesa-glx libglib2.0-0 \
    && curl -s https://packagecloud.io/install/repositories/github/git-lfs/script.deb.sh | bash \
    && git lfs install \
    && rm cuda-keyring_1.0-1_all.deb \
    && ln -s /usr/bin/python3 /usr/bin/python \
    && rm -rf /var/lib/apt/lists/*

RUN apt-get update \
    && apt-get install -y --no-install-recommends wget \
    && rm -rf /var/lib/apt/lists/*

RUN pip3 install --no-cache-dir torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118

RUN git clone --depth 1 https://github.com/ali-vilab/Ranni.git \
    && cd Ranni && mkdir models \
    && pip3 install --no-cache-dir \
        gradio==3.44.2 \
        albumentations==1.3.0 \
        opencv-contrib-python==4.7.0.72 \
        opencv-python-headless==4.7.0.72 \
        imageio==2.9.0 \
        imageio-ffmpeg==0.4.2 \
        pytorch-lightning==1.5.0 \
        omegaconf==2.1.1 \
        test-tube>=0.7.5 \
        streamlit==1.12.1 \
        einops==0.3.0 \
        transformers==4.30.2 \
        webdataset==0.2.5 \
        kornia==0.6 \
        open_clip_torch==2.24.0 \
        invisible-watermark>=0.1.5 \
        streamlit-drawable-canvas==0.8.0 \
        torchmetrics==0.6.0 \
        timm==0.6.12 \
        addict==2.4.0 \
        yapf==0.32.0 \
        prettytable==3.6.0 \
        safetensors==0.4.2 \
        basicsr==1.4.2 \
        peft==0.3.0

WORKDIR /Ranni