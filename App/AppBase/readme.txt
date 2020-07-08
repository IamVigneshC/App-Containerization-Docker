This directory contains the Dockerfile to create the Base image for all App containers

The base images is responsible for downloading and installing all of the libraries and python modules
needed by all other dependent containers.

cd \<base dir>

docker build -t app:base .
