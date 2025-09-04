# Makefile to build Docker and Singularity images

# Variables
DOCKER_IMAGE_NAME := stride
DOCKER_TAG := latest
SINGULARITY_IMAGE := stride.sif
DEF_FILE := stride.def

# Default target
all: docker singularity

# Build Docker image
docker:
	docker build -t $(DOCKER_IMAGE_NAME):$(DOCKER_TAG) .

# Build Singularity directly from definition file
singularity:
	singularity build $(SINGULARITY_IMAGE) $(DEF_FILE)


