# HyperStream-tutorials Dockerfile #
This Dockerfile builds [`HyperStream`](https://github.com/IRC-SPHERE/HyperStream) from `tutorials` branch and runs Jupyter Notebook to serve the tutorials.

It requires running MongoDB and MQTT instances on ports: 27017, 1883 and 9001. You can use provided [MongoDB](https://github.com/IRC-SPHERE/Hyperstream-Dockerfiles/tree/master/HyperStream-mongo) and [`toke/mosquitto`](https://hub.docker.com/r/toke/mosquitto/builds/bmvxctuhjvcui9nfqujvkdw/) MQTT containers.
