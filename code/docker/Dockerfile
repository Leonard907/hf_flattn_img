FROM nvcr.io/nvidia/rapidsai/base:23.12-cuda12.0-py3.10
USER root
RUN apt-get update && apt-get install -y git
RUN apt-get install vim
# Copy the requirements file
COPY requirements.txt /tmp/requirements.txt
# Install PyTorch and dependencies
RUN pip install torch torchvision torchaudio
# Install packages from requirements.txt
RUN pip install --no-cache-dir -r /tmp/requirements.txt
# Clean up
RUN rm /tmp/requirements.txt
