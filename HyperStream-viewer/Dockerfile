FROM ubuntu:16.04

MAINTAINER Kacper Sokol <ks1591@bristol.ac.uk>

ARG DEBIAN_FRONTEND=noninteractive

USER root
RUN apt-get update \
  && apt-get upgrade

RUN apt-get install -y \
    git \
    python \
    python-pip


ENV SHELL /bin/bash
ENV HYPERSTREAM_USER jovyan
ENV HYPERSTREAM_UID 1000
ENV HOME /home/$HYPERSTREAM_USER
ENV HYPERSTREAM_DIR $HOME/hyperstream

# Create jovyan user with UID=1000 and in the 'users' group \ -N -u $SWISH_UID
RUN useradd -m -s $SHELL $HYPERSTREAM_USER

RUN mkdir -p $HYPERSTREAM_DIR \
  && chown $HYPERSTREAM_USER $HYPERSTREAM_DIR
USER $HYPERSTREAM_USER

# TODO: clone with depth level 1 and by tag not the latest commit
RUN git clone https://github.com/IRC-SPHERE/HyperStreamViewer.git $HYPERSTREAM_DIR
RUN pip install --user -r $HYPERSTREAM_DIR/requirements.txt

# TODO : requirements fail: missing simplejson
RUN pip install --user simplejson

# Run HyperStreamViewer
WORKDIR $HYPERSTREAM_DIR

#RUN ./config_local.sh
# TODO: confing_local complains with rm when the file does not exist
RUN rm -f hyperstream_config.json
RUN ln -s hyperstream_config_local.json hyperstream_config.json

# TODO add another config file for docker
RUN sed -i -e 's/localhost/hyperstream-mongo/g' hyperstream_config.json

EXPOSE 5000

RUN python server.py
