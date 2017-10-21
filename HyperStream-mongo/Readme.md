# HyperStream MongoDB Dockerfile #
This Dockerfile builds a simple MongoDB server for [`HyperStream`](https://github.com/IRC-SPHERE/HyperStream) and [`HyperStreamViewer`](https://github.com/IRC-SPHERE/HyperStreamViewer).

In order to keep the MongoDB files on your local machine you can add the following flag to the docker command when running the container:
```
-v ~/hyperstream_mongodb:/home/jovyan/hyperstream
```
