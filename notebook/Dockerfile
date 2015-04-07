# Ubuntu Vivid / Python 3 / IPython Notebook 3.0

FROM ubuntu:vivid
MAINTAINER datatyp

RUN apt-get update
RUN apt-get -y dist-upgrade

# Basic python setup
RUN apt-get -y install python3
RUN apt-get -y install python3-pip

# numpy & friends
RUN apt-get -y build-dep python3-pandas python3-scipy python3-matplotlib python3-matplotlib
RUN pip3 install scipy
RUN pip3 install pandas
RUN pip3 install matplotlib
RUN pip3 install bokeh

# ipython notebook
RUN apt-get -y build-dep python3-zmq
RUN pip3 install pyzmq
RUN pip3 install jinja2
RUN pip3 install tornado
RUN pip3 install jsonschema
RUN pip3 install "ipython[notebook]"

# Other python libs used to get to data
RUN pip3 install elasticsearch

# R
RUN apt-get -y install r-recommended r-cran-evaluate
RUN pip3 install r2_kernel

# Other useful tools
RUN apt-get install -y jq curl

EXPOSE 8888
ENTRYPOINT ipython notebook --ip 0.0.0.0 --no-browser
