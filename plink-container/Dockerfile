# syntax=docker/dockerfile:1

# Base image from Ubuntu
FROM ubuntu:22.04

#Metadata (declaring ownership)
LABEL maintainer="4129565@myuwc.ac.za"

# Install dependencies, inlc for conda
RUN apt-get update && apt-get install -y --no-install-recommends \
  wget bzip2 ca-certificates curl git \
  && rm -rf /var/lib/apt/lists/*

# Install Miniconda
RUN wget --quiet https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O /tmp/miniconda.sh \
  && bash /tmp/miniconda.sh -b -p /opt/conda \
  && rm /tmp/miniconda.sh \
  && /opt/conda/bin/conda clean -afy

# Add conda to PATH
ENV PATH=/opt/conda/bin:$PATH

# Configure conda channels and accept Terms of Service
RUN conda config --add channels defaults \
  && conda config --add channels bioconda \
  && conda config --add channels conda-forge \
  && conda tos accept --override-channels --channel https://repo.anaconda.com/pkgs/main \
  && conda tos accept --override-channels --channel https://repo.anaconda.com/pkgs/r \
  && conda install -y --quiet plink \
  && conda clean -afy \
  && rm -rf /opt/conda/pkgs/*.tar.bz2

# Set default shell
CMD ["/bin/bash"]
