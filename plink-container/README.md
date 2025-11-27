# plink-container

A repository containing the Dockerfile to build a Docker image for the **PLINK** command-line tool (version1.9) installed via Bioconda. 

# Contents

* **Dockerfile** – builds a minimal Docker image with PLINK installed via Bioconda.
* **dockstore.yml** – defines metadata, inputs, outputs, and execution instructions for Dockstore.

# Usage

Build the Docker image locally

```bash
docker build -t <dockerhub_username>/bioconda-plink:latest .
```

Run the container interactively

```bash
docker run -it <dockerhub_username>/bioconda-plink:latest .
```

Inside the container, you can run PLINK commands:

```bash
plink --version
plink --bfile mydata --assoc --out results
```

Push to Docker Hub

```bash
docker push <dockerhub_username>/plink-minimal:1.0
```

# Notes

* This container is intended for single-purpose PLINK analyses.
* Additional bioinformatics tools (e.g., tabix, samtools) can be added later via Bioconda.
* Built on Ubuntu 22.04 with Miniconda for reproducibility.
