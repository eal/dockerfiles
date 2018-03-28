# Ubuntu Xenial / Python 3 / IPython Notebook 3.0

FROM ubuntu:bionic
MAINTAINER datatyp

RUN apt-get update && apt-get -y dist-upgrade

# Basic python setup
RUN apt-get -y install python3 python3-pip

# numpy & friends
RUN apt-get -y build-dep python3-pandas python3-scipy python3-matplotlib python3-matplotlib
RUN pip3 install scipy pandas matplotlib bokeh

# ipython notebook
RUN apt-get -y build-dep python3-zmq
RUN pip3 install pyzmq jinja2 tornado jsonschema jupyter

# Other python libs used to get to data
RUN pip3 install elasticsearch

# R
RUN apt-get -y install r-recommended r-cran-evaluate
RUN pip3 install r2_kernel

#mathjax stuff
RUN echo 'from IPython.external import mathjax; mathjax.install_mathjax()' | python3

# Other useful tools
RUN apt-get install -y jq curl

EXPOSE 8888
CMD jupyter notebook --ip 0.0.0.0 --no-browser
