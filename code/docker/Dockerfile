FROM nvcr.io/nvidia/rapidsai/base:23.12-cuda12.0-py3.10
USER root
RUN apt-get update && apt-get install -y git
# Copy the requirements file
COPY requirements.txt /tmp/requirements.txt
# Install PyTorch and dependencies
RUN pip install torch torchvision torchaudio
# Install packages from requirements.txt
RUN pip install --no-cache-dir -r /tmp/requirements.txt
# Clean up
RUN rm /tmp/requirements.txt
# Setup hf cache
RUN mkdir /mnt/ceph_rbd/hf_cache
RUN export XDG_CACHE_HOME=/mnt/ceph_rbd/hf_cache
