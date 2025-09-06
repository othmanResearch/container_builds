# Makefile to build freesasa-2.1.2 images

IMAGE_NAME = freesasa-2.1.2
DOCKER_TAG = latest
SIF_FILE   = $(IMAGE_NAME).sif
DEF_FILE   = freesasa-2.1.2.def

all: docker singularity

docker:
	@echo "=== Building Docker image: $(IMAGE_NAME):$(DOCKER_TAG) ==="
	docker build -t $(IMAGE_NAME):$(DOCKER_TAG) .

singularity:
	@echo "=== Building Singularity image from definition file ==="
	singularity build $(SIF_FILE) $(DEF_FILE)

clean:
	@echo "=== Removing Docker and Singularity images ==="
	-docker rmi $(IMAGE_NAME):$(DOCKER_TAG)
	-rm -f $(SIF_FILE)

.PHONY: all docker singularity clean

