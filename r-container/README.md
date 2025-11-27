# r-container

A repository containing the Dockerfile to build a Docker image for **R** (version 4.5.2) with essential CRAN packages installed (`ggplot2`, `dplyr`, `data.table`).

## Contents

* **Dockerfile** – builds a minimal Docker image with R and selected CRAN packages.
* **.dockstore.yml** – defines metadata, inputs, outputs, and execution instructions for Dockstore.

## Usage

### Build the Docker image locally

```bash
docker build -t tiffany00123/r-base:latest .
```

### Run the container interactively

```bash
docker run -it tiffany00123/r-base:latest /bin/bash
```

### Inside the container, you can use R as usual:

```R
library(ggplot2)
library(dplyr)
library(data.table)

# Example
data(mtcars)
summary(mtcars)
```

### Push to Docker Hub

```bash
docker push tiffany00123/r-base:latest .
```

## Notes

* This container is intended for R-based data analysis and visualization.
* Additional CRAN packages can be installed later via `install.packages()` inside the container.
* Built on Ubuntu 22.04 with minimal dependencies for reproducibility and small image size.
