# HyperStream Docker images #
This repository contains Docker images for the whole HyperStream collection:
* [`HyperStream`](https://github.com/IRC-SPHERE/HyperStream)
* [`HyperStreamViewer`](https://github.com/IRC-SPHERE/HyperStreamViewer)
* `MQTT` container
* `MongoDB` container

## Running ##
To run the bundle you need [Docker](https://docs.docker.com/engine/installation/) installed. Then clone this repository, enter it and build the bundle with:
```
git clone https://github.com/IRC-SPHERE/Hyperstream-Dockerfiles.git
cd Hyperstream-Dockerfiles
docker-compose build
```

Finally, run the bundle with:
```
docker-compose up
```

wait for the containers to start and point your browser to [`127.0.0.1:5000`](http://127.0.0.1:5000) to see the HyperStreamViewer up and running.

To close the containers press `<Ctrl>-C` in the terminal running the containers.

## HyperStream tutorials ##
You can run HyperStream tutorials with:
```
docker-compose -f docker-compose-tutorials.yml -p hyperstream-tutorials up
```

Then, in the same terminal there will be a line with an url that point to the tutorials. Just use the full url in a webbrowser.

```bash
hyperstream_1         |     Copy/paste this URL into your browser when you connect for the first time,
hyperstream_1         |     to login with a token:
hyperstream_1         |         http://0.0.0.0:8888/?token=d7ce9aed098ff2881433bd3ad53979b82979cf6d99e6f598
```
