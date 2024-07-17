FROM nvcr.io/nvidia/rapidsai/base:23.12-cuda12.0-py3.10
USER root
# Install commands
RUN apt-get update && apt-get install -y git
RUN apt-get install -y vim
RUN apt-get install -y build-essential
RUN apt-get install -y wget
# Copy the requirements file
COPY requirements.txt /tmp/requirements.txt
# Install alignscore
RUN git clone https://github.com/yuh-zha/AlignScore.git
RUN cd AlignScore && pip install .
# Install packages from requirements.txt
RUN pip install --no-cache-dir -r /tmp/requirements.txt
RUN pip install -U transformers huggingface-hub
RUN pip install vllm==0.5.1
# Clean up
RUN rm /tmp/requirements.txt
RUN cd .. && rm -rf AlignScore