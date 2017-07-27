# HyperStream-tutorials Dockerfile #
This Dockerfile builds [`HyperStream`](1) from `branch` branch and runs Jupyter
Notebook to serve the tutorials.

It requires running a MongoDB instance on port: 27017, 1883.
You can use provided [MongoDB](2) container.

[1]: https://github.com/IRC-SPHERE/HyperStream
[2]: https://github.com/IRC-SPHERE/Hyperstream-Dockerfiles/tree/master/HyperStream-mongo
