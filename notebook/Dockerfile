# Ubuntu / Python 3 / Jupyter / R

FROM ubuntu:groovy
MAINTAINER datatyp

RUN apt-get update && apt-get -y dist-upgrade

## for apt to be noninteractive
ENV DEBIAN_FRONTEND noninteractive
ENV DEBCONF_NONINTERACTIVE_SEEN true

## preesed tzdata, update package index, upgrade packages and install needed software
RUN echo "tzdata tzdata/Areas select Europe" > /tmp/preseed.txt; \
    echo "tzdata tzdata/Zones/Europe select Stockholm" >> /tmp/preseed.txt; \
    debconf-set-selections /tmp/preseed.txt && \
    rm -f /etc/timezone && \
    rm -f /etc/localtime && \
    apt-get update && \
    apt-get install -y tzdata

# Basic python setup
RUN apt-get -y install python3 python3-pip

# numpy & friends
RUN apt-get -y install python3-pandas python3-scipy python3-matplotlib python3-matplotlib python3-openpyxl
RUN pip3 install scipy pandas matplotlib bokeh

# ipython notebook
#RUN apt-get -y build-dep python3-zmq
RUN apt-get -y install python3-zmq
RUN pip3 install jinja2 tornado jsonschema jupyter

# Other python libs used to get to data
RUN pip3 install elasticsearch requests simplejson

# R
# RUN apt-get -y install r-recommended r-cran-evaluate
# RUN pip3 install r2_kernel

#mathjax stuff
# RUN echo 'from IPython.external import mathjax; mathjax.install_mathjax()' | python3

# Other useful tools
RUN apt-get install -y jq curl

# Clean up
RUN apt-get clean && rm -rf /root/.cache /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN useradd -u 1000 -m jupyter
RUN mkdir /home/jupyter/.jupyter && chown -R jupyter:jupyter /home/jupyter

# mount a volume on data for persistence
RUN mkdir -p /data && chown -R jupyter:jupyter /data

# and separate for config
RUN mkdir -p /etc/jupyter

VOLUME /data
WORKDIR /data
USER jupyter

EXPOSE 8888
CMD jupyter notebook --ip 0.0.0.0 --no-browser
