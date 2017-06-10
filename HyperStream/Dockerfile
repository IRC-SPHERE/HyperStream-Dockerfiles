FROM hyperstream-dockerfiles/hyperstream-base

MAINTAINER Kacper Sokol <ks1591@bristol.ac.uk>

# TODO: clone with depth level 1 and by tag not the latest commit
RUN git clone https://github.com/IRC-SPHERE/HyperStream.git $HYPERSTREAM_DIR
RUN pip install --user -r $HYPERSTREAM_DIR/requirements.txt

ENV PATH $HOME/.local/bin:$PATH

WORKDIR $HYPERSTREAM_DIR

# TODO add another config file for docker
RUN sed -i -e 's/localhost/hyperstream-mongo/g' hyperstream_config.json

# Test HyperStream
RUN python -c 'from hyperstream import HyperStream'

ENTRYPOINT nosetests --with-coverage
#ENTRYPOINT /bin/bash
