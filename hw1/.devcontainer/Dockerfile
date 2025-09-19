FROM mcr.microsoft.com/devcontainers/python:3.11

# Avoid prompts from apt
ENV DEBIAN_FRONTEND=noninteractive

# Install OS deps
RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        git \
        build-essential \
        wget \
        ca-certificates \
    && rm -rf /var/lib/apt/lists/*

# Upgrade pip first
RUN python -m pip install --upgrade pip

# Install Python packages
RUN pip install --no-cache-dir \
    ipykernel==6.29.5 \
    jupyter==1.1.1 \
    numpy==2.1.1 \
    scipy==1.14.1 \
    matplotlib==3.9.2 \
    pandas==2.2.3 \
    tqdm==4.66.5 \
    Pillow==10.4.0 \
    scikit-learn==1.5.2

# Install CPU-only PyTorch (latest compatible)
RUN pip install --no-cache-dir torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cpu

# Default to bash
SHELL ["/bin/bash", "-lc"]


