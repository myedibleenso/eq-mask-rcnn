# mask-rcnn for equation detection


## Building the docker container

```
docker build -f Dockerfile.gpu -t edu.arizona/mask-rcnn .
```

## Running the equation notebook

```
# NOTE: this incantation assumes you're running the command 
# from the project root. Changes to files under notebooks 
# will be written from client to host.

nvidia-docker run --rm -it -d \
  -p 7777:9999 \
  -v "${PWD}/notebooks:/app/notebooks" \
  -v path/to/datasets:/input \
  -v path/to/output:/output \
  edu.arizona/mask-rcnn:latest sh scripts/launch-eq-notebook.sh
```
Open [localhost:7777](http://localhost:7777) to view the jupyter notebooks.
