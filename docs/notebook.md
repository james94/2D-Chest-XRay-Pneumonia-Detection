# Deploy Jupyter Notebook Container for Pneumonia Detection

## Create Docker Bridged Network for Backend and Frontend

~~~bash
docker network create -d bridge backend
docker network create -d bridge frontend
~~~

## Deploy Docker Container's Jupyter Notebook in Background

Build Jupyter Notebook Docker Image:

~~~bash
cd ${PWD}/2D-Chest-XRay-Pneumonia-Detection/notebooks/

docker build -t jupyter-pneumonia:dev .
~~~

Launch a Docker container with Jupyter Notebook running:

~~~bash
docker run -d \
    --name pneumonia \
    -v ${PWD}:/pneumoniaDetection \
    -p 8888:8888 \
    --network=frontend \
    jupyter-pneumonia:dev
~~~

For the URL, check logs:

~~~bash
docker logs pneumonia --follow
~~~

We can access our Jupyter Notebook at `url:8888`:

http://127.0.0.1:8888/?token=3594a53157be5d69f05fef00f82393e74bcb624d7726d82d

Jump into docker container:

~~~bash
docker exec -it pneumonia bash
~~~


