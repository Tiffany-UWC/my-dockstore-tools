# Use official R base image
FROM r-base:4.5.2

# Metadata
LABEL maintainer="4129565@myuwc.ac.za"

# Install essential build tools
RUN apt-get update && apt-get install -y \
    build-essential \
  && rm -rf /var/lib/apt/lists/*

# Install CRAN packages
RUN R -e 'install.packages(c("ggplot2", "dplyr", "data.table", "htmltools"), repos="https://cloud.r-project.org")'

# Set default command to R
CMD ["R"] 
